---
title: "🐱🐶 Binary Image Classification: Cats vs Dogs (MLOps Project)"
paperurl: ""
permalink: /cats-dogs-mlops-project/
author: "MLOps Project Team"
---

This project addresses a binary image classification problem: distinguishing between images of cats and dogs using deep learning techniques.

Beyond model performance, the main focus is the implementation of a complete **Machine Learning Operations (MLOps)** pipeline. The project follows the principles taught in the DTU MLOps course, where the emphasis is not only on building models, but on making them **reproducible, maintainable, scalable, and deployable in production systems**.

---

## 🧠 What is MLOps (in this course context)?

According to the DTU MLOps course framework (Skafte Detlefsen & Hauberg), **MLOps (Machine Learning Operations)** is the practice of managing the full lifecycle of machine learning systems, beyond just model training.

It connects three main phases:

### 1. Design Phase
This phase focuses on understanding the problem, defining requirements, and identifying available data. It ensures that the machine learning task is well-defined before modeling begins.

### 2. Model Development Phase
This is the experimental stage where models are designed, trained, and evaluated. It includes:
- Data preprocessing and feature engineering  
- Model selection and training  
- Evaluation and validation to ensure generalization  

### 3. Operations Phase
This is the production-focused stage where models are:
- Packaged into reproducible systems  
- Deployed as services (e.g., APIs)  
- Monitored and maintained over time  
- Integrated into automated workflows (CI/CD pipelines)

The key idea in MLOps is that these phases are **cyclical**, meaning models are continuously improved and redeployed as requirements and data evolve.

---

## 🎯 Objective

The objective of this project is to train a convolutional neural network based on **ResNet-50** for binary classification while applying best practices from MLOps, including reproducibility, automation, and deployment.

---

## 📊 Dataset

The dataset consists of labeled images of cats and dogs. It is structured into training and validation sets, with a balanced number of examples per class.

Each image belongs to one of two categories:
- Cat
- Dog

This simple dataset allows focusing on the MLOps pipeline rather than complex data engineering.

---

## 🧠 Model Architecture

The model is based on **ResNet-50**, a deep convolutional neural network originally designed for large-scale image recognition.

Key characteristics:
- Residual learning architecture  
- Pretrained on ImageNet  
- Adapted (fine-tuned) for binary classification  

This transfer learning approach enables strong performance even with a relatively small dataset.

---

## ⚙️ MLOps Principles Applied in This Project

This project demonstrates several core MLOps principles as defined in the DTU MLOps course:

### 🔁 Reproducibility
Ensuring that experiments can be repeated and produce consistent results through structured code, fixed environments, and versioned data.

### 📦 Modularity and Code Organization
The project is structured into clear components (data, models, features, and deployment), making it easy to maintain and extend.

### ☁️ Scalability
Training can be executed on cloud infrastructure, enabling handling of larger datasets and faster experimentation.

### 🚀 Deployment
The trained model is exposed as a service using an API, demonstrating how machine learning models can be integrated into real-world applications.

### 🔄 Continuous Integration and Delivery (CI/CD)
Automated pipelines ensure that changes in code can be tested and deployed reliably.

### 📊 Experiment Tracking
Training experiments can be tracked and compared to improve model selection and hyperparameter tuning.

---

## 🧩 Connection to DTU MLOps Course

This project is aligned with the DTU MLOps course structure, which emphasizes:

- Understanding the full ML lifecycle (design, development, operations)
- Learning production-grade machine learning practices
- Bridging the gap between research models and real-world deployment
- Using tools and workflows that support scalable ML systems

The course highlights that MLOps is not just about training models, but about **engineering machine learning systems that work reliably in production environments**.

---

## 📈 Summary

This project demonstrates how a simple computer vision task (cats vs dogs classification) can be extended into a full MLOps workflow. The focus is on building not just a model, but a **robust machine learning system** that follows production standards inspired by the DTU MLOps course.
