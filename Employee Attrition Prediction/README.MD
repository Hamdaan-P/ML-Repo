# 📈 Employee Attrition Prediction and Analysis

## Project Overview
This project uses HR data to **predict employee attrition (turnover)** and, crucially, to **analyze the root causes** driving employees to leave. This work is a perfect demonstration of end-to-end data analysis and machine learning skills, covering:
1.  **Extensive Exploratory Data Analysis (EDA):** Uncovering key business insights.
2.  **Feature Engineering:** Creating high-impact features like Income per Experience.
3.  **Predictive Modeling:** Comparing multiple classification models (Logistic Regression, Random Forest, Gradient Boosting).
4.  **Actionable Insights:** Providing data-backed recommendations to management for reducing attrition.

## Key Findings & Business Insights (The "Why")

Based on the EDA and Gradient Boosting Feature Importance, the primary drivers of attrition are:

| Rank | Feature | Insight for HR |
| :--- | :--- | :--- |
| **1** | **MonthlyIncome** | Employees with lower monthly income are the highest flight risk. |
| **2** | **TotalWorkingYears** | Less experienced employees (low career investment) are more likely to leave. |
| **3** | **OverTime** | Working overtime **triples** an employee's probability of attrition. |
| **4** | **Age** | Younger employees show higher turnover rates. |
| **5** | **YearsWithCurrManager** | A lack of managerial relationship or poor management (low tenure with manager) contributes to turnover. |

## Technical Implementation

### Models Used
| Model | Handling Imbalance | ROC AUC Score | F1-Score (Attrition 'Yes') |
| :--- | :--- | :--- | :--- |
| **Logistic Regression** | `class_weight='balanced'` | **0.8166** | **0.49** |
| Random Forest | `class_weight='balanced'` | 0.7625 | 0.40 |
| Gradient Boosting | N/A | 0.7895 | 0.33 |

**Conclusion:** The **Logistic Regression** model provided the best balance of AUC (overall performance) and F1-Score (ability to correctly identify at-risk employees), making it the optimal choice for deployment.

### File Structure
. ├── Employee_Attrition_Prediction_Project.ipynb # The main Python Notebook with all EDA and ML code. ├── WA_Fn-UseC_-HR-Employee-Attrition.csv # The original dataset used for the project. ├── README.md # (This file) Project summary and instructions. └── requirements.txt # List of required libraries and versions.


## How to Run the Project

### Prerequisites
You need **Python 3.8+** installed along with the libraries listed in `requirements.txt`.

### Steps
1.  **Clone the Repository:**
    ```bash
    git clone [YOUR_REPO_URL]
    cd [YOUR_REPO_NAME]
    ```
2.  **Create and Activate Virtual Environment (Recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```
3.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
4.  **Launch Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```
5.  Open `Employee_Attrition_Prediction_Project.ipynb` and run all cells sequentially.