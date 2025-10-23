# 👩‍🔬 Breast Cancer Diagnosis Prediction using Logistic Regression

## Project Overview
This project focuses on building an accurate and interpretable machine learning model to predict the diagnosis of breast tumors as either **Malignant (M)** or **Benign (B)** based on digitized image features.

The goal is to demonstrate a complete, structured data science workflow, from initial data exploration and preprocessing to model training, evaluation, and interpretation, utilizing the simplicity and high performance of **Logistic Regression**.

## 🚀 Key Features & Performance

* **Binary Classification:** Predicts tumor diagnosis ('M' or 'B').
* **High Accuracy:** The Logistic Regression model achieved an accuracy of approximately **97.66%** on the test set.
* **Excellent Discrimination:** The model exhibits exceptional performance with a **ROC AUC Score of 0.99**.
* **Model Interpretability:** Features related to the **size (radius)**, **texture**, and **irregularity (symmetry, concave points)** of the tumor were identified as the most influential factors in the diagnosis.

## ⚙️ Methodology

1.  **Data Loading & Cleaning:** Loaded the `data.csv` file, dropped irrelevant identifier columns (`id`) and empty columns (`Unnamed: 32`).
2.  **Preprocessing:** Encoded the target variable (`diagnosis`: M=1, B=0) and performed **Standardization (Z-score scaling)** on all features to ensure optimal performance for the Logistic Regression model.
3.  **Model Training:** Trained a Logistic Regression classifier on the preprocessed data.
4.  **Evaluation:** Evaluated the model using a Confusion Matrix, Classification Report, ROC Curve, and ROC AUC Score.


## 📂 Project Structure

. ├── Breast_Cancer_Diagnosis_Prediction.ipynb (The main analysis notebook) ├── data.csv (The dataset used for training and testing) ├── README.md (This file) └── requirements.txt (List of necessary Python libraries)


## 🛠️ Prerequisites

To run this notebook, you will need a Python environment with the following libraries installed.

You can set up the environment using the `requirements.txt` file:

```bash
pip install -r requirements.txt
