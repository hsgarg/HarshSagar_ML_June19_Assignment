<div align="center">

# Machine Learning Assignment

### Classification & Regression | June 2019

**Harsh Sagar Garg**

*Exploring supervised machine learning through two end-to-end prediction problems.*

</div>

---

## About this repository

This repository contains my solutions to a two-part machine learning assignment completed in June 2019. The work explores supervised learning techniques across both classification and regression, from initial data exploration and preprocessing to model comparison and generating predictions for unseen test data.

The assignment consists of two independent problems:

| | Problem | Objective | Evaluation metric |
|:--:|---|---|---|
| **01** | Classification | Predict the `Dataset` label | Accuracy |
| **02** | Regression | Predict `tat_in_days` | RMSE |

## Repository structure

```text
HarshSagar_ML_June19_Assignment/
│
└── HarshSagar_MLassignment/
    │
    ├── problem_1/
    │   ├── Jupyter notebook
    │   ├── Training and test datasets
    │   └── Prediction output
    │
    └── problem_2/
        ├── Jupyter notebook
        ├── Training and test datasets
        └── Prediction output
```

---

## Problem 1 — Classification

### Predicting the `Dataset` label

**Objective:** Train a classification model using the training dataset and predict the `Dataset` column for the test dataset.

**Evaluation metric:** Accuracy score

### Approach

The notebook begins with exploratory data analysis to understand the dataset's structure, feature distributions, missing values, and relationships between variables.

The preparation and feature-engineering steps include:

- Inspecting dataset dimensions, data types, and descriptive statistics.
- Handling missing values in `Albumin_and_Globulin_Ratio`.
- Converting the categorical `Gender` feature into numerical values.
- Creating a `Globulin` feature using Albumin and the Albumin-to-Globulin ratio.
- Exploring feature correlations using a heatmap.
- Engineering a `bilirubin` feature from Total Bilirubin and Direct Bilirubin.
- Splitting the data into training and validation sets.

### Algorithms explored

| Algorithm | Experiments |
|---|---|
| Logistic Regression | Multinomial classification |
| Gradient Boosting Classifier | Compared different numbers of estimators |
| Random Forest Classifier | Compared 10 and 200 estimators |
| K-Nearest Neighbors | K = 3 |
| Decision Tree | Gini criterion |
| Gaussian Naive Bayes | Gaussian probability model |
| Support Vector Classifier | One-vs-One and One-vs-Rest strategies |

### Model selection & prediction

The notebook identifies **Random Forest with 200 estimators** as the selected model and uses it to generate predictions for the unseen test dataset.

Accuracy values visible in the saved notebook outputs include:

| Model / configuration | Accuracy |
|---|---:|
| K-Nearest Neighbors (K = 3) | 75.53% |
| Decision Tree | 72.34% |
| Gaussian Naive Bayes | 48.94% |
| SVC — One-vs-One | 79.79% |
| SVC — One-vs-Rest | 79.79% |

*These are the accuracy values recorded in the notebook outputs. The selected Random Forest model's accuracy is not visible in the saved output.*

---

## Problem 2 — Regression

### Predicting insurance claim turnaround time

**Objective:** Train a regression model to predict the `tat_in_days` column for the test dataset.

**Evaluation metric:** Root Mean Squared Error (RMSE)

### Approach

This problem focuses on predicting the turnaround time associated with mobile-device insurance claims.

The notebook explores the dataset, prepares date and categorical variables, studies feature relationships, and compares multiple regression techniques.

Key preparation and analysis steps include:

- Reviewing dataset dimensions, data types, summary statistics, and missing values.
- Converting membership creation, mobile purchase, claim initiation, and pickup dates into date/time representations.
- Encoding categorical variables such as mobile make, claim type, and customer PIN-code category.
- Selecting operational and claim-related features for modelling.
- Visualizing feature correlations using a heatmap.
- Exploring low-variance feature selection.
- Splitting the data into training and validation sets.

### Algorithms explored

| Algorithm | Experiment / configuration |
|---|---|
| Linear Regression | Baseline linear model |
| Ridge Regression | Regularization with alpha = 100 |
| Lasso Regression | L1 regularization |
| Elastic Net | Alpha = 0.001; L1 ratio = 0.5 |
| Support Vector Regression | RBF kernel |
| Bagging Regressor | Ridge regression as base estimator |
| Gradient Boosting Regressor | Compared 400, 500, 600, 650 and 700 estimators |

### Model comparison

The notebook compares models using RMSE. The recorded validation results are:

| Model | RMSE |
|---|---:|
| Linear Regression | 4.918 |
| Ridge Regression | 4.924 |
| Lasso Regression | 5.088 |
| Elastic Net | 4.915 |
| Support Vector Regression | 4.981 |
| Bagging Regressor | 5.250 |
| **Gradient Boosting Regressor** | **4.516** |

*Lower RMSE indicates lower prediction error.*

### Model selection & prediction

**Gradient Boosting Regressor** achieved the lowest RMSE among the models recorded in the notebook. The notebook also compares estimator counts and selects 600 estimators.

The selected model is then used to predict `tat_in_days` for the unseen test dataset, with the predictions exported to a CSV file.

---

## Tools & libraries

The notebooks use Python and the following libraries:

- **NumPy** — numerical computing
- **Pandas** — data manipulation and analysis
- **Matplotlib** — data visualization
- **Seaborn** — correlation heatmaps and statistical visualization
- **Scikit-learn** — preprocessing, model training, model selection, and evaluation
- **Jupyter Notebook** — interactive development and experimentation

## How to explore the work

1. Open the `problem_1` or `problem_2` folder.
2. Launch the corresponding Jupyter notebook.
3. Review the data exploration, preprocessing, feature engineering, and model experiments.
4. Follow the final model selection and prediction-generation steps.

> **Note:** The original training and test CSV files are required to reproduce the notebook results. The notebooks expect the datasets to be available at the file paths referenced in the code.

---

<div align="center">

**Harsh Sagar Garg** · June 2019

*An exploration of machine learning through classification and regression.*

</div>
