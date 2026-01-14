# Personal Finance Savings Recommender AI

## Overview
This project is an **AI-powered Personal Finance Savings Recommender**. It uses **machine learning** to predict potential monthly savings for an individual based on their income, expenses, and demographics, and generates **personalized financial recommendations** to optimize spending.  

The project demonstrates practical skills in:
- Data preprocessing and feature engineering
- Machine learning with scikit-learn (Random Forest Regressor)
- Handling categorical and numeric features
- Generating actionable recommendations from model insights

---

## Dataset
The dataset is sourced from [Kaggle: Indian Personal Finance and Spending Habits](https://www.kaggle.com/datasets/shriyashjagtap/indian-personal-finance-and-spending-habits).  

It contains detailed financial and demographic data for 20,000 individuals, including:
- **Income & Demographics**: Age, Occupation, City Tier, Dependents  
- **Monthly Expenses**: Rent, Loan Repayment, Insurance, Groceries, Transport, Eating Out, Entertainment, Utilities, Healthcare, Education, Miscellaneous  
- **Savings Goals**: Desired Savings, Desired Savings Percentage, Disposable Income  
- **Potential Savings**: Category-wise savings estimates  

> ⚠️ **Note:** The pre-trained pipeline file (`personal_finance_pipeline.joblib`) is ~288 MB and **not included** in this repo due to GitHub file size limits. You can retrain the model locally using the notebook.

---

## Features

The model uses the following features:
- Income, Age, Dependents, Occupation, City Tier
- Rent, Loan Repayment, Insurance, Groceries, Transport
- Eating Out, Entertainment, Utilities, Healthcare, Education, Miscellaneous
- Engineered features:
  - `Total_Expense`
  - `Expense_Income_Ratio`
  - `Discretionary_Spend`
  - `Discretionary_Ratio`
  - `High_Dependents`
  - `Is_Tier1_City`

---

## How It Works

1. **Data Preprocessing**
   - Separate categorical and numeric features
   - One-Hot Encode categorical columns (`Occupation`, `City_Tier`)
   - Standardize numeric columns  

2. **Feature Engineering**
   - Compute total monthly expenses, discretionary spending, and ratios  
   - Add flags for high dependents and Tier 1 cities  

3. **Model Training**
   - Train a **Random Forest Regressor** to predict `Desired_Savings`  
   - Evaluate using **MAE** and **R² score**  

4. **Feature Importance**
   - Identify most impactful features on predicted savings  

5. **Recommendations**
   - Generate actionable financial tips based on user spending patterns, e.g.:
     - Reduce eating out & entertainment
     - Optimize rent or housing costs
     - Plan grocery purchases efficiently

---

## Results

After training, the model achieves:

- **MAE (Mean Absolute Error):** ~608  
- **R² Score:** ~0.92  

Top features influencing savings predictions:
- `Income`  
- `Expense_Income_Ratio`  
- `Healthcare`, `Utilities`, `Transport`  

Sample recommendations for a user:

Predicted Monthly Savings: 12000.50
Recommendations:
- Reduce eating out & entertainment expenses
- Consider optimizing housing costs


