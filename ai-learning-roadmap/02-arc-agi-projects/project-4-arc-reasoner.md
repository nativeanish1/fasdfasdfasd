# Project 4: ARC-Reasoner

**Book:** *Build a Reasoning Model from Scratch* (Raschka) (Book 4)  
**Timeline:** October 2026 (after completing Book 4 in September 2026)  
**ARC-AGI-1 Target Score:** 55–70% (cumulative with Projects 1–3)  
**ARC-AGI-2 Target Score:** 30–50% (cumulative)  
**Research Output:** Conference paper (ICLR/NeurIPS workshop) — "Reasoning Models with RL for ARC-AGI-2"

---

## Motivation

ARC-Programmer generates programs but has no mechanism to *reason* about which program is correct or to *improve* based on mistakes. ARC-Reasoner adds:

1. **Chain-of-thought reasoning**: the model explicitly thinks through the ARC task before generating a program
2. **GRPO training**: the model is reinforced when its programs solve ARC tasks correctly
3. **Test-time search**: at evaluation, generate many reasoning chains and programs; execute and select the best
4. **Self-correction**: the model learns to detect and fix its own errors

This is the frontier of AI research (DeepSeek-R1, OpenAI o1) applied to ARC. It is the most ambitious component and the most likely to produce a publishable result.

---

## Architecture

### Chain-of-Thought Reasoning Format

The model is trained to produce reasoning in the following format:

```
<think>
Step 1: Analyze the input/output pairs.
  - Input 1 is a 5×5 grid with a blue cross shape on black background.
  - Output 1 has the same shape but colored red.
  - Input 2 is a 7×7 grid with a blue L-shape.
  - Output 2 has the same L-shape but colored red.

Step 2: Identify the transformation rule.
  - In both examples, the non-background object is recolored from blue to red.
  - Background color (black) is unchanged.
  - Object shape is unchanged.

Step 3: Hypothesize the rule.
  - Rule: recolor all non-background cells from their current color to red.

Step 4: Verify against training examples.
  - Applying recolor(non_background, red) to Input 1 produces Output 1. ✓
  - Applying recolor(non_background, red) to Input 2 produces Output 2. ✓

Step 5: Generate program.
  - def solve(g): return replace_color(g, BLUE, RED)
</think>
<program>
def solve(g):
    return replace_color(g, BLUE, RED)
</program>
```

---

## GRPO Training

Group Relative Policy Optimization (GRPO) — as covered in Book 4 — is applied with ARC task correctness as the reward signal:

```
Reward function:
  R(program, task) = 1.0  if program(test_input) == expected_output
  R(program, task) = 0.0  if program produces wrong output or error

GRPO objective:
  For each task, sample G=8 completions (reasoning chains + programs)
  Compute advantages: A_i = (R_i - mean(R)) / std(R)
  Update model to increase probability of high-advantage completions
```

### Why GRPO Over PPO

| Aspect | GRPO | PPO |
|---|---|---|
| Critic network | Not needed | Required (doubles compute) |
| Memory efficiency | High | Lower |
| Stability for code generation | Strong | Can be unstable |
| Implementation complexity | Moderate | High |
| Book 4 coverage | Deep | Moderate |

---

## Test-Time Search

At evaluation time (not training), the model generates multiple candidate solutions and selects the best:

### Best-of-N Sampling
```
For each ARC test task:
  1. Generate N=32 reasoning chains + programs (temperature=0.8)
  2. Execute each program against the training input/output pairs
  3. Score: fraction of training examples correctly solved
  4. Select top-ranked program
  5. Submit as prediction
```

### Iterative Refinement
```
If no program achieves perfect score on training examples:
  1. Take the best partial program (highest training score)
  2. Generate a "correction prompt": show where it fails
  3. Generate 16 correction candidates
  4. Re-evaluate and re-rank
  5. Repeat up to 3 iterations
```

---

## Technical Specifications

