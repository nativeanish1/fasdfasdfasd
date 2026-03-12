# Portfolio Guidelines

How to present your work so that it creates maximum hiring signal. Most people build good projects and then present them poorly. Don't be that person.

---

## Core Principle

Your portfolio has one job: **make a hiring manager or researcher confident that you can do serious ML work independently.**

Every decision about presentation should serve this goal.

---

## GitHub Repository Standards

Every project should be its own top-level GitHub repository (not a folder in a monorepo, but linked to the `arc-system` umbrella repo). Each repo must have:

### Required Elements

1. **README.md** — the most important document in the repo

   A high-quality README must include:

   ```
   # Project Name
   
   One-sentence description.
   
   ## Results
   
   | Metric | Score |
   |---|---|
   | ARC-AGI-1 evaluation | 23% |
   | ARC-AGI-1 (ablation: no Slot Attention) | 14% |
   
   [Link to paper / technical report]
   
   ## How It Works
   
   3–5 sentence non-technical explanation.
   
   Followed by: technical architecture diagram.
   
   ## How to Run
   
   ```bash
   pip install -r requirements.txt
   python eval/arc_eval.py --model checkpoints/best.pt
   ```
   
   ## Results Reproducibility
   
   Seed: 42. Hardware: A100 80GB. Training time: 3 days.
   ```

2. **Quantitative results table** — always first, always prominent. If your ARC score is modest, include it honestly with context.

3. **Architecture diagram** — even ASCII art is better than nothing; `architecture-overview.md` already has one.

4. **Reproducibility information** — seed, hardware, training time, exact commands.

5. **Model weights on HuggingFace** — link in README. This is standard in the research community.

6. **Demo** — Gradio or Streamlit app. Even a simple "input a grid, see the prediction" demo makes your work 10× more accessible.

---

## What to Never Do

- **Don't hide low scores.** A 23% ARC score with a principled analysis of why is more impressive than a high score with no analysis.
- **Don't list every tool/library you used.** Focus on what you built, not what you imported.
- **Don't use jargon without context.** If a non-technical recruiter reads your README, they should understand what you built in 30 seconds.
- **Don't leave code without comments.** Key algorithms (Slot Attention, GRPO training loop) should have 2–3 line comments explaining what's happening.
- **Don't mix 4 projects in one repo** — separate repos are findable, forkable, and credible.

---

## Presenting Research Work

### If You Have a Paper (Even Workshop)

- List it in a "Publications" or "Research" section of your LinkedIn and resume
- Format: "Title, Authors (you + any collaborators), Workshop/Conference Name, Year"
- Include the OpenReview or arXiv link
- Even a rejected paper with a review attached shows you went through the peer review process

### If You Don't Have a Paper (Yet)

- Write a technical blog post for each project. Length: 1500–3000 words.
- Post on Substack, Towards Data Science (Medium), or your personal site
- Include: motivation, architecture, results, what didn't work, what you'd try next
- Share in ARC Discord, ML Twitter, relevant subreddits

**A detailed blog post is 70% as credible as a workshop paper to most hiring managers.** It's also much faster to produce.

---

## LinkedIn Profile Structure

After this roadmap, your LinkedIn should look like:

```
Headline: ML Research Engineer | ARC-AGI Benchmark Research | LLM Program Synthesis

About:
  Building research-grade AI systems. Currently focused on abstract reasoning 
  and program synthesis for ARC-AGI. Completed [N]-paper reading curriculum 
  across classical ML, deep learning, LLMs, and reasoning models.

Featured:
  [Link to best GitHub project]
  [Link to best blog post]
  [Link to HuggingFace model]

Experience:
  [Any relevant experience]

Projects:
  ARC-Reasoner — ARC-AGI-1: 55%; ARC-AGI-2: 30%
  ARC-Programmer — ARC-AGI-1: 48%; program synthesis with fine-tuned LLM
  ARC-NeuralSolver — ARC-AGI-1: 30%; object-centric deep learning
  ARC-Perceiver — ARC-AGI-1: 20%; classical ML baseline

Publications:
  [Workshop paper citations if any]
```

---

## Resume One-Pager

For ML Engineer applications, keep your resume to 1 page. Key sections:

### Skills Section
List only what you can confidently discuss in an interview:
- **Languages:** Python, (add only if true: C++, Julia)
- **Frameworks:** PyTorch, scikit-learn, HuggingFace Transformers
- **Tools:** Weights & Biases, Docker, Git, CUDA (if applicable)
- **Methods:** Transformer/LLM architectures, RL (GRPO/PPO), object-centric learning, program synthesis

Do NOT list: every framework you've imported, tools you used once, certifications from online courses.

### Projects Section (Prioritize Over Experience)

Each project entry: 2–3 bullet points. Format:
```
ARC-Reasoner (Project 4)
• Built reasoning model (117M params) with GRPO training; achieved 55% on ARC-AGI-1
• Implemented test-time search (Best-of-N + iterative refinement); 8% score improvement
• Submitted to [Workshop Name] workshop at NeurIPS/ICLR 2026/2027
```

The ARC-AGI benchmark score is your most powerful resume bullet. It's specific, verifiable, and impressive to anyone who knows the benchmark.

---

## HuggingFace Profile

Upload to HuggingFace:
- All model checkpoints (even intermediate ones)
- Custom datasets (your synthetic DSL programs, ARC representations)
- Model cards with clear documentation

A HuggingFace presence with multiple uploads signals you're a practitioner who contributes to the community — not just a student doing assignments.

---

## Demo Quality Standards

For each project that has a demo (target: Projects 2 and 3 at minimum):

| Element | Standard |
|---|---|
| Input | User can upload or select an ARC task |
| Visualization | Show input/output grids and predicted output side-by-side |
| Explanation | Show the model's reasoning (chain-of-thought for Project 4) or the generated program (Project 3) |
| Performance | Response time < 10 seconds; loading indicator if slower |
| Mobile-friendly | Basic responsiveness for phone viewing |

Use Gradio (`gr.Interface`) — it takes 50 lines to build a functional demo and deploys for free on HuggingFace Spaces.

---

## The 10-Minute Technical Interview Talk

Practice describing your work in 10 minutes. Structure:
1. **(1 min)** What is ARC-AGI and why is it hard?
2. **(2 min)** What is your approach? (the 4-project arc)
3. **(4 min)** Deep dive on Project 4 (your most impressive work)
4. **(2 min)** Results and comparison to prior work
5. **(1 min)** What's next?

The ability to deliver this clearly — without rambling, without jargon, without over-qualifying — is what separates candidates who get offers from candidates who get feedback like "interesting background but not quite what we're looking for."

Record yourself doing this. Watch it back. It will be terrible the first time. Redo it until it's not.
