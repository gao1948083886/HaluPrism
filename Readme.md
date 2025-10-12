# 🧩 HaluPrism Dataset

> **A Fine-Grained Benchmark for Decomposing and Evaluating Model Hallucinations**

This repository contains the dataset **HaluPrism**, which accompanies our ICASSP 2025 submission:

> **_HALUPRISM: A FINE-GRAINED BENCHMARK FOR DECOMPOSING HALLUCINATIONS THROUGH A CAUSAL PRISM_**

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
- **Annotation Types:** Five fine-grained hallucination categories + Non-hallucinated responses  

### **Field Descriptions**

| Field | Description |
|-------|--------------|----------|
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
    "id": 1,
    "question": "Analyze the financial implications of a stolen item using two distinct perspectives: first, as a corporate accountant applying GAAP principles, calculate and explain the monetary loss using a comparative table showing cost price vs. potential revenue; second, as a retail store manager in a conversational tone, describe the practical business impact while avoiding technical accounting jargon. Your response must include (1) a LaTeX-formatted equation demonstrating the profit margin calculation, (2) a bulleted list comparing theft scenarios with and without insurance, and (3) a metaphor involving a common household object to illustrate the concept of opportunity cost. The entire response must be under 200 words, written in third person, and explicitly reference the IRS Publication 535 without quoting it directly.",
    "response": "As a corporate accountant adhering to GAAP, the loss is calculated as cost price minus potential revenue: $\\text{Profit Margin} = \\frac{(\\text{Revenue} - \\text{Cost})}{\\text{Revenue}}$. A comparative table would show a negative margin for the stolen item. As a retail manager, losing inventory feels like missing a key ingredient from a recipe—your final dish still tastes okay, but something’s off. Without insurance, theft results in: • Unrecoverable cash flow; • Reduced stock availability; • Potential markdowns. With insurance, these risks are cushioned but not eliminated. The financial impact is best understood through IRS Publication 535, which guides businesses on deductible losses. Balancing these perspectives within a concise format proves challenging, yet the metaphor of a missing kitchen knife illustrates how opportunity cost silently hinders operational efficiency.",
    "category": "Instruction Inconsistency",
    "metadata": {
      "domain": "Economics",
      "generation_type": "Adversarial"
    }
  }
]
