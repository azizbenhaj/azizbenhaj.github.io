---
title: "Customer Personality Analysis and Revenue Prediction for Retail Optimization"
excerpt: "This project analyzes customer behavior and predicts revenue generation using machine learning models, enabling targeted marketing strategies and improved business decision-making."
collection: research_projects
permalink:
reporturl: "/files/AudioAvenue.pdf"
share: false
related: false
---

## Problem Statement & Motivation

Retail companies must understand **customer behavior and purchasing patterns** to optimize marketing strategies and maximize revenue.

However, challenges include:

- **Heterogeneous customer profiles** with varying behaviors  
- Difficulty identifying **high-value customers**  
- Limited ability to predict **future revenue generation**  

This project addresses these challenges by combining **data analysis and machine learning** to segment customers and predict revenue, enabling more effective decision-making.


## Dataset & Features

The dataset contains customer information including:

- **Demographics**: age, education, marital status  
- **Income and spending behavior**  
- **Purchase history across product categories**  
- **Marketing campaign responses**  

Key variables were engineered to capture:

- Total spending  
- Customer engagement  
- Purchase frequency  


## Our Approach

### 1. Exploratory Data Analysis (EDA)

- Analyzed distributions of income, age, and spending  
- Identified correlations between **income and total purchases**  
- Detected patterns in **campaign responses and customer segments**  

📌 Insight:  
Higher income customers tend to spend more, but engagement varies significantly.


---

### 2. Data Preprocessing & Feature Engineering

- Handled missing values and outliers  
- Encoded categorical variables  
- Created aggregated features such as:
  - Total expenditure  
  - Customer activity indicators  

---

### 3. Revenue Prediction Models

We trained multiple models to predict customer revenue:

- **Linear Regression**  
- **Decision Trees**  
- **Random Forest**  
- **Gradient Boosting**

Models were evaluated using:

- Mean Squared Error (MSE)  
- R² score  


---

### 4. Model Evaluation

- Ensemble methods (**Random Forest, Gradient Boosting**) performed best  
- Linear models struggled with **non-linear relationships**  

📌 Key result:  
Tree-based models capture complex interactions between income, behavior, and spending.


## Key Results

- Strong correlation between **income and total spending**  
- Identification of **high-value customer segments**  
- **Ensemble models outperform simpler baselines**  
- Improved ability to **predict customer revenue**  

---

## Insights & Contributions

- Demonstrated the importance of **feature engineering** in retail data  
- Showed that **non-linear models** are better suited for customer behavior  
- Provided a framework for:
  - Customer segmentation  
  - Revenue prediction  
  - Marketing optimization  


## Discussion & Insights

### Strengths
- End-to-end pipeline from data analysis to prediction  
- Interpretable insights for business decisions  
- Scalable to real-world retail datasets  

### Limitations
- Dataset size may limit generalization  
- No temporal modeling of customer evolution  
- Limited external behavioral signals  

### Future Work
- Incorporate **time-series modeling** (customer lifetime value)  
- Use **deep learning approaches** for richer representations  
- Integrate **real-time recommendation systems**  


## Resources

- **Report**: [Full Report](/files/AudioAvenue.pdf)
