---
title: "Generative Approaches to Kinetic Parameter Inference in Metabolic Networks via Latent Space Exploration"
collection: publications
# category: manuscripts # conferences
permalink: /publication/2025-04-05-latent-metabolic-generative-models
excerpt: "We introduce a generative framework for constructing large-scale kinetic metabolic models through latent space exploration. By repurposing pretrained neural network generators across different physiological contexts, our method enables efficient and interpretable inference of kinetic parameters, facilitating targeted model design for diverse metabolic behaviors."
date: 2025-04-05
venue: 'bioRxiv'
paperurl: 'https://www.biorxiv.org/content/10.1101/2025.03.31.646317v1'
# slidesurl: ''
# bibtexurl: 'https://www.biorxiv.org/content/10.1101/2025.03.31.646317v1.article-info'
share: false
related: false
---

## Abstract
Generative machine learning methods that utilize neural networks to parameterize large-scale and near-genome-scale kinetic models have yielded significant efficiency gains in model construction, paving the way for high-throughput dynamic metabolism studies in biomedical and biotechnological applications. Nevertheless, challenges remain in interpreting the outputs of generative neural networks and developing strategies to quickly adapt these networks to different organisms and physiological contexts without having to restart the modeling process from scratch. Here, we present a systematic framework for repurposing generative neural networks trained on one physiological context to build large-scale kinetic models tailored for another context, thereby offering a new avenue for efficiently constructing models with targeted desired properties suitable for various physiological scenarios. We showcase the effectiveness of this method through three case studies: (i) adjusting the modeled response speed of cellular metabolism in aerobic E. coli cultures, (ii) improving interpretability by identifying key enzymatic steps that limit the dynamic response speed of the metabolic models, and (iii) adapting our neural network to capture the distinct dynamic behavior of anaerobic E. coli. Given the growing adoption of generative neural networks in biological systems modeling, our approach has the potential to advance personalized medicine and accelerate the high-throughput design of cell factories by streamlining model construction across diverse living organisms.

## Key Contributions

- **Latent Control**: Demonstrates how the generator’s latent space can be navigated to produce new kinetic models with desired properties.
- **Cross-Physiology Repurposing**: Allows transfer from one strain or condition (e.g., wild-type) to another (e.g., recombinant or fast-growing).
- **Scalable Parameter Inference**: Offers an interpretable and efficient alternative to Monte Carlo or ensemble methods.

## Publication Details

- **Date**: April 5, 2025  
- **Preprint**: [bioRxiv - DOI: 10.1101/2025.03.31.646317](https://www.biorxiv.org/content/10.1101/2025.03.31.646317v2)  
- **License**: CC-BY-NC-ND 4.0  
- **PDF**: [Download Full Paper](https://www.biorxiv.org/content/10.1101/2025.03.31.646317v2.full.pdf)

