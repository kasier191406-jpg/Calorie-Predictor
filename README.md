# Calorie Burn Prediction

A machine learning project that predicts calories burned during exercise using physiological and activity-related features.

## Overview

This project uses a Linear Regression model to predict the number of calories burned based on:

- Age
- Height
- Weight
- Exercise Duration
- Heart Rate
- Body Temperature
- Gender

The dataset contains **15,000 samples**.

## Machine Learning Workflow

```text
Dataset
   ↓
Data exploration
   ↓
Feature preprocessing
   ↓
Gender encoding
   ↓
Train / Test Split
   ↓
Linear Regression
   ↓
Prediction
   ↓
Model Evaluation
   ↓
Save trained model


Dataset

The dataset contains the following columns:

Feature	Description
User_ID	Unique user identifier
Gender	Gender of the user
Age	Age of the user
Height	Height of the user
Weight	Weight of the user
Duration	Exercise duration
Heart_Rate	Heart rate during exercise
Body_Temp	Body temperature
Calories	Calories burned — target variable

The User_ID column was removed because it does not provide useful predictive information.

Preprocessing

The Gender feature was converted from categorical values into numerical values using LabelEncoder.

The target variable is:

Calories

The input features are:

Age
Height
Weight
Duration
Heart_Rate
Body_Temp
Gender

The data was split into:

80% training data
20% testing data

with:

random_state=42
Model

The project uses:

Linear Regression

from sklearn.linear_model import LinearRegression


model = LinearRegression()
model.fit(X_train, y_train)
Results

The model was evaluated on the test set.

Metric	Result
RMSE	11.4889
R² Score	0.9673

An R² score of approximately 0.967 means the model explains a large proportion of the variation in the test-set target values.

Model Coefficients

The trained model produced the following coefficients:

Age          →   0.5015
Height       →  -0.1697
Weight       →   0.2863
Duration     →   6.6280
Heart Rate   →   1.9909
Body Temp    → -16.9425
Gender       →  -1.3742

The model intercept is:

461.8627
Saved Model

The trained model is saved using Joblib:

calorie_predictor.pkl

It can be loaded later without retraining:

import joblib


model = joblib.load("calorie_predictor.pkl")
Project Files
Calorie-Predictor/
├── calorie.ipynb
├── calorie_predictor.pkl
├── calories.csv
└── README.md
calorie.ipynb

Contains the complete data exploration, preprocessing, training, prediction, and evaluation workflow.

calorie_predictor.pkl

Contains the trained Linear Regression model.

calories.csv

Dataset used for the project.

Technologies
Python
pandas
NumPy
scikit-learn
Matplotlib
Joblib
Jupyter Notebook
Running the Project
Clone the repository
git clone https://github.com/kasier191406-jpg/Calorie-Predictor.git
Install dependencies
pip install pandas numpy matplotlib scikit-learn joblib jupyter
Open the notebook
jupyter notebook

Open:

calorie.ipynb

and run the notebook cells.

Future Improvements
Compare Linear Regression with other regression algorithms
Perform feature engineering
Add cross-validation
Build a prediction API
Deploy the trained model
Integrate the model into a larger application
Author

Kasier

GitHub:
https://github.com/kasier191406-jpg