| Component | Specification |
|---|---|
| Base model | ARC-Programmer fine-tuned LLM (117M params) |
| Reasoning format | XML-tagged CoT: `<think>...</think><program>...</program>` |
| GRPO group size | G=8 completions per task |
| RL training steps | 5000 steps (batch size 4 tasks) |
| Training tasks | 400 ARC-AGI-1 + 40K Re-ARC synthetic |
| Learning rate | 1e-5 (lower than pretraining; stable RL) |
| KL penalty coefficient | β=0.04 (prevent model from deviating too far) |
| Test-time samples | N=32 per task |
| Search budget | 3 refinement iterations |

---

## ARC-AGI-2 Specific Adaptations

ARC-AGI-2 is significantly harder than ARC-AGI-1, featuring:
- Tasks requiring longer reasoning chains
- Higher-order transformations (operations on operations)
- More abstract analogical reasoning

Adaptations for ARC-AGI-2:
1. **Extended context window**: increase from 2048 to 4096 tokens for complex tasks
2. **Hierarchical reasoning**: train the model to decompose multi-step tasks into sub-problems
3. **Meta-reasoning**: train a separate classifier to detect when a task is "ARC-1-style" vs "ARC-2-style" and route to different reasoning depths
4. **More search budget**: N=64 for ARC-2 tasks (they are harder)

---

## Reward Shaping

Beyond exact match (binary reward), implement partial credit rewards:

| Reward Signal | Value | Description |
|---|---|---|
| Exact match | 1.0 | Program produces perfect output |
| Almost correct (1 cell wrong) | 0.7 | Encourages refinement |
| Correct shape, wrong color | 0.4 | Structure is right; color rule is wrong |
| Correct size, wrong shape | 0.2 | Some structure recognized |
| Total failure | 0.0 | Program crashes or produces nonsense |

Partial credit rewards stabilize GRPO training and speed up convergence by 2–3×.

---

## Self-Correction Training

A specialized fine-tuning stage where the model learns to correct its own mistakes:

1. **Error dataset generation**: run ARC-Programmer on training tasks; collect near-miss failures
2. **Correction fine-tuning**: train the model to recognize error patterns and generate corrections
3. **Format**: `<wrong_program>...</wrong_program><error_analysis>...</error_analysis><corrected_program>...</corrected_program>`

This stage is unique to Project 4 and is the primary source of improvement over Project 3.

---

## Expected Challenges

| Challenge | Mitigation |
|---|---|
| GRPO training instability | Monitor KL divergence; reduce learning rate if KL spikes |
| Reasoning chains become repetitive | Diversity penalty in sampling; min-edit distance filter |
| 400 ARC tasks not enough for RL | Use Re-ARC 40K + synthetic RL environments |
| ARC-2 tasks overwhelmingly hard | Focus on ARC-1 first; ARC-2 is stretch goal |
| Compute requirements for test-time search | Cache intermediate results; prune clearly wrong programs early |

---

## Compute Requirements

| Stage | Estimated Time | Hardware |
|---|---|---|
| GRPO training (5000 steps) | ~5 days | Single A100 80GB (or equivalent) |
| Test-time search (N=32) | ~2 hours for 400 tasks | Single GPU |
| Full ARC-AGI-1 evaluation | ~30 minutes | Single GPU |
| Full ARC-AGI-2 evaluation | ~2 hours | Single GPU |

> **Note:** These estimates assume 117M parameter model. Larger models (345M, 1.3B) would improve scores but require proportionally more compute.

---

## Deliverables

- [ ] `reasoner/cot_model.py` — CoT wrapper over ARC-Programmer
- [ ] `reasoner/grpo.py` — GRPO training implementation
- [ ] `reasoner/search.py` — best-of-N + iterative refinement
- [ ] `reasoner/train_rl.py` — full RL training pipeline
- [ ] ARC-AGI-1 evaluation score ≥ 55%
- [ ] ARC-AGI-2 evaluation score ≥ 30%
- [ ] Conference paper draft (8 pages): full system + ablations + comparison with SOTA
- [ ] Submission to ICLR 2027 workshop or NeurIPS 2026 workshop
- [ ] Competition submission to ARC-AGI prize (if active)
