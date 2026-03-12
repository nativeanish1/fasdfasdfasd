# Phase 2 Paper Reading Plan: Deep Learning & Object-Centric Vision

**Book Pairing:** Book 2 — *Deep Learning with Python, 3rd Edition* (Chollet)  
**Timeline:** April 19 – June 14, 2026 (8 weeks, ~24 papers)  
**Reading Pace:** 1 paper per 2 days  
**Project Context:** ARC-NeuralSolver (Project 2)

---

## Goals for This Phase

By the end of Phase 2, you will be able to:
- Implement and extend the core architectures in Book 2 from scratch
- Understand object-centric learning deeply (Slot Attention, spatial attention, scene decomposition)
- Know the theoretical basis for why deep learning succeeds and fails on systematic generalization tasks like ARC
- Have implemented at least one Slot Attention variant in PyTorch

---

## Paper Schedule

| # | Date | Paper | Theme | Why Read |
|---|---|---|---|---|
| 1 | 2026-04-19 | LeCun et al. (1998) — *Gradient-Based Learning Applied to Document Recognition* (LeNet) | CNNs | Foundation of all CNNs; Book 2 Chapter 8 |
| 2 | 2026-04-21 | Simonyan & Zisserman (2015) — *Very Deep Convolutional Networks for Large-Scale Image Recognition* (VGG) | CNNs | Architecture you'll implement in NeuralSolver |
| 3 | 2026-04-23 | Vaswani et al. (2017) — *Attention Is All You Need* | Transformers | **Core paper.** Foundation of Books 2, 3, 4. |
| 4 | 2026-04-25 | Locatello et al. (2020) — *Object-Centric Learning with Slot Attention* | Object-Centric | **Core paper.** Direct implementation target for Project 2 |
| 5 | 2026-04-27 | Burgess et al. (2019) — *MONet: Unsupervised Scene Decomposition and Representation* | Object-Centric | Alternative to Slot Attention; compare approaches |
| 6 | 2026-04-29 | Greff et al. (2019) — *Multi-Object Representation Learning with Iterative Variational Inference* (IODINE) | Object-Centric | Theoretical foundations of object-centric learning |
| 7 | 2026-05-01 | **CHECKPOINT 1** — Implement Slot Attention in PyTorch; test on CLEVR | — | Practical validation |
| 7 | 2026-05-01 | Zhao et al. (2021) — *SLATE: Unsupervised Scene Representation Using Discrete Slot Attention* | Object-Centric | Improved Slot Attention with discrete representations |
| 8 | 2026-05-03 | Goodfellow et al. (2014) — *Generative Adversarial Nets* | Generative Models | Book 2's GAN chapter theoretical foundation |
| 9 | 2026-05-05 | Ho et al. (2020) — *Denoising Diffusion Probabilistic Models* | Generative Models | State-of-the-art generative modeling (beyond GANs) |
| 10 | 2026-05-07 | Marcus (2018) — *Deep Learning: A Critical Appraisal* | Critiques of DL | Why DL struggles on ARC; what systematic generalization requires |
| 11 | 2026-05-09 | Lake & Baroni (2018) — *Generalization without Systematicity* (SCAN) | Systematic Generalization | The compositional generalization problem ARC tests |
| 12 | 2026-05-11 | Keysers et al. (2020) — *Measuring Compositional Generalization* (COGS) | Systematic Generalization | How to measure systematic generalization objectively |
| 13 | 2026-05-13 | **CHECKPOINT 2** — Write mini-paper (2 pages) on "Why CNNs fail on ARC" | — | Synthesis exercise |
| 13 | 2026-05-13 | Kim et al. (2021) — *Unsupervised Visual Representation Learning by Online Constrained k-Means* (ContraCode) | Representations | Self-supervised visual representations |
| 14 | 2026-05-15 | He et al. (2022) — *Masked Autoencoders Are Scalable Vision Learners* (MAE) | Self-Supervised | Pre-training strategy for your NeuralSolver backbone |
| 15 | 2026-05-17 | Dosovitskiy et al. (2021) — *An Image is Worth 16×16 Words* (ViT) | Vision Transformers | Applying transformers directly to grids (no CNN needed) |
| 16 | 2026-05-19 | Zhang et al. (2021) — *Relational Reasoning for Abstract Visual Analogies* | ARC-Adjacent | Abstract visual reasoning using relational networks |
| 17 | 2026-05-21 | Wang et al. (2021) — *Emergent Symbols through Binding in External Memory* | Program Induction | Symbolic abstraction in neural networks |
| 18 | 2026-05-23 | Barrett et al. (2018) — *Measuring Abstract Reasoning in Neural Networks* (Raven's) | Abstract Reasoning | Abstract visual reasoning benchmarks related to ARC |
| 19 | 2026-05-25 | **CHECKPOINT 3** — ARC-NeuralSolver architecture finalized; begin implementation | — | — |
| 19 | 2026-05-25 | Mitchell et al. (2021) — *Abstraction and Analogy-Making in ARC Tasks* | ARC-Specific | Direct analysis of human reasoning on ARC tasks |
| 20 | 2026-05-27 | Xu et al. (2022) — *Graphs, Constraints, and Search for the Abstraction and Reasoning Corpus* | ARC-Specific | Graph-based ARC solving (alternative to neural) |
| 21 | 2026-05-29 | Ainooson et al. (2023) — *An Approach for Solving Tasks in the ARC Dataset* | ARC-Specific | Survey of ARC solving approaches |
| 22 | 2026-05-31 | Hodel (2023) — *Addressing the Abstraction and Reasoning Corpus via Object-Centric Methods* | ARC-Specific | Object-centric methods for ARC (highly relevant) |
| 23 | 2026-06-02 | Kolev et al. (2020) — *Probabilistic Contrastive Principal Component Analysis* | Representations | Alternative representation learning |
| 24 | 2026-06-04 | **CHECKPOINT 4** — NeuralSolver first version running; record ARC-AGI-1 baseline score | — | — |

---

## ⭐ Priority Papers (read first if time is short)

1. **Vaswani et al. (2017)** — *Attention Is All You Need*: Foundation of everything
2. **Locatello et al. (2020)** — *Slot Attention*: Your direct implementation target
3. **Marcus (2018)** — *Deep Learning: A Critical Appraisal*: Understand why you need more than DL
4. **Hodel (2023)** — *Object-Centric Methods for ARC*: Most relevant to Project 2

---

## Implementation Exercises

For Phase 2, reading must be paired with implementation:

| Week | Paper | Implementation Task |
|---|---|---|
| Week 1 | Vaswani (2017) | Implement multi-head attention from scratch (Book 2 + paper) |
| Week 2 | Locatello (2020) | Implement Slot Attention on CLEVR dataset |
| Week 3 | Dosovitskiy (2021) | Implement ViT on ARC grid data |
| Week 4 | Hodel (2023) | Apply object-centric approach to 20 ARC tasks; record accuracy |

---

## Checkpoint Criteria

| Checkpoint | Date | Pass Criteria |
|---|---|---|
| Checkpoint 1 | 2026-05-01 | Slot Attention implemented; runs on CLEVR |
| Checkpoint 2 | 2026-05-13 | 2-page mini-paper written; architectural decision made |
| Checkpoint 3 | 2026-05-25 | NeuralSolver architecture decided; PyTorch skeleton written |
| Checkpoint 4 | 2026-06-04 | NeuralSolver v1 running; baseline ARC score recorded |
| Phase Complete | 2026-06-14 | All 24 papers read; NeuralSolver v2 (with Project 1 integration) complete |
