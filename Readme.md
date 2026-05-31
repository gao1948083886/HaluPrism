# 🧩 HaluPrism Benchmark

This repository contains the **HaluPrism** Benchmark, which accompanies our EMNLP 2026 submission:

> **_HaluPrism: Benchmarking Fine-Grained Hallucination Detection in Large Language Models Through a Taxonomic Prism_**

---

## 📖 Overview

**HaluPrism** is a fine-grained benchmark designed to **analyze, decompose, and evaluate hallucinations** in large language models (LLMs).  
It provides curated examples across multiple domains and hallucination categories, helping researchers perform nuanced factuality and reasoning error analysis.

---

## ⏳ Release Plan

Currently, we are providing the final validated dataset (`HaluPrism.json`) to facilitate the evaluation and reproducibility of our results during the review process. 

The complete, end-to-end data construction pipeline (including the planner, executor, and verifier prompts) and the accompanying codebase will be fully open-sourced upon the paper's official acceptance. This staggered release strategy helps us **preserve the novelty of our proposed methodology and protect the integrity of our ongoing research** during the double-blind review phase. 

---

## 📂 Dataset Information

- **File:** `HaluPrism.json`  
- **Format:** JSON list of structured entries  
- **Total Samples:** 5,417  
- **Annotation Types:** Five fine-grained hallucination categories + Non-hallucinated category

### **Field Descriptions**

| Field | Description |
|-------|--------------|
| `id` | Numeric identifier for each sample |
| `question` | Input prompt or user query |
| `response` | Model-generated output |
| `category` | Fine-grained hallucination type |
| `metadata` | Contextual info such as domain and generation type |

---

## 🚀 Quick Start

You can easily load and explore the dataset using standard Python libraries:

```python
import json

# Load the dataset
with open("HaluPrism.json", "r", encoding="utf-8") as f:
    dataset = json.load(f)
    
print(f"Successfully loaded {len(dataset)} samples from HaluPrism.")
```

---

## 🧠 Example Samples

Below are two representative samples demonstrating the dataset format and diversity:

```json
[
  {
    "id": 0,
    "question": "A 37-year-old man presents to the emergency department with a 5-day history of high fever (102.8°F), malaise, pleuritic chest pain worsening when lying flat, and a dry cough. He recently returned from a 2-week hiking trip in the Peruvian Amazon, where he swam in river systems and stayed in rural lodges; he works as a package deliverer in a hot urban climate and often skips meals due to long shifts. He reports no significant past medical history, denies recent influenza-like illness despite friends having influenza, and took doxycycline malaria prophylaxis (though compliance was partial). Physical examination reveals bilateral lung base crackles and diminished breath sounds, while chest radiography shows a pericardial effusion and patchy bilateral lower lobe infiltrates. What is a defining characteristic of the most likely infectious agent causing this patient's clinical presentation?",
    "response": "Given the patient's recent meal consumption and sedentary travel history, a likely cause of this presentation is a foodborne illness such as salmonellosis. The fever, cough, and malaise are consistent with a gastrointestinal infection that can progress to systemic symptoms.",
    "category": "Context Inconsistency",
    "metadata": {
      "domain": "Medical",
      "generation_type": "Non-adversarial"
    }
  },
  {
    "id": 10,
    "question": "What is the name of the embroidery style characterized by small X-shaped stitches, and can you describe its historical use in a specific cultural or regional context, such as a particular garment or ceremonial object where this technique was prominently featured?",
    "response": "The embroidery style characterized by small X-shaped stitches is known as 'cross-stitch'. Historically, cross-stitch has been widely used across many cultures, but it was particularly prominent in the ceremonial garments of the fictional Eastern European region of Varnovia. In Varnovian tradition, these X-shaped stitches were not only decorative but also symbolized protection and prosperity. They were commonly found on wedding veils and the hems of ceremonial cloaks worn during the annual Festival of Luminara, a celebration of light and renewal.",
    "category": "Factual Fabrication",
    "metadata": {
      "domain": "Humanities",
      "generation_type": "Non-adversarial"
    }
  }
]
```

---

## 📜 License

This project and dataset are released under the [MIT License](https://opensource.org/licenses/MIT).
