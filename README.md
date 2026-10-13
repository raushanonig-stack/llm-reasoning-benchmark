# 🧪 Frontier LLM Reasoning Benchmark

## 📌 Problem Statement
As large language models (LLMs) become more advanced, their ability to perform complex logical reasoning and strictly follow negative constraints (e.g., "do not include explanations") remains inconsistent. This project provides a programmatic evaluation harness to objectively benchmark AI models against curated datasets.

## ⚙️ Methodology
This project uses a custom Python evaluation script (`evaluator.py`) to grade AI outputs. Instead of manual verification, it automates the testing pipeline:
1. **Data Ingestion:** Loads challenge prompts and ground-truth answers from a structured JSON dataset.
2. **Execution:** Simulates LLM responses and routes them to category-specific evaluation functions.
3. **Validation Rules:** Applies multiple grading logic such as:
   - `exact_match`: For mathematical and chemical kinetics reasoning.
   - `instruction_following`: Regex and string parsing to detect forbidden elements (like code comments).

## 📊 Evaluation Criteria
Models are scored on a strict Pass/Fail basis for each benchmark challenge. The final output generates a percentage-based reliability score, helping identify specific edge cases where the AI hallucinates or fails to follow instructions.

## 🚀 How to Run
```bash
python evaluator.py
