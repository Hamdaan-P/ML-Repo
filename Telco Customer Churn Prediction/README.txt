[![Kaggle Dataset](https://img.shields.io/badge/kaggle-dataset-brightgreen?logo=kaggle)](https://www.kaggle.com/)
[![Stars](https://img.shields.io/github/stars/Hamdaan-P/ML-Repo?style=social)](https://github.com/Hamdaan-P/ML-Repo/stargazers)
[![Python](https://img.shields.io/badge/python-3.7%2B-blue?logo=python)](https://www.python.org/)
[![Downloads](https://img.shields.io/github/downloads/Hamdaan-P/ML-Repo/total.svg)](https://github.com/Hamdaan-P/ML-Repo)
# 📉 Telco Customer Churn Prediction (Classification Project)

## Project Status: Complete

### 🎯 Overview
This project focuses on building a robust Machine Learning model to predict customer churn for a telecommunications company. Identifying high-risk customers proactively allows the company to implement targeted retention strategies, significantly reducing customer acquisition costs and increasing Customer Lifetime Value (CLV).

### 💡 Business Value
* **Proactive Retention:** Flagging potential churners with high confidence (using high Recall/ROC-AUC) before they leave.
* **Actionable Insights:** Identifying key contract, service, and usage features that are driving attrition, enabling strategic resource allocation.

### 🛠️ Technology Stack
* **Language:** Python
* **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`
* **Machine Learning:** `scikit-learn` (for Pipeline, ColumnTransformer, and Model), `RandomForestClassifier`
* **Environment:** Jupyter Notebook / Google Colab

### ⚙️ Methodology & Pipeline
1.  **Data Cleaning:** Handled missing values (`TotalCharges` NaNs) and corrected data types.
2.  **EDA:** Visualized class imbalance and identified primary churn drivers (e.g., tenure and contract type).
3.  **Preprocessing Pipeline:** Used `ColumnTransformer` for:
    * **Scaling:** `StandardScaler` on numerical features (`tenure`, `MonthlyCharges`, `TotalCharges`).
    * **Encoding:** `OneHotEncoder` on categorical features.
4.  **Modeling:** Employed a **Random Forest Classifier** with `class_weight='balanced'` to effectively handle the dataset's class imbalance.

### 📊 Key Results

| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **ROC-AUC Score** | **0.8315** | Indicates strong discriminatory power between churners and non-churners. |
| **Churn Recall (Sensitivity)** | **0.72** | The model correctly identifies 72% of all actual customers who churn. Crucial for retention efforts. |
| **Accuracy** | 0.76 | Overall classification accuracy. |


---
