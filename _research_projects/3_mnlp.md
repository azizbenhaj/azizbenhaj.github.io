---
title: "LLM as a Teaching Assistant: Fine-Tuning Qwen for Multiple-Choice Question Answering"
excerpt: "This project explores adapting a lightweight open-source language model (Qwen1.5-0.5B) for multiple-choice question answering through preference optimization, supervised fine-tuning, and quantization, achieving significant improvements on the MMLU benchmark."
collection: research_projects
share: false
related: false
reporturl: "/files/MNLP_3rd_report.pdf"
---

## Problem Statement & Motivation

Large Language Models (LLMs) have strong potential to support education, but they often struggle with **multiple-choice question (MCQ) answering**, especially in scientific domains. 

Key challenges include:
- Lack of alignment with **educational evaluation formats**  
- Difficulty selecting **precise answers (A/B/C/D)** instead of generating long text  
- High **computational requirements**, limiting accessibility  

This project aims to develop a **lightweight, efficient LLM-based teaching assistant** capable of accurately answering MCQs while operating under **limited computational resources**.


## Our Approach

We adapt the **Qwen1.5 (0.5B)** model through a structured pipeline combining preference learning, supervised fine-tuning, and efficient inference techniques.

### 1. Preference Learning with Direct Preference Optimization (DPO)

- Generated **preference pairs** using multiple prompting strategies (e.g., impersonation, CoT, ReAct).
- Evaluated strategies and found **impersonation prompting** most effective.
- Applied:
  - Standard **DPO**
  - **Conservative DPO (cDPO)** to handle noisy labels  

📌 Key finding:  
DPO yielded **limited improvements**, mainly due to **noisy and inconsistent student-generated data**.

---

### 2. Supervised Fine-Tuning for MCQ

To specialize the model for MCQ tasks, we trained it using the **SciQ dataset** with two approaches:

- **Multiple Choice Prompting (MCP)**  
  → Predict answer by comparing probabilities of tokens (A, B, C, D)

- **Cloze Prompting (CP)**  
  → Reformulate as classification with one option at a time  

📌 Key result:  
- MCP outperformed CP on MMLU  
- Fine-tuning significantly improved performance over baseline  

---

### 3. Quantization for Efficient Inference

To reduce computational cost:
- Applied **4-bit quantization** using:
  - **GPTQ**
  - **AWQ**

📌 Outcome:
- ~**60% memory reduction**
- **Minimal performance degradation**
- GPTQ selected as the best trade-off  

---

## Evaluation & Benchmarks

- **Dataset**: MMLU (57 subjects across STEM and beyond)  
- **Metrics**: Accuracy across domains  
- **Baseline**: Original Qwen1.5 model  

Evaluation was conducted in a **zero-shot setting**, ensuring fair comparison.

---

## Results

- Fine-tuning improves overall accuracy from **~30% to ~37% on MMLU** :contentReference[oaicite:0]{index=0}  
- Strong gains across:
  - STEM  
  - Social sciences  
  - Humanities  

- **MCP fine-tuning achieves the best performance**
- Quantization preserves performance while improving efficiency  

📌 Key insight:  
> Task-specific fine-tuning is far more effective than preference optimization for MCQ tasks.

---

## Analysis & Insights

### What Worked
- **Supervised fine-tuning (MCP)** → largest performance gain  
- **Quantization** → efficient deployment without loss  
- Careful **prompt design** improves answer extraction  

### What Didn’t Work Well
- DPO provided **minimal gains** due to:
  - Noisy preference data  
  - Inconsistent labeling strategies  

- Advanced prompting constraints did **not improve accuracy**  

---

## Contributions

- Demonstrated that **small LLMs (0.5B)** can be effective for education tasks  
- Compared **DPO vs supervised fine-tuning** for MCQ alignment  
- Provided a **complete pipeline**:
  - Data generation  
  - Preference learning  
  - Task-specific fine-tuning  
  - Efficient deployment via quantization  

- Delivered practical insights on:
  - Token bias  
  - Prompt robustness  
  - Evaluation challenges in MCQ tasks  


## Challenges & Future Work

- Improve **preference dataset quality** with standardized generation  
- Explore **larger or domain-specialized models** (e.g., newer Qwen versions)  
- Integrate **explanations** instead of only answers  
- Extend to **multilingual and multimodal learning**  
- Develop safeguards against **misuse and bias**  


## Ethical Considerations

- Risk of **students over-relying on answers without understanding**  
- Potential **bias in training data**  
- Need for safeguards against **misuse in exams or sensitive topics**  

Future systems should incorporate:
- Explanation generation  
- Bias detection  
- Responsible usage constraints  


## Resources

- **Report**: [Full Report](/files/MNLP_3rd_report.pdf)

