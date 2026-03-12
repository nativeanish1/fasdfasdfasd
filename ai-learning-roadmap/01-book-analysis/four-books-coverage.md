# 📚 Four-Book Coverage Analysis

Detailed breakdown of what each book contributes to your ARC-AGI journey, followed by a combined coverage table with gap analysis.

---

## Book 1: *Hands-On Machine Learning with Scikit-Learn and PyTorch* (Géron)

**Completed:** October 2025  
**Relevance to ARC-AGI:** Provides the classical ML substrate — object recognition, rule learning, feature engineering, and ensemble methods that form the backbone of the ARC-Perceiver (Project 1).

| Skill Area | Depth | ARC-AGI Relevance |
|---|---|---|
| Classical ML (SVMs, Trees, Ensembles) | Deep | High — pattern/rule detection in ARC grids |
| Data pipelines & feature engineering | Deep | High — spatial feature extraction from grids |
| PyTorch fundamentals | Moderate | Medium — baseline model training |
| CNNs (basic) | Moderate | Medium — spatial structure in grid tasks |
| Dimensionality reduction (PCA, autoencoders) | Moderate | Medium — grid abstraction |
| MLOps & deployment basics | Intro | Low — useful for benchmarking infra |

**Key Takeaways for ARC:**
- Decision trees and random forests can learn rule-like patterns from ARC training examples
- Feature engineering (color histograms, spatial relationships, symmetry detection) is core to solving ARC programmatically
- PyTorch gives you the training loop foundation you'll use in all subsequent projects

---

## Book 2: *Deep Learning with Python, 3rd Edition* (Chollet)

**Target completion:** May 2026  
**Relevance to ARC-AGI:** Chollet is the *creator* of ARC. His deep learning intuitions about systematic generalization, compositionality, and the limits of deep learning directly inform how to build ARC-NeuralSolver (Project 2).

| Skill Area | Depth | ARC-AGI Relevance |
|---|---|---|
| CNNs (full architecture) | Deep | Very High — spatial processing of ARC grids |
| Attention mechanisms | Strong | Very High — relational reasoning between grid cells |
| Transformer basics | Moderate | High — sequence modeling of ARC rules |
| Generative models (VAEs, GANs) | Moderate | Medium — hypothesis generation |
| DL theory & generalization | Deep | Very High — Chollet's views on ARC directly apply |
| Keras/JAX proficiency | Deep | Medium — framework fluency |

**Key Takeaways for ARC:**
- Object-centric representations and convolutional feature maps are how humans decompose ARC grids
- Attention lets the model focus on which parts of the input/output pair are structurally related
- Chollet explicitly argues in *DL with Python* that deep learning alone is insufficient for ARC — understanding *why* informs your hybrid approach

---

## Book 3: *Build an LLM from Scratch* (Raschka)

**Target completion:** July 2026  
**Relevance to ARC-AGI:** Enables ARC-Programmer (Project 3) — using an LLM to generate Python or DSL programs that solve ARC tasks by program synthesis.

| Skill Area | Depth | ARC-AGI Relevance |
|---|---|---|
| Transformer architecture (GPT-style) | Deep | Very High — LLM backbone for program synthesis |
| Tokenization (BPE) | Strong | High — tokenizing grid representations |
| Pretraining from scratch | Deep | High — pretraining on ARC-like data |
| Instruction fine-tuning (SFT) | Strong | Very High — teaching the LLM ARC solving strategies |
| RLHF / Preference tuning | Intro | Medium — baseline for Project 4 |
| Attention: full implementation | Deep | Very High — architectural understanding |

**Key Takeaways for ARC:**
- GPT-2-scale models (117M–345M params) can be fine-tuned to generate programs in a Domain-Specific Language (DSL) for ARC
- The tokenization of 2D grid data into sequences requires careful design — this book gives you the tools to do it
- Understanding every matrix multiply means you can modify the architecture (e.g., 2D positional encodings)

---

## Book 4: *Build a Reasoning Model from Scratch* (Raschka — MEAP/Upcoming)

**Target completion:** September 2026  
**Relevance to ARC-AGI:** The final integration layer — ARC-Reasoner (Project 4) adds chain-of-thought, RL-based self-improvement, and test-time compute to the system built in Projects 1–3.

