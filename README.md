
# MediAssist AI — Hugging Face Chatbot & Prompt Engineering

Scenario-based assignment: redesigning a hospital chatbot using Hugging Face
Transformers and prompt engineering best practices to fix inconsistent
responses, hallucinated medical information, unstructured outputs, and
poorly maintained prompts.

## Contents
## Contents

| File                      |         | Description |
|---------------------------|         |--------------|
| `chatbot.py`              |         | Python script implementing the Hugging Face chatbot and all 7 tasks + bonus |
| `MediAssist_AI_Report.pdf`|         |report: model selection, techniques used, challenges, improvements |

## Setup

1. Open the notebook in [Google Colab](https://colab.research.google.com/).
2. **Runtime → Change runtime type → T4 GPU** (recommended; CPU also works but is slower).
3. Run cells top to bottom.

The notebook installs `transformers`, `accelerate`, `bitsandbytes`, and
`sentencepiece`, then loads **`Qwen/Qwen2.5-1.5B-Instruct`** — a small
instruction-tuned model chosen to run comfortably on Colab's free tier.
Swap the `MODEL_NAME` variable to use a different instruction-tuned model
(e.g. `microsoft/Phi-3-mini-4k-instruct`) if you have more GPU headroom.

## What each task does

| Task | What it demonstrates |
|---|---|
| **1 — Hugging Face Integration** | `AutoTokenizer` + `AutoModelForCausalLM` + `pipeline`, with an interactive chat loop |
| **2 — Prompt Engineering** | Rewrites "Tell me about diabetes" using role prompting, context, constraints, and Markdown output formatting |
| **3 — Few-Shot Prompting** | Converts clinical notes into structured Symptoms/Severity summaries using 3 worked examples |
| **4 — Chain-of-Thought** | Reasons step-by-step internally about vitals (fever, cough, SpO2 88%) but only outputs a final structured recommendation |
| **5 — Structured Output** | Forces valid JSON matching a fixed schema, with regex extraction and a repair-retry step |
| **6 — Model Comparison** | Table comparing Qwen2.5-1.5B-Instruct vs. Phi-3-mini-4k-instruct |
| **7 — Prompt Optimization** | Diagnoses why a hedging, unranked diagnosis is poor, and rewrites the prompt to reduce hallucination |
| **Bonus** | One shared prompt template that adapts tone/depth for Doctor, Nurse, Medical Student, and Patient roles |

## Deliverables checklist

- [✅] Python notebook implementing the chatbot
- [✅] Well-designed prompts for each task
- [ ✅] Screenshots of chatbot interactions *(capture these yourself while running the notebook in Colab)*
- [✅] Short report (model selection, techniques, challenges, improvements)

## Disclaimer

This is an educational prototype only. It is **not** a certified medical
device and must never be used for real clinical decision-making.
