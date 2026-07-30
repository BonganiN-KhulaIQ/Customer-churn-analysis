# Customer-churn-analysis
Exploratory Data Analysis of customer churn behaviour using Python, Pandas, NumPy, Matplotlib and Seaborn.
Project Overview

This project analyzes customer churn patterns using historical customer and pricing data.
The goal is to identify factors that may influence customer retention and provide insights that can support business decision-making.

Tools Used
Python
Pandas
NumPy
Matplotlib
Seaborn
Jupyter Notebook

Project Tasks
Data Cleaning
Exploratory Data Analysis (EDA)
Missing Value Analysis
Feature Exploration
Customer Behaviour Analysis
Churn Pattern Investigation
Key Skills Demonstrated
Data Wrangling
Data Visualization
Statistical Analysis
Business Understanding
Insight Generation
Files
Customer_Churn_Analysis_BCG.ipynb


# Customer Churn Prediction & Feature Engineering

##  Project Overview
This project focuses on predicting customer churn for an energy provider by training a predictive **Random Forest Classifier** on feature-engineered historical usage and pricing data. 

Using an end-to-end Machine Learning pipeline in Python (`pandas`, `scikit-learn`), this project addresses key real-world challenges, such as model evaluation under **imbalanced class distributions**, where overall accuracy can be misleading.

---

##  Dataset Summary
* **Records:** 14,606 customer instances
* **Features:** 61 predictive variables (including one-hot encoded channel origins and tenure indicators)
* **Target Variable:** `churn` (Binary: `0` = Retained, `1` = Churned)

---

##  Machine Learning Pipeline

### 1. Data Preparation & Sampling
* Loaded clean feature dataset (`data_for_predictions.csv`).
* Dropped unnecessary identifiers (`id`) and split into target vector (`y`) and feature matrix (`X`).
* Split data using **75% training** (10,954 samples) and **25% testing** (3,652 samples) splits with a fixed seed (`random_state=42`).

### 2. Model Architecture
* **Algorithm:** `RandomForestClassifier`
* **Estimators:** `n_estimators=200`
* **Random State:** `42`

### 3. Model Evaluation & Results
Due to significant class imbalance in the target variable (~10% churn rate), model performance was evaluated using comprehensive metric classification rather than relying solely on overall accuracy:

| Metric | Score | Notes |
| :--- | :--- | :--- |
| **Accuracy** | **90.28%** | High baseline driven by majority class retention |
| **Precision** | **72.00%** | When predicting churn, the model is correct 72% of the time |
| **Recall** | **4.92%** | Identifies only ~5% of all actual churners (due to class imbalance) |
| **F1 Score** | **0.092** | Harmonic mean of precision and recall |
| **ROC AUC** | **0.661** | Model's overall discrimination threshold ability |

#### Confusion Matrix:
```text
[[3279    7]   <- True Negatives (3279) / False Positives (7)
 [ 348   18]]  <- False Negatives (348) / True Positives (18)
# Customer Churn Prediction & Feature Engineering

## 📌 Project Overview
This project focuses on predicting customer churn for an energy provider by analyzing historical consumption, pricing data, and customer tenure. Using Python and **scikit-learn**, I performed data cleaning, engineered predictive features, and trained a **Random Forest Classifier** to identify customers at risk of leaving.

The goal of this project is to demonstrate an end-to-end Machine Learning pipeline—from raw data preprocessing to baseline model evaluation—that delivers actionable business insights.

---

## 🛠️ Key Steps & Methodology

### 1. Data Loading & Preprocessing
* Loaded clean baseline datasets (`clean_data_after_eda.csv` and `price_data.csv`).
* Converted date columns (`date_activ`, `date_end`, `date_modif_prod`, `date_renewal`, `price_date`) into datetime formats.
* Handled missing values by filling numerical features with medians and baseline defaults.

### 2. Feature Engineering
Created new domain-specific features to capture customer behavior and price sensitivity:
* **Off-Peak Price Differences:** Calculated variations between December and January off-peak energy and power prices (`offpeak_diff_dec_january_energy`, `offpeak_diff_dec_january_power`).
* **Tenure Metrics:** Engineered total customer tenure in months (`tenure_months`) and time elapsed since the last product modification (`months_since_modification`).
* **Categorical Encoding:** One-hot encoded categorical variables like sales channels (`channel_sales`) and contract origin (`origin_up`).

### 3. Model Building & Evaluation
* Split data into **80% training** and **20% testing** sets using stratified sampling to maintain target balance.
* Trained a **Random Forest Classifier** (`n_estimators=100`, `random_state=42`) to baseline churn classification.

---

## 🧰 Tech Stack & Libraries
* **Language:** Python 3.x
* **Data Manipulation:** `pandas`, `numpy`
* **Machine Learning:** `scikit-learn` (RandomForestClassifier, train_test_split)

---


README.md
Author

Bongani Nkosi

Aspiring Data Scientist | Mathematics & Statistics Student
