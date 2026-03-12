# Phase 1 Paper Reading Plan: Classical ML & Foundations

**Book Pairing:** Book 1 — *Hands-On ML with Scikit-Learn and PyTorch*  
**Timeline:** March 11 – April 18, 2026 (6 weeks, ~18 papers)  
**Reading Pace:** 1 paper per 2 days  
**Project Context:** ARC-Perceiver (Project 1)

---

## Goals for This Phase

By the end of Phase 1, you will be able to:
- Explain the theoretical basis for the algorithms in Book 1 (not just use them)
- Read empirical ML papers and understand their experimental methodology
- Identify which classical ML methods apply to ARC-style grid reasoning tasks
- Write a technical report in ML paper style

---

## Paper Schedule

| # | Date | Paper | Theme | Why Read |
|---|---|---|---|---|
| 1 | 2026-03-11 | Breiman (2001) — *Random Forests* | Ensembles | Foundation of Book 1's strongest classifier |
| 2 | 2026-03-13 | Cortes & Vapnik (1995) — *Support-Vector Networks* | SVMs | Theory behind Book 1's SVM chapter |
| 3 | 2026-03-15 | Freund & Schapire (1997) — *A Decision-Theoretic Generalization of On-Line Learning* (AdaBoost) | Boosting | Theoretical basis for gradient boosting |
| 4 | 2026-03-17 | Chen & Guestrin (2016) — *XGBoost: A Scalable Tree Boosting System* | Boosting | Most competitive classical ML baseline |
| 5 | 2026-03-19 | Tibshirani (1996) — *Regression Shrinkage and Selection via the Lasso* | Regularization | Core regularization theory |
| 6 | 2026-03-21 | Pearson (1901) — *On Lines and Planes of Closest Fit* (PCA) | Dimensionality Reduction | Foundation of PCA from Book 1 |
| 7 | 2026-03-23 | MacQueen (1967) — *Some Methods for Classification and Analysis of Multivariate Observations* (K-Means) | Clustering | K-Means theory |
| 8 | 2026-03-25 | Ester et al. (1996) — *A Density-Based Algorithm for Discovering Clusters* (DBSCAN) | Clustering | Object segmentation in ARC grids |
| 9 | 2026-03-27 | **CHECKPOINT 1** — Review papers 1–8; write 1-page summary | — | — |
| 9 | 2026-03-27 | Kingma & Welling (2014) — *Auto-Encoding Variational Bayes* (VAE) | Generative Models | Latent space learning; intro to generative modeling |
| 10 | 2026-03-29 | Bengio et al. (2013) — *Representation Learning: A Review and New Perspectives* | Representations | Why learned features beat hand-crafted features |
| 11 | 2026-03-31 | Schmidhuber (2015) — *Deep Learning in Neural Networks: An Overview* | History | Historical context and big picture |
| 12 | 2026-04-02 | Goodfellow et al. (2014) — *Dropout: A Simple Way to Prevent Neural Networks from Overfitting* | Regularization | Book 1 regularization techniques theorized |
| 13 | 2026-04-04 | He et al. (2016) — *Deep Residual Learning for Image Recognition* (ResNet) | Architecture | Foundation for all modern vision networks |
| 14 | 2026-04-06 | Ioffe & Szegedy (2015) — *Batch Normalization* | Training | Book 1/2 training stability technique |
| 15 | 2026-04-08 | **CHECKPOINT 2** — Review papers 9–14; update ARC-Perceiver design based on readings | — | — |
| 15 | 2026-04-08 | Johnson et al. (2021) — *CLEVR: A Diagnostic Dataset for Compositional Language and Elementary Visual Reasoning* | Structured Reasoning | ARC-related: compositional visual reasoning dataset |
| 16 | 2026-04-10 | Santoro et al. (2017) — *A Simple Neural Network Module for Relational Reasoning* | Relational Reasoning | Object relationships in grid tasks |
| 17 | 2026-04-12 | Lake et al. (2017) — *Building Machines That Learn and Think Like People* | Cognitive Science | Chollet's intellectual foundation; core ARC motivation |
| 18 | 2026-04-14 | Chollet (2019) — *On the Measure of Intelligence* | ARC Theory | **Must-read.** The original ARC paper. |

---

## ⭐ Priority Papers (read first if time is short)

1. **Chollet (2019)** — *On the Measure of Intelligence*: This defines ARC and your entire roadmap
2. **Lake et al. (2017)** — *Building Machines That Learn and Think Like People*: The cognitive science foundation
3. **Breiman (2001)** — *Random Forests*: Your primary ARC-Perceiver algorithm
4. **He et al. (2016)** — *ResNet*: The architecture backbone you'll use in Projects 2–4

---

## Reading Strategy

For each paper, write a **2-paragraph summary** in your notes:
1. **What it claims** — the main contribution in 2–3 sentences
2. **What it means for your projects** — how you might apply or build on this

This 2-paragraph format takes ~30 minutes per paper and produces a personal literature review over time.

---

## Checkpoint Criteria

| Checkpoint | Date | Pass Criteria |
|---|---|---|
| Checkpoint 1 | 2026-03-27 | Papers 1–8 read; 2-paragraph summaries written |
| Checkpoint 2 | 2026-04-08 | Papers 9–14 read; ARC-Perceiver design influenced by at least 3 papers |
| Phase Complete | 2026-04-18 | All 18 papers read; ARC-Perceiver code started |
