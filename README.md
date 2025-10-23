# 🎯 ML-Repo: Machine Learning Project Portfolio

## 📋 Repository Overview

Welcome to ML-Repo! This repository showcases a comprehensive collection of **5 end-to-end machine learning projects** demonstrating proficiency in data science, predictive modeling, and business analytics. Each project follows industry best practices with complete data pipelines from exploration to deployment-ready models.

---

## 📂 Projects

### 1. 👩‍🔬 Breast Cancer Diagnosis Prediction
**Type:** Binary Classification | **Algorithm:** Logistic Regression

**Overview:**  
Predicts breast tumor diagnosis as Malignant (M) or Benign (B) using digitized image features.

**Key Achievements:**
- ✅ **97.66% Accuracy** on test set
- ✅ **ROC AUC Score: 0.99** (Excellent discrimination)
- ✅ Feature importance analysis revealing radius, texture, and symmetry as key diagnostic factors

**Technical Stack:**
- Data preprocessing with standardization (Z-score scaling)
- Logistic Regression classifier
- Evaluation: Confusion Matrix, Classification Report, ROC Curve

📁 [View Project →](./Breast_Cancer_Diagnosis_Prediction)

---

### 2. 📊 Employee Attrition Prediction and Analysis
**Type:** Binary Classification | **Algorithms:** Logistic Regression, Random Forest, Gradient Boosting

**Overview:**  
Predicts employee turnover and analyzes root causes using HR data with extensive exploratory data analysis (EDA).

**Key Findings:**
- 💰 **MonthlyIncome** - Primary driver: Lower income = higher flight risk
- 📅 **TotalWorkingYears** - Less experienced employees more likely to leave
- ⏰ **OverTime** - Triples attrition probability
- 👤 **Age** - Younger employees show higher turnover
- 👔 **YearsWithCurrManager** - Poor management relationships increase attrition

**Model Performance:**
| Model | ROC AUC | F1-Score (Attrition 'Yes') |
|-------|---------|---------------------------|
| Logistic Regression | 0.8166 | 0.49 |
| Random Forest | 0.7625 | 0.40 |
| **Gradient Boosting** | **0.7895** | **0.33** |

**Business Value:**  
Provides actionable insights for HR to implement targeted retention strategies.

📁 [View Project →](./Employee%20Attrition%20Prediction)

---

### 3. 🏥 US Health Insurance Cost Prediction
**Type:** Regression Analysis | **Algorithm:** Random Forest Regressor

**Overview:**  
Predicts individual medical insurance charges and identifies primary cost drivers using health factors.

**Key Insights:**
| Rank | Feature | Importance | Business Impact |
|------|---------|------------|------------------|
| 1 | **Smoker Status** | High (Primary Driver) | Most significant cost determinant - suggests targeted cessation programs |
| 2 | **Age** | High | Positive correlation, especially in non-smokers |
| 3 | **BMI** | Moderate | Higher BMI correlates with higher costs, strong interaction with smoking |

**Methodology:**
- Log transformation for right-skewed target variable
- One-Hot Encoding for categorical features (sex, smoker, region)
- Standard Scaling for numerical features (age, bmi, children)
- Random Forest Regressor for non-linear feature interactions
- Evaluation on original USD scale (inverse transform)

**Technical Highlights:**
- Complete EDA with visualizations
- Pipeline-based preprocessing (ColumnTransformer)
- Feature importance analysis
- Model interpretability focus

📁 [View Project →](./Medical%20Insurance%20Cost%20Prediction)

---

### 4. 📈 Store Sales and Profitability Forecasting
**Type:** Regression Analysis | **Algorithm:** Random Forest Regression

**Overview:**  
Predicts per-order profit using store transaction data, focusing on profitability drivers and unprofitability factors.

**Model Performance:**
- **R² = 0.8158** (explains 81.6% variance in Profit)

**Key Business Recommendations:**

| Rank | Feature | Importance | Business Action |
|------|---------|------------|------------------|
| 1 | **Sales** | 0.526 | Primary driver - focus on high-value orders |
| 2 | **Discount** | 0.373 | Major risk factor - implement stricter limits |
| 8 | **Sub-Category: Tables** | 0.006 | Major loss source - review cost structure |
| 9 | **Sub-Category: Chairs** | 0.005 | Loss contributor - optimize shipping |

**Critical Findings:**
- 🚨 Profit distribution highly right-skewed with extreme negative outliers (losses up to -$1862)
- ⚠️ Excessive discounting identified as largest controllable drain on profit
- 📦 Tables and Chairs sub-categories highlighted as high-risk areas

**Target Audience:** Data Analysts / Business Intelligence Recruiters

📁 [View Project →](./Store%20Sales%20Forecasting)

---

### 5. 📱 Telco Customer Churn Prediction
**Type:** Binary Classification | **Algorithm:** Random Forest Classifier

