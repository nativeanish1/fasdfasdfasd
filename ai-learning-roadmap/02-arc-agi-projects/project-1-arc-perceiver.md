# Project 1: ARC-Perceiver

**Book:** *Hands-On ML with Scikit-Learn and PyTorch* (Book 1)  
**Timeline:** April 2026 (after completing Book 1 in March 2026)  
**ARC-AGI-1 Target Score:** 15–25%  
**ARC-AGI-2 Target Score:** 5–10%  
**Research Output:** Technical report — "Classical ML Baselines for ARC-AGI"

---

## Motivation

Before throwing transformers and RL at ARC, you must understand what the *easiest* ARC tasks look like and build a principled perception layer. Many ARC tasks are solvable with hand-crafted rules + a few classical ML components. ARC-Perceiver does this rigorously, using everything in Book 1.

The Perceiver is not a toy baseline — it becomes the **feature extraction backbone** for all subsequent projects.

---

## Core Insight

ARC tasks are fundamentally about:
1. **Perceiving structure** in input/output grid pairs (colors, objects, spatial relationships)
2. **Hypothesizing a rule** that maps input to output
3. **Applying that rule** to a test input

Book 1 gives you: SVMs, decision trees, random forests, feature engineering, and PyTorch for basic networks. These are exactly the tools for steps 1 and 2.

---

## What You Build

### 1. Grid Feature Extractor (`perceiver/features.py`)

A hand-engineered feature extractor that produces, for each ARC input/output pair:

| Feature Group | Features |
|---|---|
| **Color statistics** | color histogram, unique colors, color ratios |
| **Spatial structure** | bounding boxes per color, object count, grid dimensions |
| **Symmetry** | horizontal/vertical/rotational symmetry flags |
| **Relationships** | color co-occurrence, spatial adjacency matrix |
| **Transformation clues** | size ratio input/output, color remapping candidates |
| **Pattern detection** | tiling patterns, repeating motifs |

### 2. Rule Template Library (`perceiver/rule_templates.py`)

A library of ~50 parameterized ARC rule templates (covering ~30–40% of ARC tasks):

- Color substitution rules: `map_color(A → B)`
- Geometric transformations: `rotate_90`, `flip_horizontal`, `flip_vertical`
- Object operations: `extract_largest_object`, `fill_enclosed_regions`
- Grid operations: `tile_pattern`, `crop_to_bounding_box`
- Counting rules: `count_objects_of_color(C)`
- Conditional rules: `if size(obj) == N then color(obj) = C`

### 3. Rule Classifier (`perceiver/classifier.py`)

A **Random Forest classifier** trained to predict, given a set of input/output pair features, which rule template category applies. Training data comes from ARC-AGI-1 training tasks (400 tasks × 2–5 examples each).

```python
# Conceptual pipeline
features = extract_features(input_grid, output_grid)
rule_probabilities = rf_classifier.predict_proba(features)
top_k_rules = select_top_k_templates(rule_probabilities, k=5)
solution = apply_best_matching_rule(top_k_rules, test_input)
```

### 4. Evaluation Harness (`eval/arc_eval.py`)

The official ARC evaluation protocol:
- A task is "solved" only if the predicted output exactly matches the expected output (pixel-perfect)
- Score = fraction of solved evaluation tasks

---

## Technical Specifications

| Component | Choice | Justification |
|---|---|---|
| Feature extraction | Hand-crafted + scikit-learn | Book 1's core strength; fast and interpretable |
| Classifier | Random Forest (n=500 trees) | Handles high-dimensional sparse features well |
| Rule templates | Python functions on NumPy arrays | Exact, deterministic execution |
| Hyperparameter tuning | Grid search with CV | Book 1 covers this thoroughly |
| Data augmentation | Color permutation, reflection | Increases effective training set 8–16× |

---

## Training Protocol

1. **Feature extraction:** Compute features for all 400 × (avg 3 examples) = ~1200 input/output pairs from the ARC training set.
2. **Rule labeling:** Manually label each training task with its dominant rule category (one-time effort, ~10 hours).
3. **Classifier training:** Train Random Forest on labeled features.
4. **Template search:** For each test task, extract features → predict rule category → enumerate matching templates → apply and score against training examples → submit best.
5. **Evaluation:** Run official ARC evaluation; record score.

---

## Expected Challenges

| Challenge | Mitigation |
|---|---|
| Tasks requiring compositional rules | Implement rule chaining: try combinations of 2 rules |
| Noisy feature extraction | Careful feature normalization and selection |
| Many tasks not covered by templates | Accept ~60–75% of tasks unsolved; focus on what *is* covered |
| Exact pixel match requirement | Implement exhaustive template search over parameters |

---

## Deliverables

- [ ] `perceiver/features.py` — complete feature extractor
- [ ] `perceiver/rule_templates.py` — ≥50 rule templates
- [ ] `perceiver/classifier.py` — trained Random Forest
- [ ] `eval/arc_eval.py` — evaluation harness
- [ ] ARC-AGI-1 evaluation score ≥ 15%
- [ ] Technical report documenting methodology and results
- [ ] Open-source release with reproducibility instructions

---

## Connection to Next Project

ARC-Perceiver's output — the `PerceptionBundle` (features + rule candidates + symmetry flags) — becomes the **input preprocessing layer** for ARC-NeuralSolver (Project 2). Project 2 will use deep learning to *refine* the perception rather than replace it, treating Project 1 as a strong prior.
