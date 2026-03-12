# Phase 3 Paper Reading Plan: Transformers, LLMs & Program Synthesis

**Book Pairing:** Book 3 — *Build an LLM from Scratch* (Raschka)  
**Timeline:** June 15 – August 9, 2026 (8 weeks, ~24 papers)  
**Reading Pace:** 1 paper per 2 days  
**Project Context:** ARC-Programmer (Project 3)

---

## Goals for This Phase

By the end of Phase 3, you will be able to:
- Understand the full transformer/GPT architecture from a research paper perspective (not just a textbook)
- Implement a custom tokenizer for non-standard inputs (ARC grids)
- Understand program synthesis as a research area and its application to ARC
- Know the current state of LLMs on ARC tasks (spoiler: they are surprisingly bad, and for a specific reason)

---

## Paper Schedule

| # | Date | Paper | Theme | Why Read |
|---|---|---|---|---|
| 1 | 2026-06-15 | Radford et al. (2018) — *Improving Language Understanding by Generative Pre-Training* (GPT-1) | LLMs | The original GPT; your Book 3 architecture |
| 2 | 2026-06-17 | Radford et al. (2019) — *Language Models are Unsupervised Multitask Learners* (GPT-2) | LLMs | GPT-2 scaling; the model you'll fine-tune |
| 3 | 2026-06-19 | Brown et al. (2020) — *Language Models are Few-Shot Learners* (GPT-3) | LLMs | In-context learning; few-shot prompting for ARC |
| 4 | 2026-06-21 | Devlin et al. (2019) — *BERT: Pre-training of Deep Bidirectional Transformers* | LLMs | Bidirectional context; understanding vs generation |
| 5 | 2026-06-23 | Raffel et al. (2020) — *Exploring the Limits of Transfer Learning with T5* | LLMs | Sequence-to-sequence framing; alternative to GPT |
| 6 | 2026-06-25 | **CHECKPOINT 1** — Implement GPT-2-style model (Book 3, Chapters 4–6); test on ARC task generation | — | — |
| 6 | 2026-06-25 | Wei et al. (2022) — *Chain-of-Thought Prompting Elicits Reasoning in Large Language Models* | CoT | Foundation of Project 4; intro in Phase 3 |
| 7 | 2026-06-27 | Wei et al. (2022) — *Emergent Abilities of Large Language Models* | Scaling | What capabilities emerge and when |
| 8 | 2026-06-29 | Ellis et al. (2021) — *DreamCoder: Bootstrapping Inductive Program Synthesis with Wake-Sleep Library Learning* | Program Synthesis | **Core paper.** DreamCoder is the best program synthesis system for ARC |
| 9 | 2026-07-01 | Devlin et al. (2017) — *RobustFill: Neural Program Learning under Noisy I/O* | Program Synthesis | Neural approaches to program induction |
| 10 | 2026-07-03 | Nye et al. (2021) — *Show Your Work: Scratchpads for Intermediate Computation* | CoT / Scratchpad | Scratchpad reasoning; precursor to chain-of-thought |
| 11 | 2026-07-05 | Austin et al. (2021) — *Program Synthesis with Large Language Models* | Program Synthesis + LLMs | LLMs for code generation; your Project 3 approach |
| 12 | 2026-07-07 | **CHECKPOINT 2** — Design ARC-DSL; implement 10 core operations; test on 20 ARC tasks | — | — |
| 12 | 2026-07-07 | Li et al. (2022) — *Competition-Level Code Generation with AlphaCode* | Program Synthesis | AlphaCode: large-scale program synthesis |
| 13 | 2026-07-09 | Chen et al. (2021) — *Evaluating Large Language Models Trained on Code* (Codex/HumanEval) | Code Generation | How to evaluate code-generating LLMs |
| 14 | 2026-07-11 | Ouyang et al. (2022) — *Training Language Models to Follow Instructions with Human Feedback* (InstructGPT) | RLHF | Book 3's instruction fine-tuning chapter in context |
| 15 | 2026-07-13 | Ziegler et al. (2019) — *Fine-Tuning Language Models from Human Preferences* | RLHF | Original RLHF paper |
| 16 | 2026-07-15 | Lewkowycz et al. (2022) — *Solving Quantitative Reasoning Problems with Language Models* (Minerva) | Math + LLMs | Mathematical reasoning with LLMs |
| 17 | 2026-07-17 | **CHECKPOINT 3** — ARC-Programmer LLM fine-tuned on DSL; evaluate on ARC-AGI-1 | — | — |
| 17 | 2026-07-17 | Wang et al. (2022) — *Self-Consistency Improves Chain of Thought Reasoning* | CoT | Sampling multiple chains; selecting by majority vote |
| 18 | 2026-07-19 | Drozdov et al. (2023) — *Compositional Semantic Parsing with Large Language Models* | Semantic Parsing | Structured output generation from LLMs |
| 19 | 2026-07-21 | Mirchandani et al. (2023) — *Large Language Models as General Pattern Machines* | LLMs on ARC | **Direct relevance.** LLMs on ARC sequence tasks |
| 20 | 2026-07-23 | Xu et al. (2023) — *LLMs and the Abstraction and Reasoning Corpus* | ARC + LLMs | Survey of LLM performance on ARC; why they fail |
| 21 | 2026-07-25 | Greenblatt (2023) — *Getting 50% (SoTA) on ARC-AGI with GPT-4* | ARC SoTA | State-of-the-art LLM approach to ARC |
| 22 | 2026-07-27 | Butt et al. (2024) — *CodeARC: Evaluating LLMs on Abstraction and Reasoning* | ARC + Code | LLMs writing code to solve ARC (your approach) |
| 23 | 2026-07-29 | **CHECKPOINT 4** — ARC-Programmer v2 (with NeuralSolver context) evaluated; score ≥ 48% | — | — |
| 23 | 2026-07-29 | Parisotto et al. (2017) — *Neuro-Symbolic Program Synthesis* | Neurosymbolic | Neural + symbolic program synthesis |
| 24 | 2026-07-31 | Odena et al. (2021) — *BUSTLE: Bottom-Up Program Synthesis Through Learning-Guided Exploration* | Program Synthesis | Bottom-up synthesis: complementary to LLM top-down |

