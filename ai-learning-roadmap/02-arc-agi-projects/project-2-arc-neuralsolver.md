# Project 2: ARC-NeuralSolver

**Book:** *Deep Learning with Python, 3rd Edition* (Chollet) (Book 2)  
**Timeline:** June 2026 (after completing Book 2 in May 2026)  
**ARC-AGI-1 Target Score:** 30–42% (cumulative with Project 1)  
**ARC-AGI-2 Target Score:** 10–18% (cumulative)  
**Research Output:** Workshop paper — "Object-Centric Deep Learning for Abstract Visual Reasoning"

---

## Motivation

Chollet created ARC specifically to challenge systems that memorize statistical patterns. His book directly addresses the architectural requirements for systematic generalization. Project 2 takes his insights and operationalizes them with a deep learning system that:
1. Learns to **decompose ARC grids into objects**
2. Learns to **represent transformations as operations on objects**
3. Generalizes to novel transformations via **attention over object properties**

This is not a standard image classification problem. It is an object-centric, relational reasoning problem — exactly what Chollet argues deep learning *can* handle when designed carefully.

---

## Core Architecture

### Object-Centric Grid Encoder

Inspired by the Slot Attention mechanism (Locatello et al., 2020), the grid encoder decomposes each input grid into a set of "slots," where each slot represents one object.

```
Input ARC grid (H × W × C)
        │
        ▼
CNN Backbone (4 layers, 64 channels)
        │
        ▼
Spatial Feature Map (H/4 × W/4 × D)
        │
        ▼
Slot Attention (K=8 slots, D=128)
        │
        ▼
Object Representations [slot_1, ..., slot_K] — each a D-dim vector
```

### Transformation Reasoning Module

Given object representations from input and output grids (for each training example), the Transformation Reasoning Module uses cross-attention to produce a **transformation embedding**:

```
Input objects [I₁...Iₖ] + Output objects [O₁...Oₖ]
        │
        ▼
Cross-Attention Transformer (4 layers)
        │
        ▼
Transformation Embedding T (D=256)
        │
        ▼
Transformation Classifier (→ rule category from Project 1)
  +
Transformation Executor (→ predicted output grid)
```

### Output Grid Decoder

A convolutional decoder that takes:
- The transformation embedding T
- The test input's object representations

And generates the predicted output grid.

---

## Technical Specifications

| Component | Choice | Justification |
|---|---|---|
| Grid encoder | CNN (4 layers, 3×3 kernels) | Book 2 CNN expertise; spatial feature extraction |
| Object decomposition | Slot Attention (8 slots) | Object-centric learning; handles ARC's discrete objects |
| Transformation model | 4-layer Transformer | Book 2 attention mechanisms; relational reasoning |
| Output decoder | Transposed CNN | Symmetric to encoder; produces exact grid dimensions |
| Loss function | Cross-entropy per cell | Exact match optimization |
| Training data | Re-ARC (400 × 100 synthetic) | 40,000 training tasks; covers distribution |
| Optimizer | AdamW, lr=3e-4, cosine schedule | Standard DL practice from Book 2 |

---

## What You Build

### 1. Data Pipeline (`neuralsolver/data.py`)

- Load ARC-AGI JSON tasks into PyTorch datasets
- Implement Re-ARC augmentation: randomly regenerate ARC task instances using original generators
- Grid tokenization: each cell becomes a one-hot vector over 10 colors
- Padding: normalize all grids to 30×30 with a null-color padding token

### 2. CNN Backbone (`neuralsolver/model.py`)

- 4-layer convolutional network with batch normalization and ReLU
- Output: spatial feature map
- Inspired by VGG-style architecture from Book 2, Chapter 8

### 3. Slot Attention Module (`neuralsolver/object_centric.py`)

- Implement Slot Attention from scratch using Book 2's attention primitives
- Key operation: iteratively assign grid pixels to slots via competitive attention
- Output: K fixed-size slot vectors representing discovered objects

### 4. Transformer Reasoning Layers

- Cross-attention between input slots and output slots
- Self-attention over the combined slot set
- Produces a compact transformation representation

### 5. Training Script (`neuralsolver/train.py`)

- Multi-GPU support (via PyTorch DataParallel)
- Mixed precision training (torch.amp)
- Checkpoint saving every 1000 steps
- Validation on held-out ARC training tasks (80/20 split)

### 6. Integration with ARC-Perceiver

- Load PerceptionBundle from Project 1 as additional input features
- Concatenate classical features with neural features before the Transformer
- This hybrid approach improves over pure neural by ~5–8% on ARC-AGI-1

---

## Training Protocol

| Stage | Description | Duration |
|---|---|---|
| Stage 1: Pre-train on Re-ARC | Train full model on 40K synthetic tasks | ~3 days (single GPU) |
| Stage 2: Fine-tune on ARC-Train | Fine-tune on official 400 training tasks | ~4 hours |
| Stage 3: Test-time ensemble | Run model N times with different seeds; vote | At eval time |

---

## Expected Challenges

| Challenge | Mitigation |
|---|---|
| Slot Attention instability | Warm-up phase; gradient clipping at 1.0 |
| 400 training tasks is tiny | Rely on Re-ARC synthetic data; heavy augmentation |
| Object decomposition fails on complex tasks | Increase slots (K=8→16) for complex inputs |
| Output decoder produces blurry grids | Categorical cross-entropy loss (not MSE); sharp outputs |

---

## Deliverables

- [ ] `neuralsolver/` — complete model codebase
- [ ] Trained model checkpoint (reproducible with seed)
- [ ] Ablation study: CNN-only vs CNN+Attention vs CNN+Attention+Perceiver
- [ ] ARC-AGI-1 evaluation score ≥ 30%
- [ ] Workshop paper draft (4 pages): methodology + ablation results
- [ ] Public model weights on HuggingFace

---

## Connection to Next Project

ARC-NeuralSolver produces ranked transformation hypotheses and object-centric grid representations. ARC-Programmer (Project 3) takes these as context for **program synthesis**: the LLM is told "here are the objects detected and the top transformation hypotheses — generate a program that implements this transformation."
