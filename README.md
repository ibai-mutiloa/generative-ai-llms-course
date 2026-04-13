# Generative AI with Large Language Models — Course Labs

My lab notebooks for the [DeepLearning.AI — Generative AI with Large Language Models](https://www.coursera.org/learn/generative-ai-with-llms) course on Coursera.

Each lab builds on the previous one, progressively improving a FLAN-T5 model for dialogue summarization — from zero-shot prompting to instruction fine-tuning to RLHF-based detoxification.

## Repository Structure

```
├── Week_1_Lab/
│   └── Lab_1_summarize_dialogue.ipynb
├── Week_2_Lab/
│   └── Lab_2_fine_tune_generative_ai_model.ipynb
├── Week_3_Lab/
│   └── Lab_3_fine_tune_model_to_detoxify_summaries.ipynb
└── README.md
```

---

## Lab 1 — Prompt Engineering & Zero/Few-Shot Inference

**Goal:** Explore how prompt design affects FLAN-T5 output quality for dialogue summarization, without modifying any model weights.

**Key concepts:**
- Zero-shot, one-shot and few-shot inference
- In-context learning
- Prompt templates
- Baseline ROUGE evaluation

**Stack:** `transformers`, `datasets` (knkarthick/dialogsum), FLAN-T5

---

## Lab 2 — Instruction Fine-Tuning + PEFT/LoRA

**Goal:** Improve summarization quality by fine-tuning FLAN-T5 on the DialogSum dataset, first with full fine-tuning and then with parameter-efficient fine-tuning (PEFT/LoRA).

**Key concepts:**
- Instruction fine-tuning with prompt-completion pairs
- Full fine-tuning vs PEFT — memory and performance trade-offs
- LoRA (Low-Rank Adaptation) — only ~1.4% of parameters trained
- ROUGE metrics for quantitative evaluation (ROUGE-1, ROUGE-2, ROUGE-L)

**Results summary:**

| Method | ROUGE-1 improvement | Trainable params |
|---|---|---|
| Base model (zero-shot) | baseline | — |
| Full fine-tuning | highest | 100% |
| PEFT/LoRA | near full FT | ~1.4% |

**Stack:** `transformers`, `peft`, `datasets`, `evaluate`, FLAN-T5, LoRA

---

## Lab 3 — Detoxification with RLHF + PPO

**Goal:** Reduce toxicity of the fine-tuned model's summaries using Reinforcement Learning from Human Feedback (RLHF) with Proximal Policy Optimization (PPO).

**Key concepts:**
- RLHF pipeline — reward model drives LLM weight updates
- PPO (Proximal Policy Optimization) with trust region
- KL divergence vs reference model to prevent reward hacking
- Hate speech classifier (Facebook RoBERTa) as reward model
- Value head for advantage estimation in PPO
- PEFT/LoRA maintained throughout — only adapters updated

**Architecture:**
```
Prompt → FLAN-T5 (LoRA) → Summary
                               ↓
              RoBERTa hate speech classifier
                               ↓
                   not_hate logit → reward scalar
                               ↓
              PPOTrainer updates LoRA adapters
              KL divergence keeps model stable
```

**Stack:** `transformers`, `peft`, `trl`, `evaluate`, `datasets`, FLAN-T5, RoBERTa

---

## Lab Progression

```
Lab 1 (Prompting)
    └─→ Lab 2 (Fine-tuning) ──── produces LoRA checkpoint
              └─→ Lab 3 (RLHF) ─ takes Lab 2 checkpoint as input
```

Each lab takes the output of the previous as its starting point, mirroring a realistic LLM development workflow: prompt → fine-tune → align.

---

## Setup

All labs require an `ml.m5.2xlarge` instance (8 vCPUs, 32 GiB RAM) or equivalent.

```bash
pip install torch transformers datasets evaluate peft trl
```

## Course

[Generative AI with Large Language Models](https://www.coursera.org/learn/generative-ai-with-llms) — DeepLearning.AI & AWS on Coursera
