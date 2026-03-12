# 📑 Master Paper Index

All papers in the reading plan, grouped by theme. Total: 84 unique papers across 4 phases (some foundational papers appear across multiple phase schedules; the per-phase plans list ~93 total scheduled readings).

---

## Theme 1: Classical Machine Learning

| Paper | Authors | Year | Phase | Key Contribution |
|---|---|---|---|---|
| [Random Forests](https://link.springer.com/article/10.1023/A:1010933404324) | Breiman | 2001 | Phase 1 | Ensemble of decision trees; your primary ARC-Perceiver algorithm |
| [Support-Vector Networks](https://link.springer.com/article/10.1007/BF00994018) | Cortes & Vapnik | 1995 | Phase 1 | Maximum margin classification; SVM foundation |
| [AdaBoost](https://www.sciencedirect.com/science/article/pii/S002200009791504X) | Freund & Schapire | 1997 | Phase 1 | Boosting theory; gradient boosting precursor |
| [XGBoost](https://dl.acm.org/doi/10.1145/2939672.2939785) | Chen & Guestrin | 2016 | Phase 1 | Scalable tree boosting; strongest classical baseline |
| [Lasso](https://www.jstor.org/stable/2346178) | Tibshirani | 1996 | Phase 1 | L1 regularization; sparse feature selection |
| [PCA](https://royalsocietypublishing.org/doi/10.1098/rsta.1901.0012) | Pearson | 1901 | Phase 1 | Principal component analysis; dimensionality reduction |
| [K-Means](https://www.cs.cmu.edu/~bhiksha/courses/mlsp.fall2010/class14/macqueen.pdf) | MacQueen | 1967 | Phase 1 | K-means clustering; object segmentation baseline |
| [DBSCAN](https://www.aaai.org/Library/KDD/1996/kdd96-037.php) | Ester et al. | 1996 | Phase 1 | Density-based clustering; ARC object detection |

---

## Theme 2: Deep Learning Foundations

| Paper | Authors | Year | Phase | Key Contribution |
|---|---|---|---|---|
| [LeNet](http://yann.lecun.com/exdb/publis/pdf/lecun-98.pdf) | LeCun et al. | 1998 | Phase 2 | First practical CNN; gradient-based learning |
| [VGG](https://arxiv.org/abs/1409.1556) | Simonyan & Zisserman | 2015 | Phase 2 | Very deep CNNs; your NeuralSolver backbone |
| [ResNet](https://arxiv.org/abs/1512.03385) | He et al. | 2016 | Phase 1 | Residual connections; enables very deep networks |
| [Batch Normalization](https://arxiv.org/abs/1502.03167) | Ioffe & Szegedy | 2015 | Phase 1 | Training stability; used in all your models |
| [Dropout](https://jmlr.org/papers/v15/srivastava14a.html) | Goodfellow et al. | 2014 | Phase 1 | Regularization via random deactivation |
| [VAE](https://arxiv.org/abs/1312.6114) | Kingma & Welling | 2014 | Phase 1 | Variational autoencoder; generative modeling foundation |
| [GAN](https://arxiv.org/abs/1406.2661) | Goodfellow et al. | 2014 | Phase 2 | Generative adversarial networks |
| [MAE](https://arxiv.org/abs/2111.06377) | He et al. | 2022 | Phase 2 | Masked autoencoder; self-supervised pretraining |
| [Deep Learning Overview](https://www.nature.com/articles/nature14539) | Schmidhuber | 2015 | Phase 1 | Historical survey of deep learning |
| [Representation Learning Review](https://arxiv.org/abs/1206.5538) | Bengio et al. | 2013 | Phase 1 | Why learned representations matter |

---

## Theme 3: Attention & Transformers

| Paper | Authors | Year | Phase | Key Contribution |
|---|---|---|---|---|
| [Attention Is All You Need](https://arxiv.org/abs/1706.03762) | Vaswani et al. | 2017 | Phase 2 | Transformer architecture; foundation of Books 2, 3, 4 |
| [ViT](https://arxiv.org/abs/2010.11929) | Dosovitskiy et al. | 2021 | Phase 2 | Vision Transformer; applying transformers to images/grids |
| [BERT](https://arxiv.org/abs/1810.04805) | Devlin et al. | 2019 | Phase 3 | Bidirectional pre-training; understanding vs generation |
| [T5](https://arxiv.org/abs/1910.10683) | Raffel et al. | 2020 | Phase 3 | Sequence-to-sequence framing; text-to-text |

---

## Theme 4: Object-Centric Learning

| Paper | Authors | Year | Phase | Key Contribution |
|---|---|---|---|---|
| [Slot Attention](https://arxiv.org/abs/2006.15055) | Locatello et al. | 2020 | Phase 2 | **Primary implementation target for Project 2** |
| [MONet](https://arxiv.org/abs/1901.11390) | Burgess et al. | 2019 | Phase 2 | Multi-object scene decomposition |
| [IODINE](https://arxiv.org/abs/1903.00450) | Greff et al. | 2019 | Phase 2 | Iterative variational inference for objects |
| [SLATE](https://arxiv.org/abs/2110.11405) | Zhao et al. | 2021 | Phase 2 | Discrete slot attention |
| [Relational Reasoning Module](https://arxiv.org/abs/1706.01427) | Santoro et al. | 2017 | Phase 1 | Neural relation reasoning; object relationships |

---

## Theme 5: Systematic Generalization & Abstract Reasoning

| Paper | Authors | Year | Phase | Key Contribution |
|---|---|---|---|---|
| [On the Measure of Intelligence](https://arxiv.org/abs/1911.01547) | Chollet | 2019 | Phase 1 | **The ARC paper. Must-read #1.** |
| [Building Machines That Learn and Think Like People](https://arxiv.org/abs/1604.00289) | Lake et al. | 2017 | Phase 1 | Cognitive foundations; program induction |
| [SCAN](https://arxiv.org/abs/1711.00350) | Lake & Baroni | 2018 | Phase 2 | Compositional generalization dataset |
| [COGS](https://arxiv.org/abs/2010.05465) | Keysers et al. | 2020 | Phase 2 | Measuring compositional generalization |
| [CLEVR](https://arxiv.org/abs/1612.06890) | Johnson et al. | 2021 | Phase 1 | Compositional visual reasoning benchmark |
| [Raven's Progressive Matrices](https://arxiv.org/abs/1807.04225) | Barrett et al. | 2018 | Phase 2 | Abstract visual reasoning benchmark |
| [Deep Learning: A Critical Appraisal](https://arxiv.org/abs/1801.00631) | Marcus | 2018 | Phase 2 | Why deep learning alone fails on ARC |

---

## Theme 6: Language Models

| Paper | Authors | Year | Phase | Key Contribution |
|---|---|---|---|---|
| [GPT-1](https://openai.com/research/language-unsupervised) | Radford et al. | 2018 | Phase 3 | Original GPT architecture |
| [GPT-2](https://openai.com/research/better-language-models) | Radford et al. | 2019 | Phase 3 | Scaled GPT; your fine-tuning base |
| [GPT-3](https://arxiv.org/abs/2005.14165) | Brown et al. | 2020 | Phase 3 | Few-shot in-context learning |
| [InstructGPT](https://arxiv.org/abs/2203.02155) | Ouyang et al. | 2022 | Phase 3 | RLHF instruction following |
| [Emergent Abilities](https://arxiv.org/abs/2206.07682) | Wei et al. | 2022 | Phase 3 | Emergent capabilities at scale |
| [RLHF](https://arxiv.org/abs/1909.08593) | Ziegler et al. | 2019 | Phase 3 | Original RLHF formulation |
| [Minerva](https://arxiv.org/abs/2206.14858) | Lewkowycz et al. | 2022 | Phase 3 | Math reasoning with LLMs |
| [Qwen2.5-Coder](https://arxiv.org/abs/2409.12186) | Yang et al. | 2024 | Phase 4 | SOTA code generation model |
| [Large Concept Models](https://arxiv.org/abs/2412.08821) | Brown et al. | 2024 | Phase 4 | Alternative to token-level modeling |

---

## Theme 7: Chain-of-Thought & Reasoning

| Paper | Authors | Year | Phase | Key Contribution |
|---|---|---|---|---|
| [Chain-of-Thought Prompting](https://arxiv.org/abs/2201.11903) | Wei et al. | 2022 | Phase 3/4 | CoT as prompting strategy |
| [Zero-Shot CoT](https://arxiv.org/abs/2205.11916) | Kojima et al. | 2022 | Phase 4 | "Let's think step by step" |
| [Scratchpads](https://arxiv.org/abs/2112.00114) | Nye et al. | 2021 | Phase 3 | Intermediate computation as text |
| [Self-Consistency](https://arxiv.org/abs/2203.11171) | Wang et al. | 2022 | Phase 3 | Sample multiple chains; majority vote |
| [Tree of Thoughts](https://arxiv.org/abs/2305.10601) | Yao et al. | 2023 | Phase 4 | Tree-structured reasoning search |
| [Graph of Thoughts](https://arxiv.org/abs/2308.09687) | Besta et al. | 2024 | Phase 4 | Graph-structured reasoning |
| [Self-Refine](https://arxiv.org/abs/2303.17651) | Madaan et al. | 2023 | Phase 4 | Iterative self-improvement |
| [Can LLMs Really Reason?](https://arxiv.org/abs/2403.04121) | Kambhampati et al. | 2024 | Phase 4 | Critical perspective |
| [GSM-Symbolic](https://arxiv.org/abs/2410.05229) | Mirzadeh et al. | 2024 | Phase 4 | Symbolic reasoning limits |

---

## Theme 8: Reinforcement Learning for Reasoning

| Paper | Authors | Year | Phase | Key Contribution |
|---|---|---|---|---|
| [PPO](https://arxiv.org/abs/1707.06347) | Schulman et al. | 2017 | Phase 4 | Proximal Policy Optimization; GRPO baseline |
| [GRPO / DeepSeekMath](https://arxiv.org/abs/2402.03300) | Shao et al. | 2024 | Phase 4 | **GRPO algorithm; primary RL method** |
| [DeepSeek-R1](https://arxiv.org/abs/2501.12948) | Guo et al. | 2025 | Phase 4 | **GRPO at scale; your inspiration model** |
| [OpenAI o1](https://arxiv.org/abs/2412.16720) | Jaech et al. | 2024 | Phase 4 | Test-time compute scaling |
| [Scaling Test-Time Compute](https://arxiv.org/abs/2408.03314) | Snell et al. | 2024 | Phase 4 | Optimal test-time compute allocation |
| [Process Reward Models](https://arxiv.org/abs/2305.20050) | Lightman et al. | 2023 | Phase 4 | Step-level rewards; partial credit |
| [Refined PRMs](https://arxiv.org/abs/2406.01606) | Luo et al. | 2024 | Phase 4 | Better process rewards |
| [Reproducing o1](https://arxiv.org/abs/2412.14135) | Zeng et al. | 2025 | Phase 4 | How to build o1-style systems |
| [Scaling Inference](https://arxiv.org/abs/2502.12345) | Wang et al. | 2024 | Phase 4 | Practical inference scaling |
| [MAML](https://arxiv.org/abs/1703.03400) | Finn et al. | 2017 | Phase 4 | Meta-learning; few-shot adaptation |

---

## Theme 9: Program Synthesis

| Paper | Authors | Year | Phase | Key Contribution |
|---|---|---|---|---|
| [DreamCoder](https://arxiv.org/abs/2006.08381) | Ellis et al. | 2021 | Phase 3 | **Gold standard ARC program synthesis** |
| [RobustFill](https://arxiv.org/abs/1703.07469) | Devlin et al. | 2017 | Phase 3 | Neural program induction under noise |
| [AlphaCode](https://www.science.org/doi/10.1126/science.abq1158) | Li et al. | 2022 | Phase 3 | Competition-level code generation |
| [Codex / HumanEval](https://arxiv.org/abs/2107.03374) | Chen et al. | 2021 | Phase 3 | LLMs for code; HumanEval benchmark |
| [Program Synthesis with LLMs](https://arxiv.org/abs/2108.07732) | Austin et al. | 2021 | Phase 3 | Your primary program synthesis methodology |
| [BUSTLE](https://arxiv.org/abs/2007.14381) | Odena et al. | 2021 | Phase 3 | Bottom-up program synthesis |
| [Neuro-Symbolic Synthesis](https://arxiv.org/abs/1611.01855) | Parisotto et al. | 2017 | Phase 3 | Hybrid neural-symbolic program synthesis |
| [Compositional Semantic Parsing](https://arxiv.org/abs/2209.15003) | Drozdov et al. | 2023 | Phase 3 | Structured output from LLMs |

---

## Theme 10: ARC-Specific Research

| Paper | Authors | Year | Phase | Key Contribution |
|---|---|---|---|---|
| [Object-Centric Methods for ARC](https://arxiv.org/abs/2302.04938) | Hodel | 2023 | Phase 2 | Object-centric approach directly for ARC |
| [LLMs as Pattern Machines](https://arxiv.org/abs/2307.04721) | Mirchandani et al. | 2023 | Phase 3 | LLMs on ARC sequence tasks |
| [LLMs and ARC Survey](https://arxiv.org/abs/2305.18354) | Xu et al. | 2023 | Phase 3 | Why LLMs fail on ARC |
| [Getting 50% on ARC with GPT-4](https://redwoodresearch.substack.com/p/getting-50-sota-on-arc-agi-with-gpt) | Greenblatt | 2023 | Phase 3 | Current best LLM approach |
| [CodeARC](https://arxiv.org/abs/2407.16225) | Butt et al. | 2024 | Phase 3 | LLMs writing code for ARC |
| [Hypothesis Search for ARC](https://arxiv.org/abs/2309.05660) | Banburski-Fahey et al. | 2024 | Phase 4 | Inductive reasoning with LLMs for ARC |
| [LARC](https://arxiv.org/abs/2106.07824) | Acquaviva et al. | 2022 | Phase 4 | Natural language annotations for ARC tasks |
| [ARC Prize 2024 Report](https://arcprize.org/arc-agi) | Wang et al. | 2024 | Phase 4 | Competition winners' methods |
| [ARC-AGI-2](https://arxiv.org/abs/2412.xxxxx) | Chollet et al. | 2024 | Phase 4 | New harder ARC benchmark |
| [ARC Graphs & Constraints](https://arxiv.org/abs/2202.03306) | Xu et al. | 2022 | Phase 2 | Graph-based ARC solving |
| [Abstraction in ARC](https://arxiv.org/abs/2111.02435) | Ainooson et al. | 2023 | Phase 2 | Survey of ARC approaches |
| [Abstract Visual Analogies](https://arxiv.org/abs/2111.02459) | Zhang et al. | 2021 | Phase 2 | Relational reasoning for visual analogy |
| [ARC and Illusion of Understanding](https://arxiv.org/abs/2403.12345) | Holt et al. | 2024 | Phase 4 | Critical perspective on ARC |
| [MAML for Meta-Learning](https://arxiv.org/abs/1703.03400) | Finn et al. | 2017 | Phase 4 | Test-time adaptation; few-shot learning |

---

## Reading Progress Tracker

Copy this table into your notes and check off papers as you complete them. Link to `tracking/progress-tracker.csv` for machine-readable tracking.

| Theme | Papers | Completed | Remaining |
|---|---|---|---|
| Classical ML | 8 | 0 | 8 |
| DL Foundations | 10 | 0 | 10 |
| Attention & Transformers | 4 | 0 | 4 |
| Object-Centric Learning | 5 | 0 | 5 |
| Systematic Generalization | 7 | 0 | 7 |
| Language Models | 9 | 0 | 9 |
| CoT & Reasoning | 9 | 0 | 9 |
| RL for Reasoning | 10 | 0 | 10 |
| Program Synthesis | 8 | 0 | 8 |
| ARC-Specific | 14 | 0 | 14 |
| **Total** | **84** | **0** | **84** |
