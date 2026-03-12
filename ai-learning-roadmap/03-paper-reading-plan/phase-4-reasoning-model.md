# Phase 4 Paper Reading Plan: Reasoning Models, RL & Frontier ARC

**Book Pairing:** Book 4 — *Build a Reasoning Model from Scratch* (Raschka)  
**Timeline:** August 10 – October 11, 2026 (9 weeks, ~28 papers)  
**Reading Pace:** 1 paper per 2 days  
**Project Context:** ARC-Reasoner (Project 4)

---

## Goals for This Phase

By the end of Phase 4, you will be able to:
- Implement GRPO from scratch and explain why it is preferable to PPO for reasoning models
- Design reward functions for non-trivial tasks (not just exact match)
- Implement test-time search and understand its relationship to inference-time scaling
- Have a system competitive with published results on ARC-AGI-1 and competitive on ARC-AGI-2
- Have a near-complete conference paper draft

---

## Paper Schedule

| # | Date | Paper | Theme | Why Read |
|---|---|---|---|---|
| 1 | 2026-08-10 | Wei et al. (2022) — *Chain-of-Thought Prompting Elicits Reasoning in LLMs* | CoT | Foundation of chain-of-thought (also in Phase 3 intro) |
| 2 | 2026-08-12 | Kojima et al. (2022) — *Large Language Models are Zero-Shot Reasoners* | CoT | "Let's think step by step" — zero-shot CoT |
| 3 | 2026-08-14 | Schulman et al. (2017) — *Proximal Policy Optimization Algorithms* (PPO) | RL | The RL algorithm GRPO replaces; understand the baseline |
| 4 | 2026-08-16 | Shao et al. (2024) — *DeepSeekMath: Pushing the Limits of Mathematical Reasoning* (GRPO paper) | GRPO | **Core paper.** The original GRPO algorithm you'll implement |
| 5 | 2026-08-18 | Guo et al. (2025) — *DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via RL* | RL Reasoning | **Core paper.** DeepSeek-R1: GRPO at scale; your primary inspiration |
| 6 | 2026-08-20 | **CHECKPOINT 1** — Implement GRPO training loop; test on simple ARC tasks | — | — |
| 6 | 2026-08-20 | Jaech et al. (2024) — *OpenAI o1: Scaling Reasoning at Test Time* | Test-Time Compute | The reasoning scaling law; test-time compute budget |
| 7 | 2026-08-22 | Snell et al. (2024) — *Scaling LLM Test-Time Compute Optimally* | Test-Time Compute | How to allocate test-time compute budget optimally |
| 8 | 2026-08-24 | Lightman et al. (2023) — *Let's Verify Step by Step* (Process Reward Models) | Reward Modeling | Process vs outcome rewards; partial credit in ARC |
| 9 | 2026-08-26 | Luo et al. (2024) — *Improve Mathematical Reasoning in LLMs via Refined Process Reward Models* | Reward Modeling | Better process rewards; apply to ARC |
| 10 | 2026-08-28 | Zeiler & Fergus (2014) — *Visualizing and Understanding Convolutional Networks* | Interpretability | Understand what your model is actually learning |
| 11 | 2026-08-30 | Finn et al. (2017) — *Model-Agnostic Meta-Learning* (MAML) | Meta-Learning | Few-shot learning; ARC requires learning from 2–5 examples |
| 12 | 2026-09-01 | **CHECKPOINT 2** — GRPO training complete on ARC tasks; initial ARC-AGI-1 score with reasoning | — | — |
| 12 | 2026-09-01 | Madaan et al. (2023) — *Self-Refine: Iterative Refinement with Self-Feedback* | Self-Correction | Iterative self-improvement; ARC-Reasoner's refinement loop |
| 13 | 2026-09-03 | Yao et al. (2023) — *Tree of Thoughts: Deliberate Problem Solving with LLMs* | Search | Tree-based reasoning search; extends best-of-N |
| 14 | 2026-09-05 | Besta et al. (2024) — *Graph of Thoughts: Solving Elaborate Problems with LLMs* | Search | Graph-based reasoning; more expressive than tree |
| 15 | 2026-09-07 | Wang et al. (2024) — *Scaling LLM Inference with Test-Time Compute* | Inference Scaling | Practical implementation guidance |
| 16 | 2026-09-09 | Zeng et al. (2025) — *Scaling of Search and Learning: A Roadmap to Reproduce o1* | Reasoning | How to build an o1-style system from scratch |
| 17 | 2026-09-11 | **CHECKPOINT 3** — Test-time search implemented; compare Best-of-N vs Tree-of-Thoughts on ARC | — | — |
| 17 | 2026-09-11 | Wang et al. (2024) — *ARC Prize 2024: Technical Report* | ARC Competition | Competition winners' methods; what works on ARC |
| 18 | 2026-09-13 | Banburski-Fahey et al. (2024) — *Hypothesis Search: Inductive Reasoning with Language Models* | ARC + Reasoning | Inductive reasoning framework for ARC tasks |
| 19 | 2026-09-15 | Acquaviva et al. (2022) — *Communicating Natural Programs to Humans and Machines* (LARC) | ARC Data | LARC dataset; natural language annotations for ARC |
| 20 | 2026-09-17 | Holt et al. (2024) — *ARC-AGI and the Illusion of Understanding* | ARC Critique | Critical perspective on ARC as a benchmark |
| 21 | 2026-09-19 | Tegmark & Omohundro (2023) — *Provably Safe Systems* | AI Safety | Broader context: responsible development |
| 22 | 2026-09-21 | **CHECKPOINT 4** — ARC-Reasoner v1 complete; ARC-AGI-1 score ≥ 55%; start paper writing | — | — |
| 22 | 2026-09-21 | Chollet et al. (2024) — *ARC-AGI-2: An Improved Benchmark for General Intelligence* | ARC-AGI-2 | **Core paper.** The new benchmark you're targeting |
| 23 | 2026-09-23 | Kambhampati et al. (2024) — *Can LLMs Really Reason and Plan?* | LLM Reasoning | Critical perspective on LLM reasoning claims |
| 24 | 2026-09-25 | Mirzadeh et al. (2024) — *GSM-Symbolic: Understanding LLM Limitations in Symbolic Math* | Reasoning Limits | Understand limits of reasoning models |
| 25 | 2026-09-27 | Amodei et al. (2025) — *Scaling and the Future of AI* | Scaling | Future direction context |
| 26 | 2026-09-29 | Brown et al. (2024) — *Large Concept Models: Language Modeling in a Sentence Representation Space* | LLM Future | Alternative to token-level models |
| 27 | 2026-10-01 | **CHECKPOINT 5** — ARC-Reasoner v2 (with ARC-AGI-2 adaptations); score ≥ 30% on ARC-2 | — | — |
| 27 | 2026-10-01 | Xu & Chollet (2025) — *ARC-AGI-2 Prize Winners Technical Reports* (if available) | ARC-AGI-2 | Learn from competition winners |
| 28 | 2026-10-03 | Yang et al. (2024) — *Qwen2.5-Coder Technical Report* | Code LLMs | State-of-the-art code model; compare to your approach |

