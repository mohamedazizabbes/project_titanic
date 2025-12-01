# Titanic Survival Prediction


## Overview
This repository contains a machine learning project focused on predicting the survival of passengers aboard the Titanic. By analyzing the historic Titanic dataset from Kaggle, we build and evaluate several models to identify key factors influencing survival. The final Logistic Regression model achieves an accuracy of **81.5%** on the validation set.

## Project Workflow
The analysis is conducted within the `notebook.ipynb` Jupyter Notebook and follows these key steps:

1.  **Data Loading**: The training data (`train.csv`) is loaded into a pandas DataFrame.
2.  **Exploratory Data Analysis (EDA)**: Initial analysis is performed to understand the dataset, including visualizing the distribution of the target variable (`Survived`) and exploring relationships between survival and features like `Sex` and `Pclass`.
3.  **Data Cleaning**: Missing values are handled by imputing the median for the `Age` column and the mode for the `Embarked` column.
4.  **Feature Engineering**: New features are created to improve model performance:
    *   `FamilySize`: Combines `SibSp` and `Parch` to represent the total number of family members on board.
    *   `Title`: Extracts the passenger's title (e.g., Mr, Mrs, Miss) from the `Name` column.
    *   `is_child`: A binary flag for passengers under the age of 12.
    *   The `Sex` column is converted from a string to a binary numerical format.
5.  **Model Training**: A `LogisticRegression` model is trained using a selection of the most impactful features. A `RandomForestClassifier` is also trained for comparison.
6.  **Model Evaluation**: The Logistic Regression model's performance is evaluated using metrics such as Accuracy, Precision, Recall, F1 Score, and ROC AUC score, achieving 81.5% accuracy.

## Features Used for Modeling
The final model uses the following features for prediction:
*   `Pclass`
*   `Sex`
*   `Age`
*   `Fare`
*   `FamilySize`
*   `is_child`

## Getting Started

### Prerequisites
*   Python 3.x
*   Jupyter Notebook or JupyterLab

### Installation
1.  Clone the repository to your local machine:
    ```sh
    git clone https://github.com/mohamedazizabbes/project_titanic.git
    cd project_titanic
    ```
2.  Install the required Python packages:
    ```sh
    pip install -r requirements.txt
    ```

### Running the Analysis
To view the complete data analysis, model training, and evaluation process, open and run the Jupyter Notebook:
```sh
jupyter notebook notebook.ipynb
```

## Prediction Function
A utility function, `predict_survival`, is provided in the notebook to predict the survival probability for a new passenger based on their attributes.

**Usage Example:**
```python
def predict_survival(pclass, sex, age, fare, family_size, is_child):
    """
    Return probability of survival (0-1) using the trained Logistic Regression model.
    sex: 0=female, 1=male
    is_child: 0=no, 1=yes
    """
    x_new = pd.DataFrame([[pclass, sex, age, fare, family_size, is_child]], columns=features)
    prob = model_lr.predict_proba(x_new)[0,1]
    return float(prob)

# Predict survival for a 1st class, 60-year-old female with a high fare and no family
prob_1 = predict_survival(1, 0, 60, 100, 1, 0)
print(f"Example 1 Survival Probability: {prob_1:.2f}")

# Predict survival for a 3rd class, 25-year-old male with a low fare and a family of 4
prob_2 = predict_survival(3, 1, 25, 15, 4, 0)
print(f"Example 2 Survival Probability: {prob_2:.2f}")

# Predict survival for a 2nd class, 8-year-old female child with a family of 3
prob_3 = predict_survival(2, 0, 8, 20, 3, 1)
print(f"Example 3 Survival Probability: {prob_3:.2f}")
```

## Authors
*   Mohamed Aziz Abbes
*   Anas Abd Elmalek Cherif
*   Ahmed Ben Salahh

