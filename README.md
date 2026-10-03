# Customer Churn Prediction Using Machine Learning

## 1. Project Overview

Customer churn occurs when customers stop using a company's products or services. Understanding customer churn is important because retaining existing customers helps businesses maintain revenue and improve customer relationships.

In this project, I used Python and machine learning to analyse customer behaviour and predict customer churn in a telecommunications company.

I performed data exploration, data cleaning, exploratory data analysis (EDA), feature engineering, model training and model evaluation.

Two machine learning algorithms were implemented: **Logistic Regression and Random Forest Classifier**.

## 2. Project Objectives

The objectives of this project were to:

* Explore customer data and understand its structure.
* Identify customer characteristics associated with churn.
* Clean and preprocess the dataset.
* Analyse customer behaviour using statistical analysis and visualizations.
* Develop machine learning models to predict customer churn.
* Evaluate and compare the performance of the models.
* Identify important features associated with customer churn.

## 3. Dataset Description

**Dataset:** IBM Telco Customer Churn Dataset

**Source:** [IBM Telco Customer Churn Dataset](https://github.com/IBM/telco-customer-churn-on-icp4d)

The original dataset contains:

* **7,043 customer records**
* **21 columns**
* **Target variable:** Churn

The dataset contains customer information relating to demographics, services, account details and billing information.

Some important features include:

| Feature         | Description                              |
| --------------- | ---------------------------------------- |
| Gender          | Customer gender                          |
| SeniorCitizen   | Whether the customer is a senior citizen |
| Tenure          | Number of months the customer has stayed |
| InternetService | Type of internet service                 |
| Contract        | Customer contract type                   |
| PaymentMethod   | Customer payment method                  |
| MonthlyCharges  | Monthly customer charges                 |
| TotalCharges    | Total customer charges                   |
| Churn           | Whether the customer left the company    |

The target variable, `Churn`, contains two categories:

* Yes: The customer churned.
* No: The customer did not churn.

## 4. Technologies and Libraries Used

**Programming Language:** Python

**Development Environment:** Google Colab / Jupyter Notebook

**Libraries:**

* Pandas — Data manipulation and analysis
* NumPy — Numerical operations
* Matplotlib — Data visualization
* Seaborn — Statistical data visualization
* Scikit-learn — Machine learning and model evaluation

## 5. Data Cleaning and Preprocessing

I performed several data cleaning and preprocessing operations to prepare the dataset for machine learning.

The steps included:

1. Loading the dataset using Pandas.
2. Examining the dataset structure, data types and summary statistics.
3. Checking for missing values and duplicate records.
4. Identifying 11 blank values in the `TotalCharges` column.
5. Converting `TotalCharges` into a numeric data type.
6. Removing records containing missing `TotalCharges` values.
7. Removing the `customerID` column from the predictive features.
8. Converting categorical features into numerical features using one-hot encoding.
9. Splitting the dataset into training and testing sets using an 80:20 ratio.
10. Applying StandardScaler to prepare the features for Logistic Regression.

After cleaning, the dataset contained **7,032 customer records**.

## 6. Exploratory Data Analysis (EDA)

Exploratory data analysis was performed to understand customer behaviour and investigate factors associated with churn.

The analysis examined:

* Overall customer churn distribution
* Contract type and churn
* Internet service and churn
* Payment method and churn
* Customer tenure
* Monthly and total charges
* Senior citizen status

### Customer Churn Distribution

The original dataset contained:

| Churn Status | Customers | Percentage |
| ------------ | --------: | ---------: |
| No           |     5,174 |     73.46% |
| Yes          |     1,869 |     26.54% |

The dataset contained more customers who remained with the company than customers who churned.

### Contract Type

The analysis showed the following churn rates:

* Month-to-month contracts: 42.71%
* One-year contracts: 11.28%
* Two-year contracts: 2.85%

Customers with month-to-month contracts had a higher observed churn rate than customers with longer contracts.

### Internet Service

The observed churn rates were:

* Fiber optic: 41.89%
* DSL: 19.00%
* No internet service: 7.43%

Customers using fiber optic internet had the highest observed churn rate among these groups.

### Payment Method

Customers using electronic checks had an observed churn rate of approximately 45.29%.

This was higher than the churn rates observed for customers using automatic bank transfers or credit card payments.

### Senior Citizen Status

The analysis showed that senior citizens had an observed churn rate of approximately 41.68%, compared with 23.65% among non-senior citizens.

### Numerical Features

Box plots were used to examine the relationship between churn and:

* Tenure
* MonthlyCharges
* TotalCharges

These visualizations helped explore differences in customer account characteristics between churned and retained customers.

These findings describe associations in the dataset and do not establish that individual features cause customers to churn.

## 7. Machine Learning Model Development

I developed two supervised machine learning classification models to predict customer churn.

The dataset was divided into:

* 80% training data
* 20% testing data

Stratified sampling was used to maintain the distribution of the target variable across the training and testing datasets.

### Model 1: Logistic Regression

Logistic Regression was trained using standardized features.

The model was configured with a maximum of 1,000 iterations and a random state of 42.

**Model accuracy: 80.38%**

### Model 2: Random Forest Classifier

A Random Forest Classifier was trained using 100 decision trees and a random state of 42.

**Model accuracy: 78.96%**

## 8. Model Evaluation

Both models were evaluated using classification metrics, including accuracy, precision, recall and F1-score.

A confusion matrix was also generated for the Logistic Regression model.

### Model Performance Comparison

| Evaluation Metric | Logistic Regression | Random Forest |
| ----------------- | ------------------: | ------------: |
| Accuracy          |              80.38% |        78.96% |
| Churn Precision   |                0.65 |          0.63 |
| Churn Recall      |                0.57 |          0.52 |
| Churn F1-score    |                0.61 |          0.57 |

Logistic Regression achieved higher accuracy and higher churn-class precision, recall and F1-score on the test dataset.

However, both models missed some customers who actually churned, indicating opportunities for further improvement.

## 9. Feature Importance

I examined feature importance using the Random Forest Classifier.

The three features with the highest importance scores were:

1. TotalCharges
2. Tenure
3. MonthlyCharges

Other features appearing among the model's ten most important predictors included:

* InternetService_Fiber optic
* PaymentMethod_Electronic check
* Contract_Two year
* Gender_Male
* OnlineSecurity
* PaperlessBilling
* TechSupport

Feature importance describes how the trained Random Forest model used these variables. It does not establish a causal relationship with customer churn.

## 10. Key Findings

The analysis produced several findings:

* Approximately 26.54% of customers in the original dataset had churned.
* Customers with month-to-month contracts had a higher observed churn rate.
* Customers using fiber optic internet had a higher observed churn rate than the other internet service groups.
* Electronic check users had a relatively high observed churn rate.
* Senior citizens had a higher observed churn rate than non-senior citizens.
* Total charges, tenure and monthly charges received the highest feature importance scores in the Random Forest model.
* Logistic Regression achieved approximately 80.38% accuracy, while Random Forest achieved approximately 78.96%.

## 11. Conclusion

This project demonstrates how Python, data analysis and machine learning can be applied to customer churn prediction.

Through data cleaning, exploratory data analysis and predictive modelling, I investigated customer characteristics associated with churn.

I developed and evaluated Logistic Regression and Random Forest classification models. Logistic Regression achieved approximately 80.38% accuracy on the test dataset, compared with approximately 78.96% for Random Forest.

The analysis also identified customer characteristics that businesses could investigate when developing customer retention strategies.

The project provided practical experience in data preprocessing, exploratory data analysis, feature engineering, classification modelling and model evaluation.

## 12. Future Improvements

Potential improvements to this project include:

* Testing additional machine learning algorithms.
* Performing hyperparameter tuning.
* Investigating techniques for handling class imbalance.
* Using cross-validation to assess model performance.
* Improving recall for customers who churn.
* Developing an interactive customer churn prediction application.

These are proposed future improvements and were not implemented in the current notebook.

## 13. How to Run the Project

1. Download or clone this GitHub repository.
2. Open `Customer_Churn_Prediction.ipynb` using Google Colab or Jupyter Notebook.
3. Install the required Python libraries if they are not already available.
4. Run the notebook cells in order.

The notebook loads the Telco Customer Churn dataset directly from IBM's GitHub repository, so an internet connection is required when running the data-loading cell.

Required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## 14. Project File

`Customer_Churn_Prediction.ipynb` — Contains the complete data exploration, cleaning, visualizations, preprocessing, model training and evaluation.

## 15. Author

**Uzoka Esomchukwu Peace**

Data Science and Machine Learning Student

Interested in applying data science and machine learning to solve real-world problems.
