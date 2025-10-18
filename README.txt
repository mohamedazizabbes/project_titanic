# Titanic Survival Prediction Using Machine Learning

## Overview

This repository (`project_titanic`) predicts Titanic passenger survival using state-of-the-art machine learning models. We analyze the historic Titanic dataset to uncover key factors influencing survival, and build a model achieving **81% accuracy**.

## Libraries Used

- **pandas**: Data manipulation and analysis.
- **numpy**: Numerical operations.
- **seaborn** & **matplotlib.pyplot**: Data visualization.

## Project Workflow

1. **Data Loading**
   - Load Titanic training and test data from CSV files using pandas.

2. **Exploratory Data Analysis (EDA)**
   - Visualize age, fare, and family size distributions.
   - Analyze relationships and correlations among features.

3. **Data Cleaning & Feature Engineering**
   - Impute missing values.
   - Remove irrelevant columns (PassengerId, Cabin, Name, Ticket).
   - Create new features to enhance prediction.

4. **Model Selection & Testing**
   - Evaluate models: Decision Tree, Random Forest, ExtraTrees, Logistic Regression, LGBM, XGBoost.
   - Select the best model with **81% validation accuracy**.

5. **Results & Submission**
   - Predict survival on the test dataset.
   - Generate a CSV submission file for external evaluation.

## Conclusion

Our model demonstrates effective prediction of Titanic passenger survival, providing insights into historical disaster outcomes and the practical use of machine learning.

## Authors

- Mohamed Aziz Abbes
- Anas Abd Elmalek Cherif
- Ahmed Ben Salah