| Skill Area | Depth | ARC-AGI Relevance |
|---|---|---|
| Chain-of-thought reasoning | Deep (expected) | Very High — step-by-step ARC solving |
| GRPO / RL for reasoning | Strong (expected) | Very High — reward shaping from ARC correctness |
| Test-time compute / search | Moderate (expected) | Very High — best-of-N sampling for ARC |
| Reward modeling | Strong (expected) | High — partial credit for near-correct solutions |
| Distillation of reasoning | Moderate (expected) | Medium — compression for inference speed |

**Key Takeaways for ARC:**
- ARC requires multi-step hypothesis formation — exactly what reasoning models learn
- GRPO with ARC correctness as reward is a principled way to improve the model's ARC score
- Test-time search (beam search over reasoning chains) can dramatically increase ARC accuracy

---

## 🧮 Combined Coverage Table

| Skill Area | Book 1 | Book 2 | Book 3 | Book 4 | Total Coverage |
|---|---|---|---|---|---|
| Classical ML fundamentals | ████████████ | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | 100% |
| Feature engineering | ████████████ | ██████░░░░░░ | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | 100% |
| Deep learning theory | ████░░░░░░░░ | ████████████ | ████░░░░░░░░ | ░░░░░░░░░░░░ | 100% |
| CNNs / Vision | ████████░░░░ | ████████████ | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | 85% |
| Transformers / Attention | ████░░░░░░░░ | ████████░░░░ | ████████████ | ░░░░░░░░░░░░ | 100% |
| LLM pretraining | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ████████████ | ░░░░░░░░░░░░ | 100% |
| Fine-tuning (SFT) | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ████████████ | ██████░░░░░░ | 90% |
| Chain-of-thought reasoning | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ████░░░░░░░░ | ████████████ | 80% |
| RL for LLMs (GRPO/PPO) | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ████░░░░░░░░ | ████████████ | 80% |
| Test-time compute / search | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ████████████ | 65% |
| Program synthesis | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ████████░░░░ | ████████████ | 70% |
| RAG / Retrieval | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ████░░░░░░░░ | ░░░░░░░░░░░░ | 20% ← **GAP** |
| Multimodal (vision+language) | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | 10% ← **GAP** |
| Efficient inference/serving | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ████░░░░░░░░ | 20% ← **GAP** |
| Agents / Tool use | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | 10% ← **GAP** |
| Object-centric learning | ░░░░░░░░░░░░ | ████████░░░░ | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | 50% ← **GAP** |
| Program induction / DSL | ░░░░░░░░░░░░ | ░░░░░░░░░░░░ | ████████░░░░ | ████████████ | 65% ← partial |

---

## 🔍 Critical Gaps for ARC-AGI

The following areas are **underserved by the 4-book curriculum** but are important for ARC-AGI. Each gap maps to papers in the reading plan.

| Gap Area | Why It Matters for ARC | Mitigation |
|---|---|---|
| **Domain-Specific Languages (DSLs)** | ARC winners use hand-crafted DSLs; programs over grids outperform neural approaches alone | Papers: DreamCoder, ARC-DSL; implemented in Project 3 |
| **Object-Centric Learning** | ARC requires parsing grids into objects with properties | Papers: MONet, Slot Attention; implemented in Project 2 |
| **Neurosymbolic Integration** | Combining symbolic rules with neural pattern matching | Papers: AlphaCode, Neural Program Synthesis; Project 3 & 4 |
| **Abstract Visual Reasoning** | Matrix reasoning analogues | Papers: Raven's Progressive Matrices studies; Project 1 & 2 |
| **Test-Time Adaptation** | ARC tasks are novel; the model must adapt from 2–5 examples | Papers: MAML, Meta-learning; covered partially in Book 4 |
| **Systematic Generalization** | The core of what makes ARC hard | Papers: SCAN, COGS, Compositional generalization; cross-cutting |

---

## 📌 Overall Verdict

After completing all 4 books, you will have **~85% of the foundational and intermediate knowledge** needed to do serious ARC-AGI research. The gaps are well-known in the field and can be addressed through targeted paper reading (see Phase 3 and 4 papers). The 4-project sequence is designed to close these gaps progressively — you will discover the gaps organically as you build.
