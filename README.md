## Introduction  

The [**Telco Customer Churn**](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) dataset contains records of **7,043 telecom customers** with details about their demographics, account information, subscribed services, and billing history.  

The goal is to predict **customer churn** — whether a customer leaves the company (**Yes**) or stays (**No**).  

This project explores the data and builds machine learning models in **Python**, using **Pandas, Scikit-learn, XGBoost, and Seaborn** for analysis and visualization.  

---

## Project Workflow

1. **Data Loading & Cleaning**
   - Removed unnecessary column (`customerID`)
   - Converted `TotalCharges` from string to numeric
   - Handled missing values

2. **Exploratory Data Analysis (EDA)**
   - Visualized categorical features vs. churn
   - Examined correlations between features and churn
   - Identified top correlated features (e.g., `Contract`, `tenure`, `OnlineSecurity`, `TechSupport`)

3. **Feature Engineering**
   - Encoded categorical features using `OrdinalEncoder`

4. **Modeling**
   - Implemented and evaluated multiple classifiers:
     - **XGBoost**
       - Accuracy: ~0.77
     - **Logistic Regression**
       - Accuracy: ~0.78
     - **K-Nearest Neighbors (with GridSearchCV for tuning)**
       - Best k = 19
       - Accuracy: ~0.79
     - **Random Forest**
       - Accuracy: ~0.78

5. **Evaluation**
   - Used accuracy, precision, recall, F1-score
   - Plotted confusion matrices for each model

---

## Results

| Model                | Accuracy | Notes                                    |
|-----------------------|----------|------------------------------------------|
| Logistic Regression   | 0.782    | Balanced precision & recall              |
| XGBoost               | 0.777    | Slightly lower recall on churned class   |
| KNN (k=19)            | 0.785    | Best accuracy, but lower recall on churn |
| Random Forest         | 0.78     | Comparable to Logistic Regression        |

Logistic Regression and KNN performed best, but **recall for churned customers remains a challenge**.

