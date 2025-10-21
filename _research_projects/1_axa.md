---
title: "Structured Representations for Fine-Grained Text-to-Image Retrieval in Remote Sensing"
excerpt: "This thesis introduces a multimodal framework for fine-grained text-to-image retrieval in remote sensing, combining global and structured representations through scene graphs and semantic region embeddings. It addresses the limitations of CLIP-style global embeddings by capturing spatial, semantic, and relational details critical for fine-grained reasoning."
collection: research_projects
permalink: /publication/2025-08-26-structured-representations
paperurl: '/files/Master_thesis_final_report.pdf'
share: false
related: false
---

## Problem Statement & Motivation

Traditional CLIP-based models represent both text and images as single vectors within a shared embedding space. While effective for generic retrieval, this approach fails to capture the **fine-grained spatial and semantic relationships** that characterize **remote sensing (RS) imagery**, such as object counts, arrangements, and contextual interactions.

Remote sensing datasets are often **visually repetitive and textually generic**, limiting retrieval quality and interpretability. For industries such as **insurance and environmental monitoring**, accurate retrieval requires a deeper, structured understanding of scenes.

This work addresses these challenges by introducing **structured, multimodal representations**—spanning vector, graph, and scene levels—to enhance cross-modal alignment and reasoning.


## Our Approach

The proposed framework integrates **graph-based** and **scene-based** representations on top of traditional vector embeddings, yielding a unified retrieval system capable of reasoning over object relations, attributes, and global semantics.

### 1. Fine-Grained Dataset Creation
- Generated **fine-grained captions** using large vision–language models (Gemini-2.5-flash).  
- Conducted human evaluations showing improved **semantic richness and diversity** over existing datasets (e.g., RSICD, NWPU, RSITMD).
- Released new benchmark-ready datasets for fine-grained RS retrieval tasks.

### 2. Structured Multimodal Representations
- **Image-to-Graph**: scene graph generation from RS images via VLM-based object, attribute, and relation extraction.
- **Text-to-Graph**: structured graph extraction from captions for relational grounding.
- **Scene Decomposition**: lightweight alternative to graphs—segmenting images and captions into semantically coherent regions.

### 3. Retrieval Framework
Implemented multiple cross-modal retrieval modes:
- **V2V** – CLIP-style global embedding matching.  
- **G2G / VG2VG** – graph-level and hybrid vector–graph matching using Graph Matching Networks (GMN).  
- **S2S / V2S / S2V** – scene-level retrieval as a cost-effective alternative requiring no graph construction.

## Key Results

- **VG2VG** (Hybrid Vector–Graph) achieves **+8.30% mean accuracy gain** over baselines.  
- **Scene-based matching** provides **+3.55% gain** with minimal computation—ideal for scalable deployment.  
- Human evaluations confirm **stronger grounding and interpretability** for fine-grained captions.  
- Demonstrated applicability to **real-world insurance and risk assessment** scenarios.


## Contributions

- **Fine-Grained Caption Generation and Validation** for remote sensing datasets.  
- **Unified multimodal retrieval framework** combining global, graph, and scene-based representations.  
- **Novel Graph Matching Network (GMN)** for dynamic graph similarity scoring.  
- **Scene-based retrieval** as a lightweight, training-free alternative.  
- **Extensive benchmarking** across RSICD, NWPU, RSITMD, and FIT-RS datasets.

## Defense & Supervision

- **Institution**: EPFL – School of Computer and Communication Sciences  
- **Supervisors**: Prof. *Devis Tuia* (EPFL ENAC) & *Ciprian Tomoiaga* (AXA Group Operations)  
- **Defense Date**: August 26, 2025  
- **Author**: *Oussama Gabouj*  


## Resources

- **Date**: August 28, 2025  
- **PDF**: [Full Thesis PDF](/files/Master_thesis_final_report.pdf)  
- **Slides**:[Presentation Slides](/files/Master_Thesis_Presentation.pptx)


> *This work bridges vision–language modeling and remote sensing, paving the way for structured, interpretable, and fine-grained retrieval systems in complex geospatial domains.*
