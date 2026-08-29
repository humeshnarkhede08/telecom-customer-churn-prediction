# Customer Churn Prediction (Telecom)

A Machine Learning project to predict whether a telecom customer will leave the company ("churn") or stay, using the famous **Telco Customer Churn** dataset.

## Project Overview

Customer churn means a customer stopping the services of the company. Finding new customers is much more expensive than keeping existing ones, so if a telecom company can predict in advance which customers are likely to leave, it can offer them special deals and try to retain them.

This project uses machine learning to do exactly that — predict the `Churn` column (Yes/No) using customer information like tenure, monthly charges, contract type, internet service, payment method, etc.

## Dataset

- **Source:** IBM Telco Customer Churn dataset (`Telco-Customer-Churn.csv`)
- **Size:** 7043 rows (customers), 21 columns (features)
- **Target column:** `Churn` (Yes = customer left, No = customer stayed)
- Some important features: `tenure`, `MonthlyCharges`, `TotalCharges`, `Contract`, `InternetService`, `PaymentMethod`

## What is inside the notebook

The notebook `Customer_Churn_Prediction.ipynb` contains:

1. **Introduction** — problem explanation
2. **Data loading & overview** — `df.info()`, `df.describe()`, missing value check
3. **Exploratory Data Analysis (EDA)** — graphs showing churn distribution, churn vs contract type, churn vs internet service, tenure vs churn, correlation heatmap
4. **Data Preprocessing** — removed `customerID`, converted Yes/No to 0/1, one-hot encoding for categorical columns, feature scaling
5. **Model Building** — trained 3 models:
   - Logistic Regression
   - Decision Tree
   - Random Forest
6. **Model Comparison** — accuracy, precision, recall and F1-score of all 3 models
7. **Feature Importance** — top factors that influence churn most
8. **Conclusion** — results and suggestions for the company

## Requirements

Install the required libraries using:

```
pip install -r requirements.txt
```

The `requirements.txt` file includes:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- jupyter
- ipykernel

## How to Run

1. Keep all the files in the same folder.
2. Open a terminal in that folder and run:

```
jupyter notebook Customer_Churn_Prediction.ipynb
```

3. The notebook will open in the browser. Run all cells (Kernel -> Restart & Run All).

## Results

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Logistic Regression | ~0.79 | ~0.62 | ~0.52 | ~0.56 |
| Decision Tree | ~0.72 | ~0.46 | ~0.48 | ~0.47 |
| Random Forest | ~0.79 | ~0.62 | ~0.48 | ~0.54 |

**`tenure`, `TotalCharges` and `MonthlyCharges`** are the most important features. After examining the data, we also found that customers with month-to-month contracts, fiber optic internet and low tenure are most likely to churn.

## Files

- `Customer_Churn_Prediction.ipynb` — main project notebook
- `Telco-Customer-Churn.csv` — dataset
- `requirements.txt` — list of required libraries
- `README.md` — this file