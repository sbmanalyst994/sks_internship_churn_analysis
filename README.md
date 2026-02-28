# Customer Churn Analysis and Prediction

## Project Overview
This project focuses on analyzing customer churn for a telecommunications company and developing predictive models to identify at-risk customers. The primary objective is to provide actionable insights and recommendations to improve customer retention and reduce revenue loss.

This project was developed as part of the **SaiKet Systems Internship Program**.

---

## Technical Workflow

### 1. Data Preparation & Preprocessing
* **Exploratory Data Analysis:** Initial assessment of the 7,043-entry dataset to identify data types and missing values.
* **Feature Conversion:** Converted `TotalCharges` from an object (string) type to numeric, addressing 11 missing values that occurred during conversion by filling them with 0.
* **Handling Class Imbalance:** Identified a significant imbalance in the target variable `Churn` (5,174 "No" vs. 1,869 "Yes").
* **Encoding:** Utilized `LabelEncoder` for categorical variable transformation.

### 2. Feature Selection
* **Multicollinearity Check:** Used Variance Inflation Factor (VIF) and correlation heatmaps to identify redundant features.
* **Dimensionality Reduction:** Dropped `customerID`, `gender`, and `TotalCharges` (highly correlated with tenure and monthly charges) to improve model stability.

### 3. Model Training & Evaluation
The dataset was split into **80% training** and **20% testing** sets, using stratification to maintain class balance. 

We prioritized **Recall** because the cost of a False Negative (missing a churner) is significantly higher than the cost of a False Positive (sending a retention offer to a loyal customer).

#### Model Performance Comparison (Final Result)
| Metric | Logistic Regression | XGBoost |
| :--- | :---: | :---: |
| **Recall (Class 1)** | 0.81 | **0.89** |
| **Precision (Class 1)** | 0.52 | 0.45 |
| **False Negatives** | 72 | **40** |
| **Accuracy** | 0.75 | 0.68 |

---

## Key Insights & Conclusion
* **Winner:** **XGBoost** is the superior model for this business case due to its high **Recall (0.89)**.
* **Strategic Impact:** XGBoost identifies nearly 90% of all potential churners, missing only 40 customers compared to the 72 missed by Logistic Regression. 
* **Business Trade-off:** We effectively traded a higher volume of marketing outreach (False Positives) for a significantly lower rate of customer loss (False Negatives).


---

## Technologies Used
* **Languages:** Python
* **Libraries:** Pandas, NumPy, Scikit-learn, XGBoost, Seaborn, Matplotlib
* **Environment:** Jupyter Notebook

---

## Acknowledgments
Special thanks to **SaiKet Systems** for sponsoring this internship and providing the framework for this analysis.
