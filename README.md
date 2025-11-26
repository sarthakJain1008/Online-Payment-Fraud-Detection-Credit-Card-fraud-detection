# 🛡️ **Online Payment Fraud Detection – Credit Card Fraud Detection**

*A Machine Learning–Based Fraud Detection System*

---

## 📌 **Abstract**

This project implements a complete end-to-end machine learning pipeline for detecting fraudulent online payment transactions using real-world credit card data. The workflow includes data cleaning, feature scaling, correlation analysis, model training, and performance evaluation using multiple algorithms such as Logistic Regression, Decision Tree, Random Forest, KNN, Naïve Bayes, and SVM.

The **Random Forest Classifier** achieves the best results with an **F1-score of 0.9998**, demonstrating near-perfect detection capability. This repository serves as a student-friendly and deployment-ready fraud detection solution.

---

# 📁 **Project Structure**

```
|-- ONLINE_PAYMENT_FRAUD_DETECTION.ipynb
|-- data/ (optional: dataset path or instructions)
|-- figures/ (correlation heatmap & model comparison)
|-- README.md

```

---

# 🔧 **Technologies Used**

- **Python 3.x**
- **Pandas**, **NumPy**
- **Scikit-Learn**
- **Seaborn**, **Matplotlib**
- **StandardScaler**
- **Machine Learning Algorithms**
    - Logistic Regression
    - Naïve Bayes
    - Decision Tree
    - Random Forest
    - KNN
    - Linear SVM

---

# 📊 **Dataset Information**

- 431,316 rows
- 31 columns originally
- After cleaning → 431,316 × 30
- Features: `V1`–`V28` (PCA-transformed), `Amount`, `Class`
- `Class`:
    - **0 → Legitimate**
    - **1 → Fraud**

---

# 🧠 **Methodology**

### **1. Data Loading & Inspection**

- Loaded dataset using Pandas
- Checked shape, types, missing values, duplicates

### **2. Data Cleaning**

- Removed 20 missing values
- Removed irrelevant `id` column
- Final shape: **431,316 × 30**

### **3. Exploratory Data Analysis**

- Fraud vs legitimate distribution
- Correlation matrix heatmap of 30 features
- Observed feature relationships and variance
- Confirmed imbalanced dataset

### **4. Preprocessing**

- **StandardScaler** applied to `Amount` feature
- Removed remaining missing values
- Train-test split:
    - **80% training**
    - **20% testing**
    - Stratified for class balance

### **5. Model Training**

Trained 6 machine learning models:

| Model | Status |
| --- | --- |
| Logistic Regression | ✔ Trained |
| Naïve Bayes | ✔ Trained |
| Decision Tree | ✔ Trained |
| Random Forest | ✔ Trained |
| KNN (k=3) | ✔ Trained |
| Linear SVM | ✔ Trained |

A unified evaluation function calculated:

- Accuracy
- Precision
- Recall
- F1-score
- Training time

### **6. Model Comparison**

- Compiled all results
- Bar plot generated for F1-score comparison
- Random Forest emerged as best model

---

# 📈 **6. Performance Analysis**

## **6.1 Performance Metrics (Test Set)**

| **Model** | **Accuracy** | **Precision** | **Recall** | **F1-score** |
| --- | --- | --- | --- | --- |
| **Random Forest (Best)** | **99.97%** | **99.93%** | **99.99%** | **99.96%** |
| **KNN (k=3)** | 99.81% | 99.43% | **100%** | 99.72% |
| **Decision Tree** | 99.73% | 99.48% | 99.73% | 99.60% |
| **Logistic Regression** | 97.10% | 97.62% | 93.79% | 95.67% |
| **Linear SVM** | 96.96% | 97.96% | 93.02% | 95.43% |
| **Naïve Bayes** | 93.76% | 95.43% | 85.82% | 90.37% |

---

## **6.2 Correlation Matrix (Summary)**

### **Top Positive Correlations**

| Feature Pair | Correlation |
| --- | --- |
| V20 – V21 | +0.48 |
| V2 – V5 | +0.36 |
| V3 – V4 | +0.33 |

### **Top Negative Correlations**

| Feature Pair | Correlation |
| --- | --- |
| V1 – V3 | –0.53 |
| V4 – V5 | –0.41 |

### **Correlation with Target (Fraud Class)**

| Feature | Correlation |
| --- | --- |
| V17 | +0.32 |
| V14 | +0.29 |
| V12 | +0.26 |
