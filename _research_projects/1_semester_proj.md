---
title: "Reverse Knowledge Distillation and Task Arithmetic for Generalist Vision Models"
excerpt: "This project explores how to integrate specialized knowledge into generalist vision models using reverse knowledge distillation and task arithmetic, enabling scalable and privacy-preserving multi-task learning."
collection: research_projects
permalink: /publication/2026-03-11-reverse-knowledge-distillation
paperurl: '../../files/Semester_Project_LTS4-3.pdf'
share: false
related: false
---

## Problem Statement & Motivation

Modern machine learning systems face a fundamental trade-off:

- **Specialized models** achieve high performance on specific tasks but lack scalability and are often constrained by **data privacy**  
- **Generalist models** are flexible but fail to capture **task-specific knowledge**  

A key challenge is:

> How can we transfer knowledge from specialized models into a generalist model **without access to labeled data**?

This project addresses this problem using **reverse knowledge distillation** and **task arithmetic**, enabling scalable and privacy-preserving multi-task learning.


## Our Approach

We design a unified framework combining **unsupervised distillation**, **model merging**, and **representation analysis**.

### 1. Reverse Knowledge Distillation (RKD)

Unlike standard distillation, we transfer knowledge:

- From **specialized teacher models → generalist student model**

Key innovation:

- Use **feature-level contrastive learning** instead of label-based supervision  
- Enables training with **unlabeled data only**

The student learns to align its embeddings with those of the teacher using:

- Contrastive loss (positive = same input, negative = different inputs)  
- Optional KL-based distillation  

📌 Key advantage:  
Preserves **data privacy** while enabling effective knowledge transfer.


### 2. Task Arithmetic for Model Merging

We represent each task as a **task vector**:

- Difference between fine-tuned model and base model  
- Captures task-specific knowledge  

We then:

- Combine multiple task vectors into a single model  
- Create a **multi-task generalist model without retraining**

📌 Insight:  
Task arithmetic provides a **lightweight alternative to full fine-tuning**.


### 3. Experimental Setup

- **Models**:
  - Vision Transformers (ViT-B16, ViT-B32, ViT-L14)  
  - CNNs (ResNet50, ConvNeXt)  

- **Datasets (8 tasks)**:
  - MNIST, SVHN, DTD, GTSRB, SUN397, RESISC45, EuroSAT, Cars  

- **Training strategies**:
  - Fine-tuning  
  - Reverse distillation  
  - Task vector merging  


### 4. Representation Analysis

To understand knowledge transfer, we analyzed embeddings using:

- **t-SNE** → visual cluster separation  
- **Cosine similarity** → parameter alignment  
- **CKA (Centered Kernel Alignment)** → representation similarity  

These tools provide interpretability of how knowledge is transferred across models.


## Key Results

- **Fine-tuning achieves the highest performance** across all tasks  
- **Reverse distillation effectively transfers knowledge without labels**  
- **Task arithmetic enables multi-task generalization** with reduced cost  

Key findings:

- Distillation works best when  
  → **Teacher and student architectures are similar**

- Task arithmetic  
  → Achieves **intermediate performance** between pretrained and fully fine-tuned models  

- Representation alignment (CKA, cosine similarity)  
  → Directly correlates with transfer quality  


## Contributions

- **Privacy-preserving reverse distillation framework**  
- **Feature-based contrastive knowledge transfer** without labels  
- **Task arithmetic for scalable model merging**  
- Insights into:
  - Embedding geometry  
  - Architecture compatibility  
  - Knowledge transfer dynamics  


## Discussion & Insights

### Strengths
- No labeled data required  
- Scalable to multiple tasks  
- Strong interpretability through representation analysis  

### Limitations
- Sensitive to architecture similarity  
- Variability in task merging performance  
- Limited performance on complex datasets  

### Future Work
- Learn optimal weighting of task vectors  
- Improve cross-architecture distillation  
- Explore hierarchical or graph-based representations  
- Deploy in real-world multi-domain systems  


## Defense & Supervision

- **Institution**: EPFL – School of Computer and Communication Sciences  
- **Lab**: Signal Processing Laboratory (LTS4)  
- **Professor**: Prof. Pascal Frossard  
- **Supervisors**: Ortal Senouf & Nikolaos Dimitriadis  


## Resources

- **PDF**: [Full Report](/files/Semester_Project_LTS4.pdf)


> *This project demonstrates how knowledge distillation and task arithmetic can bridge the gap between specialized and generalist models, enabling scalable, privacy-preserving multi-task learning.*
