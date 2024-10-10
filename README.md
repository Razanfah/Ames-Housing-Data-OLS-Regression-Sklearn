# Ames-Housing-Data-OLS-Regression-Sklearn

## Overview

This project aims to predict house prices using Ordinary Least Squares (OLS) regression and Scikit-learn, employing the Ames Housing dataset. The workflow consists of exploratory data analysis (EDA), data cleaning, OLS regression analysis, and model evaluation using Scikit-learn.

## Table of Contents

- [Project Pipeline](#Project_Pipeline)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Ordinary Least Squares (OLS)](#ordinary-least-squares-ols)
- [Regression with Scikit-learn](#regression-with-scikit-learn)
- [Error Metrics](#error-metrics)
- [Conclusion](#conclusion)

## Project Pipeline
![image](https://github.com/user-attachments/assets/1cfc7fe2-62d8-466b-99ab-449dbeb442ed)

## Exploratory Data Analysis (EDA)

In this phase of the project, we will conduct Exploratory Data Analysis (EDA) to gain insights into the dataset. Our primary objectives include:

1. **Removing Non-significant Data**: We will drop unnecessary features and remove rows that do not contribute meaningfully to our analysis.
  
2. **Fixing Field Values**: We will correct any inconsistencies or errors in the data fields to ensure accuracy and reliability for further analysis.

3. **Handling Missing Values**: We will fill missing values using appropriate strategies:
   - **Mean Imputation**: For numerical fields, we will replace NaNs with the mean of the column.
   - **Mode Imputation**: For categorical fields, we will replace NaNs with the most frequently occurring value.
   - **Zero Imputation**: In cases where it makes sense, we may replace NaNs with zero.

Through these steps, we aim to prepare a clean and informative dataset that will facilitate deeper insights into the factors influencing property prices.

Next, we will count the missing values in each column to evaluate the completeness of the dataset. Columns with a significant number of null values will be dropped.

We will examine the unique values of each feature to check for any remaining NaNs and understand the distribution of values. For instance, we will correct the 'MS Zoning' feature by replacing incorrect values with the correct ones.

Next, we will deal with NaN values using different strategies, such as replacing NaNs with the most used value, the mean, and zero. Finally, we will clean the feature names by replacing spaces with underscores and changing "1st" to "First."


## Ordinary Least Squares (OLS)

In this project, we will conduct an OLS regression analysis with the primary goal of maximizing the R² value. Our approach will involve several key steps:

1. **Correlation Analysis**: We will calculate the correlation of numeric features to evaluate their contributions to the R² value.

2. **Dummy Variable Conversion**: We will convert categorical features into dummy variables for inclusion in our regression model.

3. **Incremental Dummy Features Addition**: We will add dummy features to the model one by one, monitoring changes in the R² value.

### Model Summary

- Dependent Variable: SalePrice
- R-squared (OLS): 0.879
- Adjusted R-squared (OLS): 0.877
  
## Regression with Scikit-learn

In this section, we implement a robust regression analysis using Scikit-learn after addressing multicollinearity in our features.

1. **Feature Selection**: We retained only the features that had been filtered out during the OLS step.

2. **Model Evaluation Approaches**:
   - **Model Training with Train, Validation, and Test Split**: We split the dataset into training, validation, and test sets.
   - **Cross-Validation**: We performed 5-fold cross-validation to assess the model’s performance across different data splits.
   - **Combining Both Methods**: We combined the train-validation-test split with cross-validation for a robust assessment.

### Comparison of Results:

|  Metric  | Validation Set | Test Set |  Cross-Validation Mean |
|----------|----------------|----------|------------------------|
| **Normal Split**         | Validation R²: 0.898 | Test R²: 0.821 | -                      |
| **Cross-Validation**     | -                  | -        | Mean R²: 0.864        |
| **Normal Split + Cross-Validation** | - | -        | Mean R²: 0.886        |

### Summary of Results:

1. **Normal Split**:
   - **Validation Set**: R² score of **0.898**.
   - **Test Set**: R² score of **0.821**.

2. **Cross-Validation**:
   - Mean R² score of **0.864** from 5-fold cross-validation.

3. **Normal Split followed by Cross-Validation**:
   - Mean R² score of **0.886**.

## Error Metrics

To evaluate the model’s performance, we calculated the following metrics during cross-validation:

- **Sum of Squared Errors (SSE)**: [Insert SSE Value]
- **Root Mean Squared Error (RMSE)**: [Insert RMSE Value]
- **Mean Absolute Error (MAE)**: [Insert MAE Value]

These metrics provide a comprehensive understanding of the model's predictive performance.

## Conclusion

The OLS regression analysis successfully identified significant predictors of `SalePrice`, culminating in a final model that achieved an R-squared value of 0.879. The regression analysis using Scikit-learn further validated the model's robustness, demonstrating its effectiveness in predicting housing prices. The combination of OLS and Scikit-learn methodologies allowed for a thorough exploration and understanding of the factors impacting property sale prices.
