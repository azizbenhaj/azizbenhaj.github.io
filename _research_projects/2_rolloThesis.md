---
title: "Learning Similarity for Curve-Based Retrieval in Industrial Tool Design"
excerpt: "This thesis develops a metric learning framework for fine-grained geometric similarity retrieval of laser machining tools, enabling efficient reuse of designs and accelerating industrial engineering workflows."
collection: research_projects
permalink: /publication/2026-03-11-curve-similarity-retrieval
share: false
related: false
---

## Problem Statement & Motivation

In industrial tool design, engineers frequently rely on **existing tools as references** when creating new ones. Identifying geometrically and functionally similar tools enables the reuse of validated manufacturing strategies, reduces redundant designs, and accelerates engineering workflows.

However, current approaches rely heavily on:
- **Manual expert knowledge**, which is time-consuming and difficult to scale  
- **Predefined templates**, which fail to cover the full design space  
- **Heuristic similarity measures**, lacking objective evaluation and consistency  

Additionally, prior systems focus on **whole-tool representations**, which overlook the **fine-grained geometric structure** of tools—particularly the curves that define their shape and function.

This thesis addresses these limitations by shifting toward **curve-level similarity learning**, enabling precise, data-driven retrieval of relevant reference tools.


## Industrial Context

This work was conducted in collaboration with **Rollomatic SA**, a Swiss company specializing in high-precision CNC machines for tool grinding and laser machining.

- Founded in 1989 and headquartered in Le Landeron, Switzerland  
- Serves industries including automotive, aerospace, medical, and electronics  
- Operates globally with advanced production and automation facilities  

The project aims to **integrate intelligent retrieval directly into the tool design workflow**, assisting engineers in selecting relevant reference tools efficiently.


## Our Approach

The proposed system introduces a **complete pipeline for curve-based similarity learning**, combining dataset construction, representation learning, and ranking-based evaluation.

### 1. Dataset Construction & Annotation
- Built a **similarity-aware dataset of tool curves**  
- Leveraged **expert annotations** to capture real industrial perception of similarity  
- Used embedding-based preselection (Top-K) to reduce annotation effort  

### 2. Curve Representations
Evaluated multiple representation strategies:
- **Classical shape descriptors**  
- **Pretrained deep embeddings** (e.g., ResNet50, ConvNeXt, ViT)  
- Analysis showed limited transferability of generic vision models to geometric similarity  

### 3. Metric Learning for Similarity
Introduced learning-based approaches to align embeddings with similarity annotations:
- **Binary contrastive learning** for similarity classification  
- **Rank-aware learning (regression & triplet-based)** to preserve graded similarity  

Key insight:  
→ **Ordinal similarity matters** — preserving ranking relationships is crucial for retrieval tasks.

### 4. Evaluation Framework
Adopted a **multi-perspective evaluation strategy**:
- Clustering metrics: ARI, NMI, Silhouette, DBI  
- Binary classification metrics  
- Ranking metrics: **nDCG, gMRR**  
- Visualization tools (e.g., t-SNE) for embedding analysis  


## Key Results

- **Rank-aware metric learning significantly improves retrieval quality** over binary contrastive methods  
- **L2-based regression losses** outperform cosine-based formulations in stability and ranking performance  
- Pretrained deep models provide **only marginal gains** without task-specific adaptation  
- Data augmentation yields **limited benefits** in this specialized geometric domain  

Overall, the results highlight that:
> Designing learning objectives aligned with **graded similarity** is essential for effective retrieval.


## Contributions

- **First curve-level similarity learning framework** for industrial tool retrieval  
- **High-quality expert-annotated dataset** reflecting real-world similarity perception  
- **Comprehensive evaluation methodology** combining clustering, classification, and ranking metrics  
- **Demonstration of rank-aware metric learning** for preserving ordinal similarity  
- **Practical pipeline** ready for integration into industrial design workflows  


## Discussion & Insights

### Strengths
- End-to-end pipeline from data to deployment-ready retrieval  
- Strong integration of **domain expertise** in annotation  
- Deep analysis of **embedding geometry and loss functions**  
- Clear empirical validation of rank-aware learning advantages  

### Limitations
- Moderate dataset size limits generalization  
- Annotation distribution imbalance due to subjective rankings  
- Loss of **tool-level context** when focusing solely on curves  
- Limited impact of augmentation strategies  

### Future Work
- Hybrid **curve + tool-level representations** (hierarchical or graph-based)  
- Improved ranking objectives and sampling strategies  
- Large-scale annotation via **active learning**  
- Deployment of an **interactive retrieval system** for real-world validation  


## Defense & Supervision

- **Institution**: EPFL – School of Computer and Communication Sciences  
- **Industry Partner**: Rollomatic SA  
- **Supervisors**: Prof. *Jean-Philippe Thiran*
- **Defense Date**: March 2026  


## Resources

- **PDF**: [Full Thesis PDF](/files/rollomatic_master_thesis_report.pdf)  
- **Slides**: [Presentation Slides](/files/rollomatic_thesis_presentation.pdf)


> *This work bridges vision–language modeling and remote sensing, paving the way for structured, interpretable, and fine-grained retrieval systems in complex geospatial domains.*
