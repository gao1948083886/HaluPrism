# 🧩 HaluPrism Benchmark

This repository contains the dataset **HaluPrism**, which accompanies our ICCBR 2026 submission:

> **_HaluPrism: A Fine-Grained Benchmark for Decomposing Hallucinations via a Causal Prism_**

---

## 📖 Overview

**HaluPrism** is a fine-grained benchmark designed to **analyze, decompose, and evaluate hallucinations** in large language models (LLMs).  
It provides curated examples across multiple domains and hallucination categories, helping researchers perform nuanced factuality and reasoning error analysis.

📄 *This dataset corresponds to our ICASSP 2025 submission. The full paper and accompanying code will be released upon official acceptance.*

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