**Overview:**  
Predicts customer churn for a telecommunications company, enabling proactive retention strategies and reducing acquisition costs.

**Business Value:**
- 🎯 **Proactive Retention:** Flag high-risk customers before they leave (high Recall/ROC-AUC)
- 💡 **Actionable Insights:** Identify key contract, service, and usage features driving attrition
- 💰 **Resource Optimization:** Focus retention efforts on customers most likely to churn

**Model Performance:**
| Metric | Value | Interpretation |
|--------|-------|----------------|
| **ROC-AUC Score** | **0.8315** | Strong discriminatory power between churners and non-churners |
| **Churn Recall (Sensitivity)** | **0.72** | Correctly identifies 72% of actual customers who churn |
| **Accuracy** | 0.76 | Overall classification accuracy |

**Technology Stack:**
- **Language:** Python
- **Libraries:** pandas, numpy, matplotlib, seaborn
- **ML Framework:** scikit-learn (Pipeline, ColumnTransformer, RandomForestClassifier)
- **Environment:** Jupyter Notebook / Google Colab

**Methodology:**
1. Data cleaning with missing value handling
2. EDA with class imbalance visualization
3. Preprocessing pipeline:
   - StandardScaler on numerical features (tenure, MonthlyCharges, TotalCharges)
   - OneHotEncoder on categorical features
4. Random Forest Classifier with `class_weight='balanced'` for imbalance handling

📁 [View Project →](./Telco%20Customer%20Churn%20Prediction)

---

## 🛠️ Technical Skills Demonstrated

### Machine Learning
- **Classification:** Logistic Regression, Random Forest, Gradient Boosting
- **Regression:** Random Forest Regressor, Linear Models
- **Techniques:** Feature Engineering, Hyperparameter Tuning, Class Imbalance Handling

### Data Science Workflow
- ✅ Exploratory Data Analysis (EDA)
- ✅ Data Preprocessing & Feature Engineering
- ✅ Model Training & Evaluation
- ✅ Model Interpretation & Business Insights

### Tools & Libraries
- **Languages:** Python
- **Libraries:** pandas, numpy, matplotlib, seaborn, scikit-learn
- **Environments:** Jupyter Notebook, Google Colab

### Business Acumen
- Translating technical metrics into actionable business recommendations
- Feature importance analysis for strategic decision-making
- Domain-specific insights (Healthcare, HR, Retail, Telecom)

---

## 📊 Project Structure

Each project follows a consistent structure:

```
Project_Name/
├── README.md              # Detailed project documentation
├── notebook/              # Jupyter notebooks with full analysis
├── data/                  # Dataset files
├── assets/                # Visualizations and images
├── requirements.txt       # Python dependencies
└── gitkeep               # Directory placeholder
```

---

## 🚀 Getting Started

### Prerequisites
- Python 3.7+
- pip or conda package manager

### Installation

1. Clone the repository:
```bash
git clone https://github.com/Hamdaan-P/ML-Repo.git
cd ML-Repo
```

2. Navigate to a specific project:
```bash
cd "Breast_Cancer_Diagnosis_Prediction"
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Launch Jupyter Notebook:
```bash
jupyter notebook
```

---

## 📈 Key Metrics Summary

| Project | Type | Best Model | Key Metric | Score |
|---------|------|------------|------------|---------|
| Breast Cancer Diagnosis | Classification | Logistic Regression | Accuracy | 97.66% |
| Breast Cancer Diagnosis | Classification | Logistic Regression | ROC AUC | 0.99 |
| Employee Attrition | Classification | Logistic Regression | ROC AUC | 0.8166 |
| Medical Insurance Cost | Regression | Random Forest | - | - |
| Store Sales Forecasting | Regression | Random Forest | R² | 0.8158 |
| Telco Customer Churn | Classification | Random Forest | ROC AUC | 0.8315 |
| Telco Customer Churn | Classification | Random Forest | Recall | 0.72 |

---

## 💼 Business Impact

These projects demonstrate the ability to:

1. **Healthcare:** Build accurate diagnostic support systems
2. **Human Resources:** Reduce employee turnover through predictive analytics
3. **Insurance:** Optimize pricing strategies and identify high-risk individuals
4. **Retail:** Maximize profitability through data-driven inventory and pricing decisions
5. **Telecommunications:** Reduce customer acquisition costs through proactive retention

---

## 📝 License

This repository is available for educational and portfolio purposes.

---

## 👤 Author

**Hamdaan-P**

📧 Feel free to reach out for collaborations or questions!

---

## 🌟 Acknowledgments

- Datasets sourced from public repositories and Kaggle
- Inspired by real-world business problems
- Built with a focus on practical, deployment-ready solutions

---

⭐ **If you find this repository helpful, please consider giving it a star!**