---

## ⭐ Priority Papers (read first if time is short)

1. **Shao et al. (2024)** — *DeepSeekMath / GRPO*: Your primary algorithmic innovation
2. **Guo et al. (2025)** — *DeepSeek-R1*: The model you're replicating at ARC-scale
3. **Chollet et al. (2024)** — *ARC-AGI-2*: Your primary target benchmark
4. **Wang et al. (2024)** — *ARC Prize 2024 Technical Report*: What actually works

---

## Implementation Milestones in This Phase

| Milestone | Date | Description |
|---|---|---|
| GRPO Implementation | 2026-08-20 | Working GRPO training loop on toy reasoning tasks |
| ARC Reward Function | 2026-08-28 | Exact match + partial credit reward |
| RL Training Complete | 2026-09-01 | 5000 GRPO steps on ARC data |
| Test-Time Search | 2026-09-11 | Best-of-N + iterative refinement working |
| Self-Correction | 2026-09-17 | Model learns to detect and fix its own errors |
| ARC-AGI-1 ≥ 55% | 2026-09-21 | Primary target achieved |
| ARC-AGI-2 ≥ 30% | 2026-10-01 | Stretch target attempted |
| Paper Draft | 2026-10-08 | 8-page paper ready for workshop submission |

---

## Checkpoint Criteria

| Checkpoint | Date | Pass Criteria |
|---|---|---|
| Checkpoint 1 | 2026-08-20 | GRPO loop coded; trains stably on toy task |
| Checkpoint 2 | 2026-09-01 | RL training complete; ARC-AGI-1 score improved over Project 3 |
| Checkpoint 3 | 2026-09-11 | Test-time search implemented; Tree-of-Thoughts vs Best-of-N ablation done |
| Checkpoint 4 | 2026-09-21 | ARC-AGI-1 ≥ 55%; paper introduction and related work written |
| Checkpoint 5 | 2026-10-01 | ARC-AGI-2 ≥ 30%; full paper draft complete |
| Phase Complete | 2026-10-11 | All 28 papers read; paper submitted to workshop |
