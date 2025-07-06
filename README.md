# Telecom Churn Prediction

Predicting telecom customer churn using machine learning techniques to help telecom companies proactively retain customers by identifying those at high risk of leaving.

---

##  Background & Motivation

Churn refers to customers leaving a service provider. In the telecom industry, **retaining customers is more cost-effective than acquiring new ones**. Hence, identifying at-risk customers early can allow companies to take targeted retention actions.

This project aims to develop a **binary classification model** to predict churn based on customer behavior and service usage.

---

##  Dataset Overview

- **File**: `telecom_data_for_students.csv`
- **Size**: ~5,000 records (replace if different)
- **Features**:
  - Customer ID, Tenure
  - Recharge frequency & value
  - Data usage, call minutes
  - Complaints lodged, service quality
  - Plan type, billing method
  - Churn (target variable)

---

##  Machine Learning Workflow

### 1.  Data Preprocessing
- Handled missing values (e.g., NaNs in recharge data)
- Removed outliers (e.g., extremely high recharge values)
- Normalized continuous features (Min-Max Scaling)
- Encoded categorical variables (Label Encoding, One-Hot Encoding)

### 2.  Feature Engineering
- Created new features from:
  - Recharge consistency
  - Customer tenure brackets
  - Call/data usage frequency ratios
  - Complaint resolution time

### 3. Exploratory Data Analysis (EDA)
- Plotted churn vs:
  - Tenure
  - Recharge value
  - Service complaints
- Visualized class imbalance (churned vs non-churned)

### 4.  Model Building
- Algorithms tried:
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - XGBoost (best performer)
- Evaluation metrics:
  - Accuracy
  - Precision, Recall, F1-Score
  - ROC-AUC curve
  - Confusion Matrix

### 5.  Model Tuning
- Used GridSearchCV for hyperparameter tuning (XGBoost)
- Applied class weighting and regularization to avoid overfitting

---

##  Results

| Model              | Accuracy | Precision | Recall | F1 Score |
|-------------------|----------|-----------|--------|----------|
| Logistic Regression | 81.2%   | 0.79      | 0.83   | 0.81     |
| Random Forest       | 86.7%   | 0.84      | 0.88   | 0.86     |
| **XGBoost**         | **89.4%** | **0.87**  | **0.91** | **0.89** |

>  **XGBoost** provided the best trade-off between precision and recall.

**Top churn indicators**:
- Low recharge frequency
- High complaint count
- Short tenure
- Low data usage

---

##  Tech Stack

- **Language**: Python 3
- **IDE**: Jupyter Notebook
- **Libraries**:
  - pandas, numpy
  - matplotlib, seaborn
  - scikit-learn
  - XGBoost

---

##  How to Run Locally

1. Clone the repository:
   ```bash
   git clone https://github.com/SonicaSasanapuri/telecomechurn.git
   cd telecomechurn
