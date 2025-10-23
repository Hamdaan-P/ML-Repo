# 📈 Store Sales and Profitability Forecasting (Regression Analysis)

## Project Summary
This project employs a **Random Forest Regression** model to predict per-order **Profit** using a dataset of store transactions. The analysis focuses on identifying the primary drivers of profitability—and crucially, *unprofitability*—to deliver actionable recommendations for sales strategy and inventory management.

**Target Audience:** Data Analyst / Business Intelligence Recruiters

## 🔑 Key Findings & Business Recommendations

The model achieved a strong performance, explaining **81.6%** of the variance in Profit ($\mathbf{R^2 = 0.8158}$). The feature importance analysis revealed critical insights:

| Rank | Feature | Importance Score | Business Impact & Recommendation |
| :--- | :--- | :--- | :--- |
| **1** | **Sales** | **0.526** | **Primary Driver.** Profit scales directly with the Sales price. Focus efforts on securing high-value orders. |
| **2** | **Discount** | **0.373** | **Major Risk Factor.** Excessive discounting is the largest controllable drain on profit. **Action:** Implement stricter discount limits, especially for products with high variable costs. |
| **8** | **Sub-Category\_Tables** | **0.006** | **Major Loss Source.** The **Tables** sub-category (part of Furniture) is highlighted as a high-risk area. **Action:** Immediately review the true cost of goods sold, shipping, and storage for tables to prevent sustained losses. |
| **9** | **Sub-Category\_Chairs** | **0.005** | **Major Loss Source.** Similar to Tables, Chairs contribute significantly to variance, often negatively. **Action:** Optimize shipping modes or partner with third parties to reduce logistics costs for bulky items. |

## 🛠️ Technical Details & Methodology

### 1. Data Exploration (EDA)
* **Target Analysis:** Profit distribution showed a low mean but extreme negative outliers (losses up to **-\$1862**), indicating serious issues with specific high-cost transactions.
* **Categorical Deep Dive:** Confirmed that the **Furniture** category is the most volatile and the primary source of losses compared to Technology and Office Supplies.

### 2. Feature Engineering
* **Date Features:** Extracted `Order Year`, `Order Month`, and `Order DayOfWeek`.
* **Operational Feature:** Calculated `Ship Time Days` to measure potential impact of shipping speed on profit.

### 3. Preprocessing & Modeling
* **Feature Selection:** High-cardinality features (`City`, `State`) were dropped to prevent overfitting and multicollinearity, simplifying the model for business interpretability.
* **Encoding:** Categorical variables (`Segment`, `Region`, `Sub-Category`) were converted using **One-Hot Encoding**.
* **Scaling:** Numerical features (`Sales`, `Quantity`, `Discount`, etc.) were scaled using `StandardScaler`.
* **Model:** A **Random Forest Regressor** (`max_depth=10`, `n_estimators=100`) was selected for its balance of performance and built-in feature interpretability.

### 4. Results

| Metric | Random Forest Regressor | Baseline (Mean) |
| :--- | :--- | :--- |
| **R-squared ($R^2$)** | **0.8158** | 0.00 |
| **Root Mean Squared Error (RMSE)** | **\$57.40** | \$136.05 |

## 📦 Repository Contents

* `stores_sales_forecasting.csv`: The raw transaction dataset.
* `Store_Sales_Forecasting.ipynb`: The complete Python analysis notebook containing all data cleaning, EDA, model building, and interpretation code.
* `requirements.txt`: Python package dependencies.
* `assets/`: Directory containing all saved visualization outputs.

## ⚙️ How to Run This Project

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/YourUsername/Store-Sales-Profit-Forecasting.git](https://github.com/YourUsername/Store-Sales-Profit-Forecasting.git)
    cd Store-Sales-Profit-Forecasting
    ```
2.  **Create Environment & Install Dependencies:**
    ```bash
    # Assuming you have Python and pip installed
    pip install -r requirements.txt
    ```
3.  **Execute the Notebook:**
    Open `Store_Sales_Forecasting.ipynb` in Jupyter Lab or VS Code and run all cells sequentially.