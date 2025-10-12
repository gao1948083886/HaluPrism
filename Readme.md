# 🧩 HaluPrism Dataset

> **A Fine-Grained Benchmark for Decomposing and Evaluating Model Hallucinations**

This repository contains the cleaned dataset **HaluPrism**, which accompanies our ICASSP 2025 submission:

> **_HALUPRISM: A FINE-GRAINED BENCHMARK FOR DECOMPOSING HALLUCINATIONS THROUGH A CAUSAL PRISM_**

---

## 📖 Overview

**HaluPrism** is a fine-grained benchmark designed to **analyze, decompose, and evaluate hallucinations** in large language models (LLMs).  
It provides curated examples across multiple domains and hallucination categories, helping researchers perform nuanced factuality and reasoning error analysis.

This dataset is a **simplified, cleaned version** of the *Sampled Seeds (18k)* subset described in the paper.

---

## 📂 Dataset Information

- **File:** `HaluPrism.json`  
- **Format:** JSON list of structured entries  
- **Total Samples:** 18,000  
- **Annotation Types:** Six fine-grained hallucination categories + Non-hallucinated responses  

### **Field Descriptions**

| Field | Description |
|-------|--------------|
| `id` | Numeric identifier for each sample |
| `question` | Input prompt or user query |
| `response` | Model-generated output |
| `category` | Fine-grained hallucination type (e.g., *Factual Fabrication*, *Logical Inconsistency*) |
| `metadata` | Contextual information such as `domain` and `generation_type` |

---

## 🧠 Example Samples

```json
[
  {
    "id": 4,
    "question": "With an interest in archaeology, this female monarch has had a long and successful reign in a country where popular support for the royal family is high. She is the Queen of which country?",
    "response": "The Queen is Elizabeth II of the United Kingdom.",
    "category": "No Hallucination",
    "metadata": {
      "domain": "Humanities",
      "generation_type": "Non-adversarial"
    }
  },
  {
    "id": 14,
    "question": "What precise geodetic reference systems were implemented by the Soviet Venera 9 lander in 1975 to quantify surface elevations on Venus?",
    "response": "The Venera 9 lander employed a modified version of the Pulkovo 1942 geodetic reference system...",
    "category": "Factual Fabrication",
    "metadata": {
      "domain": "Technology",
      "generation_type": "Adversarial"
    }
  }
]
