# Customer Churn — Advanced EDA & Feature Engineering

## Project Overview

This project focuses on transforming raw customer data into a clean, structured, and machine-learning-ready dataset.

The project covers data loading, data cleaning, exploratory data analysis (EDA), missing-value handling, outlier detection and treatment, feature engineering, machine-learning preprocessing, model training, and model evaluation.

## Project Objectives

* Clean and prepare the customer dataset.
* Analyze customer behavior using exploratory data analysis.
* Identify and handle missing values.
* Detect and treat outliers using the Interquartile Range (IQR) method.
* Create predictive features from existing customer information.
* Prepare numerical and categorical variables for machine learning.
* Train and evaluate classification models.
* Identify the most important features for customer churn prediction.
* Produce a final clean dataset suitable for further machine-learning analysis.

## Dataset

The dataset contains customer-level information related to purchasing behavior, customer tenure, spending, returns, cancellations, payment methods, referral sources, and churn.

### Final Dataset

* **Rows:** 1,073
* **Columns:** 28
* **Missing Values:** 0
* **Duplicate Rows:** 0
* **Infinite Values:** 0

The final cleaned dataset is:

`customer_churn_final_cleaned.csv`

## Exploratory Data Analysis

The project includes analysis and visualizations of important customer characteristics, including:

* Customer Recency
* Purchase Frequency
* Customer Tenure
* Customer Returns
* Customer Cancellations
* Spending behavior
* Feature distributions
* Feature correlations

These analyses were used to understand customer behavior and prepare the data for feature engineering and machine learning.

## Data Cleaning

The dataset was checked for:

* Missing values
* Duplicate records
* Infinite numerical values
* Data types
* Invalid or unusual values

Missing numerical values were handled using median-based imputation where appropriate, while categorical values were handled using the most frequent category during machine-learning preprocessing.

## Outlier Detection and Treatment

The Interquartile Range (IQR) method was used to identify potential outliers.

The IQR was calculated as:

`IQR = Q3 - Q1`

Outlier boundaries were defined using:

`Lower Bound = Q1 - 1.5 × IQR`

`Upper Bound = Q3 + 1.5 × IQR`

Instead of removing customer records, IQR capping was used to limit extreme values to the calculated boundaries.

## Feature Engineering

Four new predictive features were created.

### 1. PurchaseIntensity

Measures purchasing frequency relative to customer tenure.

### 2. ValuePerTenureDay

Measures customer monetary value relative to the customer's tenure.

### 3. ReturnCancelRate

Combines the customer's return and cancellation percentages.

### 4. ProductSpendRatio

Measures monetary spending relative to product diversity.

These engineered features were created to provide additional information about customer purchasing behavior.

## Machine Learning Preprocessing

Numerical and categorical features were processed separately.

### Numerical Features

* Missing values were handled using median imputation.
* Numerical features were standardized using `StandardScaler`.

### Categorical Features

* Missing categorical values were handled using the most frequent value.
* Categorical variables were converted into numerical features using One-Hot Encoding.

## Machine Learning Models

The following classification models were trained and evaluated:

* Logistic Regression
* Decision Tree
* Random Forest

Cross-validation was also used to evaluate model stability.

## Model Results

| Model                                 | Accuracy |
| ------------------------------------- | -------: |
| Logistic Regression                   |   99.53% |
| Decision Tree                         |  100.00% |
| Random Forest                         |  100.00% |
| Random Forest 5-Fold Cross-Validation |   99.30% |

The Decision Tree and Random Forest achieved the highest test accuracy of 100.00%. Random Forest achieved a mean five-fold cross-validation accuracy of 99.30%, indicating strong and relatively stable performance.

## Feature Importance

Random Forest feature importance analysis identified the most influential features used by the model.

The highest-ranking features included:

1. EngagementScore
2. Tenure
3. TenureYears
4. PurchaseIntensity
5. FirstOrderYear
6. LastOrderYear
7. ValuePerTenureDay
8. CLV_Proxy

Feature importance analysis helps explain which customer characteristics contributed most to the model's predictions.

## Final Project Validation

The final dataset was successfully validated:

* **Dataset Shape:** 1,073 × 28
* **Missing Values:** 0
* **Duplicate Rows:** 0
* **Infinite Values:** 0
* **Engineered Features:** 4

## Repository Contents

* `Project_1_Advanced_EDA_Feature_Engineering.ipynb` — Complete project notebook
* `customer_level_churn_dataset.csv` — Original customer dataset
* `customer_churn_final_cleaned.csv` — Final cleaned and feature-engineered dataset
* `README.md` — Project documentation
* `.gitignore` — Git ignored files
* `LICENSE` — MIT License

## Conclusion

This project successfully transformed the raw customer dataset into a clean and machine-learning-ready dataset.

The workflow covered advanced exploratory data analysis, statistical data cleaning, IQR-based outlier treatment, feature engineering, categorical encoding, model training, cross-validation, and feature-importance analysis.

The final dataset contains 1,073 records and 28 columns with no missing, duplicate, or infinite values and is ready for further machine-learning analysis.
