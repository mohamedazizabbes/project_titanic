# Titanic Survival Prediction

This project predicts the probability of survival for Titanic passengers using machine learning (scikit-learn, pandas, etc).  
It is a mini-project for learning basic data analysis, feature engineering, and classification modeling.

## Project Structure

- `notebook.ipynb`: Main Jupyter notebook with all code and documentation.
- `train.csv`: Titanic dataset (from [Kaggle](https://www.kaggle.com/c/titanic/data)).
- `requirements.txt`: List of Python dependencies.

## How to Run

1. Clone the repo:
   ```
   git clone https://github.com/mohamedazizabbes/project_titanic.git
   cd project_titanic
   ```

2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

3. Start Jupyter Notebook:
   ```
   jupyter notebook notebook.ipynb
   ```
   Run the cells in order.

## Example Usage

After training, use:
```python
predict_survival(pclass=1, sex=0, age=60, fare=80, family_size=1, is_child=0)  # Example: 1st class female, 60 years old
```
Returns probability of survival (e.g., 0.92).

## Authors

Group project by Mohamed Aziz Abbes, Anas Abd Elmalek Cherif and Ahmed Ben Salah 
