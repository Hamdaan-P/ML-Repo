# US Health Insurance Cost Prediction 🏥

## Project Overview

This project focuses on analyzing and predicting individual medical **insurance charges** using a public dataset of health factors. The core goal is to identify the primary drivers of healthcare costs and develop a robust machine learning model (Random Forest Regressor) to estimate annual charges.

This repository serves as a showcase of end-to-end data analysis skills, including **Exploratory Data Analysis (EDA)**, **Data Preprocessing**, **Model Building**, and **Model Interpretation**.

## 📊 Key Findings (Data Analyst Portfolio Focus)

The Exploratory Data Analysis (EDA) and subsequent **Feature Importance** analysis revealed critical, actionable insights:

| Rank | Feature | Importance | Insight for Business/Policy |
| :--- | :--- | :--- | :--- |
| **1** | **Smoker Status** | High (Primary Driver) | Smoking is, by far, the most significant determinant of high charges. This suggests targeted smoking cessation programs would yield the largest cost reductions. |
| **2** | **Age** | High | Charges show a clear positive correlation with age, especially within the non-smoker group. |
| **3** | **BMI** | Moderate | Higher BMI generally correlates with higher costs, with a strong interaction effect seen in the smoker population. |

## 💻 Methodology and Model Performance

### Workflow

1.  **Data Loading & Cleaning**: Initial checks confirmed no missing values.
2.  **EDA**: Visualizations and statistical analysis confirmed that the target variable (`charges`) is **right-skewed**, necessitating a **Log Transformation** to normalize the distribution.
3.  **Preprocessing**: A `ColumnTransformer` and `Pipeline` were used to apply **One-Hot Encoding** to categorical features (`sex`, `smoker`, `region`) and **Standard Scaling** to numerical features (`age`, `bmi`, `children`).
4.  **Modeling**: A **Random Forest Regressor** was chosen for its high predictive accuracy and ability to capture non-linear feature interactions.
5.  **Evaluation**: The model was evaluated on the original (USD) scale after an inverse transform ($\exp$).

### Model Results (Random Forest Regressor)

| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **R-squared ($R^2$) Score** | **0.884** | The model explains approximately **88.4%** of the variance in health insurance charges. |
| **Mean Absolute Error (MAE)** | **\$2,279** | On average, the model's prediction is off by about **\$2,279 USD**. |
| **Root Mean Squared Error (RMSE)** | **\$3,426** | This metric penalizes larger errors more heavily than MAE. |

## 🚀 How to Run the Project

### Prerequisites

You need the following files in your project directory:
* `US_Health_Insurance.ipynb` (The main notebook)
* `insurance.csv` (The dataset)

### Installation

1.  **Clone the repository:**
    ```bash
    git clone [your_repo_link]
    cd us-health-insurance-prediction
    ```
2.  **Create a virtual environment (Recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: .\venv\Scripts\activate
    ```
3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
4.  **Run the analysis:** Open and execute the cells in the `US_Health_Insurance.ipynb` notebook.
    ```bash
    jupyter notebook
    ```
The notebook will perform the full EDA, training, evaluation, and save the final trained model as `insurance_charge_predictor_rf.pkl`.