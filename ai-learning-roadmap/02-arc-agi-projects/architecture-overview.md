# 🏗️ ARC-AGI Projects: Cumulative Architecture Overview

This document describes how all 4 ARC-AGI projects fit together into a single, progressively improving system. Each project adds a new architectural layer; by Project 4, the system is a unified hybrid that combines classical ML, deep learning, LLM program synthesis, and reasoning.

---

## System Diagram (Text)

```
┌────────────────────────────────────────────────────────────────────┐
│                   ARC-REASONER (Project 4)                         │
│  Reasoning model (Book 4): chain-of-thought + GRPO + test-time     │
│  search over solution hypotheses. Generates, evaluates, and         │
│  selects best solution from ARC-Programmer's candidate pool.        │
│                                                                      │
│  ┌──────────────────────────────────────────────────────────────┐  │
│  │                ARC-PROGRAMMER (Project 3)                    │  │
│  │  LLM (Book 3): fine-tuned on ARC DSL. Given grid repr.       │  │
│  │  from ARC-NeuralSolver, generates candidate programs.         │  │
│  │                                                               │  │
│  │  ┌──────────────────────────────────────────────────────┐   │  │
│  │  │            ARC-NEURALSOLVER (Project 2)              │   │  │
│  │  │  CNN + Attention (Book 2): reads raw ARC grids,       │   │  │
│  │  │  produces object-centric representations and          │   │  │
│  │  │  transformation hypotheses.                           │   │  │
│  │  │                                                       │   │  │
│  │  │  ┌────────────────────────────────────────────────┐  │   │  │
│  │  │  │         ARC-PERCEIVER (Project 1)              │  │   │  │
│  │  │  │  Classical ML (Book 1): spatial feature         │  │   │  │
│  │  │  │  extractor. Produces rule candidates,           │  │   │  │
│  │  │  │  symmetry flags, and color mappings from        │  │   │  │
│  │  │  │  input/output pairs.                            │  │   │  │
│  │  │  └────────────────────────────────────────────────┘  │   │  │
│  │  └──────────────────────────────────────────────────────┘   │  │
│  └──────────────────────────────────────────────────────────────┘  │
└────────────────────────────────────────────────────────────────────┘
```

---

## Cumulative Score Targets

| Project | What It Adds | ARC-AGI-1 Target | ARC-AGI-2 Target |
|---|---|---|---|
| Project 1: ARC-Perceiver | Classical feature extraction + rule templates | 15–25% | 5–10% |
| Project 2: ARC-NeuralSolver | Deep learning object-centric perception | 30–42% | 10–18% |
| Project 3: ARC-Programmer | LLM-based program synthesis | 48–62% | 20–35% |
| Project 4: ARC-Reasoner | Reasoning + RL + test-time search | 55–70% | 30–50% |

> **Note:** Scores are ranges reflecting realistic outcomes under different implementation choices, compute budgets, and training data quality. Current top open-source ARC-AGI-1 scores are ~60–85% (with heavy augmentation and search). ARC-AGI-2 is significantly harder; 30–50% would be highly competitive.

---

## Data Strategy (Shared Across All Projects)

| Dataset | Size | Use |
|---|---|---|
| ARC-AGI-1 Training Set | 400 tasks | Primary training/evaluation |
| ARC-AGI-1 Evaluation Set | 400 tasks | Benchmark scoring |
| ARC-AGI-2 Tasks | ~1000 tasks (est.) | Stretch goal for Project 4 |
| Re-ARC (synthetic) | 400 × 100 instances | Data augmentation for Projects 2–4 |
| LARC (natural language) | 400 tasks + descriptions | Grounding for LLM in Project 3 |
| ARC-Heavy (community) | Varies | Supplement training for Project 4 |

---

## Shared Codebase Structure

```
arc-system/
├── data/
│   ├── arc_train/          # Official ARC-AGI-1 training tasks
│   ├── arc_eval/           # Official ARC-AGI-1 evaluation tasks
│   ├── arc2/               # ARC-AGI-2 tasks
│   ├── rearc/              # Re-ARC synthetic augmentation
│   └── larc/               # LARC natural language annotations
│
├── perceiver/              # Project 1: classical ML feature extraction
│   ├── features.py
│   ├── rule_templates.py
│   └── classifier.py
│
├── neuralsolver/           # Project 2: CNN + attention model
│   ├── model.py
│   ├── object_centric.py
│   └── train.py
│
├── programmer/             # Project 3: LLM program synthesizer
│   ├── dsl.py              # Domain-Specific Language definition
│   ├── tokenizer.py
│   ├── model.py            # Fine-tuned GPT-style LLM
│   └── finetune.py
│
├── reasoner/               # Project 4: reasoning model + RL
│   ├── cot_model.py        # Chain-of-thought wrapper
│   ├── grpo.py             # Group Relative Policy Optimization
│   ├── search.py           # Best-of-N test-time search
│   └── train_rl.py
│
├── eval/
│   ├── arc_eval.py         # Standard ARC evaluation harness
│   ├── score.py
│   └── leaderboard.md
│
└── utils/
    ├── grid_utils.py
    ├── visualization.py
    └── augmentation.py
```

---

## Integration Protocol

At each project stage, the new component integrates with previous ones via a **solver pipeline**:

1. **ARC-Perceiver** runs first: extracts spatial features, color mappings, symmetry flags, and candidate rules. Outputs a structured `PerceptionBundle`.
2. **ARC-NeuralSolver** takes the `PerceptionBundle` + raw grids as input: refines the object decomposition and produces a ranked list of transformation hypotheses.
3. **ARC-Programmer** takes the transformation hypotheses and generates programs in the ARC-DSL. Each program is executed against training examples.
4. **ARC-Reasoner** uses chain-of-thought reasoning to select, refine, and verify the best program. Applies test-time search to maximize correctness.

---

## Evaluation Methodology

- **Primary metric:** ARC-AGI official score (% of evaluation tasks correctly solved)
- **Secondary metrics:** Per-category accuracy (geometry, symmetry, color, pattern, counting)
- **Ablation tracking:** Each project adds a module; ablations confirm each module's contribution
- **Reproducibility:** All runs logged with seeds, hyperparameters, and dataset splits in `eval/leaderboard.md`

---

## Research Outputs

| Project | Target Research Output |
|---|---|
| Project 1 | Technical report / blog post: "Classical ML baselines for ARC-AGI" |
| Project 2 | Workshop paper: "Object-Centric Deep Learning for Abstract Visual Reasoning" |
| Project 3 | Workshop paper: "Program Synthesis via Fine-tuned LLMs for ARC-AGI" |
| Project 4 | Conference paper (ICLR / NeurIPS workshop): "Reasoning Models with RL for ARC-AGI-2" |