---

## ⭐ Priority Papers (read first if time is short)

1. **Ellis et al. (2021)** — *DreamCoder*: The gold standard for ARC program synthesis
2. **Greenblatt (2023)** — *Getting 50% on ARC-AGI with GPT-4*: Your primary benchmark to beat
3. **Xu et al. (2023)** — *LLMs and ARC*: Why current LLMs fail and what would fix it
4. **Austin et al. (2021)** — *Program Synthesis with LLMs*: Your methodological foundation

---

## ARC-Specific Program Synthesis Notes

From reading this literature, the key insight for ARC program synthesis is:
- **The search problem is huge**: there are exponentially many programs; need good guidance
- **LLMs provide good search guidance**: they generate plausible programs based on examples
- **Execution feedback is critical**: the model must see whether its programs *work*
- **DSL quality matters enormously**: a well-designed DSL covers 80%+ of ARC tasks; a poor one covers 20%

This means your ARC-DSL design (Project 3) deserves more time than the LLM training itself.

---

## Checkpoint Criteria

| Checkpoint | Date | Pass Criteria |
|---|---|---|
| Checkpoint 1 | 2026-06-25 | GPT-2 model running on ARC data; generates plausible (if wrong) programs |
| Checkpoint 2 | 2026-07-07 | ARC-DSL designed; 10 operations implemented; 20 ARC tasks solvable |
| Checkpoint 3 | 2026-07-17 | Fine-tuned model evaluating on ARC-AGI-1; score > 30% |
| Checkpoint 4 | 2026-07-29 | Full ARC-Programmer pipeline complete; score ≥ 48% |
| Phase Complete | 2026-08-09 | All 24 papers read; workshop paper draft started |
