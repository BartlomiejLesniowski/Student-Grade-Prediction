# Student Grade Prediction

**Author:** Bartłomiej “Bartek” Leśniowski  
**Date:** Dec 07, 2024

Description from Kaggle.com - https://www.kaggle.com/datasets/uciml/student-alcohol-consumption/data

"The data were obtained in a survey of students math and portuguese language courses in secondary school. It contains a lot of interesting social, gender and study information about students. You can use it for some EDA or try to predict students final grade."

My goal is to create the prediction model, that will predict if student pass the exam or fail. 
---

## 📋 Table of Contents

1. [Project Overview]
2. [Requirements]
3. [Installation]
4. [Data]
5. [Exploratory Data Analysis (EDA)]
6. [Data Preparation]
7. [Modeling]  
   - 7.1 [Train/Test Split]
   - 7.2 [Feature Engineering] 
   - 7.3 [Algorithms] 
8. [Results & Evaluation]
9. [Usage]


---

## Project Overview

This project builds regression models to predict a student’s final grade (`G3`) based on:

- **Demographics**: age, gender, address  
- **Study habits**: weekly study time, past failures, absences  
- **Support factors**: family support, extra educational activities  

We walk through EDA, preprocessing, model training, and performance comparison.

---

## Requirements

- **Language:** Python 3.8+  
- **Environment:** Jupyter Notebook / JupyterLab  
- **Key Libraries:**  
  - pandas, numpy  
  - matplotlib, seaborn  
  - scikit-learn  
  - scipy (optional)

---

## Installation

1. **Clone the repository**  
   bash
   git clone https://github.com/<your-username>/student-grade-prediction.git
   cd student-grade-prediction

2. **Create & activate a virtual environment**

  bash
  python3 -m venv venv
  source venv/bin/activate   # macOS/Linux
  venv\Scripts\activate      # Windows

3. **Install dependencies**

  bash

  pip install -r requirements.txt

**Data**

Source: CSV file containing student survey and grade data

Size: ~67 KB, 33 columns

**Key columns:**

age – student age

study_time – weekly study hours

failures – number of past course failures

absences – number of school absences

G1, G2 – first and second period grades

G3 – final grade (target variable)

**Exploratory Data Analysis (EDA)**

Descriptive statistics – mean, median, range, outliers

Visualizations – histograms, boxplots, correlation heatmap

Feature relationships – scatterplots and bar charts to identify strong predictors

**Data Preparation**

Missing values:

Numeric features filled with median

Categorical features imputed with mode

Scaling: StandardScaler or MinMaxScaler for numeric data

Encoding: One-hot encode categorical variables

**Feature engineering:**

Average partial grade: (G1 + G2) / 2

Attendance ratio: absences / max(absences)

Modeling

Train/Test Split

Split: 80% train, 20% test

Reproducibility: random_state=42

**Feature Engineering**

Select top features using SelectKBest (e.g., top 10)

**Algorithms**

Model	- Main Parameters

Linear Regression	- default

Ridge Regression	- alpha=0.5, grid search optional

Lasso Regression	- alpha=0.5, grid search optional

Decision Tree Regressor	- max_depth=5

Random Forest Regressor	- n_estimators=100, max_depth=7


**Results & Evaluation**

Metrics:

MSE (Mean Squared Error)

MAE (Mean Absolute Error)

R² (Coefficient of Determination)

**Highlights:**

Random Forest achieved the lowest MSE (e.g., MSE = 1.23)

Ridge Regression delivered the highest R² (e.g., R² = 0.85)

Detailed performance reports, residual plots, and prediction vs. actual comparisons are available in the notebook.

**Usage**

Open the notebook:

bash

jupyter notebook "Student Grade Prediction.ipynb"

Follow each section from EDA through Modeling.

To predict on new data, update the CSV path and rerun cells in the “Modeling” section.
