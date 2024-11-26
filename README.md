# Titanic Data Preprocessing and Logistic Regression Model

This project involves preprocessing the Titanic dataset and training a logistic regression model to predict passenger survival. The script performs data cleaning, feature engineering, transformation, and model training steps to achieve the desired outcome.

## Files

- **titanic_data_preprocessing.py**: The main Python script used for data preprocessing, exploratory data analysis (EDA), feature engineering, and model training.
- **train.csv**: The training dataset containing Titanic passenger data with survival information.
- **test.csv**: The test dataset used for making predictions on unseen data.

## Prerequisites

Ensure the following libraries are installed:
- pandas
- scikit-learn

You can install them using pip:
```sh
pip install pandas scikit-learn
```


## Script Overview

### 1. Data Cleaning

The script begins by removing irrelevant columns (`PassengerId`, `Name`, `Ticket`, `Cabin`) from the training and test datasets.

### 2. Handling Missing Values

- Missing values in the `Age` column are filled with the median age from the training data.
- Missing values in the `Fare` column are filled with the median fare from the training data.
- Missing values in the `Embarked` column are filled with the most frequent value (mode) from the training data.

### 3. Transformation

- The `Sex` column is transformed into a binary numerical value where 'male' is mapped to 0 and 'female' is mapped to 1.
- The `Embarked` column is converted into dummy variables using one-hot encoding, dropping the first category to avoid multicollinearity.

### 4. Normalization/Scaling

- The `Age` and `Fare` columns are scaled using `StandardScaler` to normalize the data.

### 5. Feature Engineering

- A new feature `FamilySize` is created by summing the `SibSp` and `Parch` columns and adding 1 (for the passenger themselves).
- The `SibSp` and `Parch` columns are dropped after the `FamilySize` feature is created.

### 6. Exploratory Data Analysis (EDA)

- Descriptive statistics for both the training and test datasets are displayed using `describe()` to understand the distribution of data.

### 7. Model Training

- The dataset is split into training and validation sets using `train_test_split`.
- A logistic regression model is trained on the training data.
- The model’s performance is evaluated using accuracy on the validation set, and the result is displayed.

## Conclusion

This script provides a comprehensive pipeline for data preprocessing, feature engineering, and model training on the Titanic dataset. It uses logistic regression to predict passenger survival and provides a clear evaluation of the model's performance.

