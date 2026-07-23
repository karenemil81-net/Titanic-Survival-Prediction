# Titanic Survival Prediction 🚢

## Project Overview

This project focuses on predicting whether a passenger survived the Titanic disaster using Machine Learning classification algorithms.

The goal is to analyze passenger information, perform data preprocessing and feature engineering, apply statistical feature selection techniques, and build models that can predict survival outcomes.

---

# Dataset

The dataset used in this project is the **Titanic Dataset**.

It contains information about passengers including:

- Passenger class
- Gender
- Age
- Fare
- Family information
- Embarkation location
- Survival status

### Target Variable

`Survived`

| Value | Meaning |
|------|---------|
| 0 | Did Not Survive |
| 1 | Survived |

---

# Project Workflow

## 1. Data Exploration (EDA)

Performed exploratory data analysis to understand the dataset:

- Dataset dimensions
- Data types
- Missing values analysis
- Duplicate detection
- Target distribution analysis
- Feature relationships with survival

Visualizations included:

- Survival distribution
- Gender vs survival
- Passenger class vs survival
- Fare distribution
- Age distribution
- Passenger class vs fare
- Embarkation analysis

---

# 2. Data Preprocessing

The following preprocessing steps were applied:

## Removing Unnecessary Features

Removed:

- `PassengerId` → unique identifier
- `Ticket` → high cardinality feature
- `Name` → raw text feature
- `Cabin` → large number of missing values

---

## Handling Missing Values

Applied:

- Median imputation for `Age`
- Mode imputation for `Embarked`

---

## Handling Outliers

Used the **IQR method** for:

- Age
- Fare

Extreme values were capped instead of removed.

---

# 3. Feature Engineering

Created new meaningful features:

## Family Size

Calculated using:

```
FamilySize = SibSp + Parch + 1
```

This represents the total number of family members traveling together.

---

## Is Alone

Created a binary feature:

```
1 → Passenger traveled alone
0 → Passenger traveled with family
```

---

## Title Extraction

Extracted titles from passenger names:

Examples:

- Mr
- Mrs
- Miss
- Master
- Rare titles

Titles can provide information about:

- Gender
- Age
- Social status

---

# 4. Feature Analysis

Statistical analysis was performed before modeling.

## Correlation Analysis

Used correlation matrix to analyze relationships between numerical features and survival.

Main observations:

- Fare has a positive relationship with survival.
- Passenger class negatively affects survival.
- Numerical relationships are generally weak because survival depends on multiple factors.

---

## ANOVA Test

Used ANOVA to determine whether numerical feature distributions differ between survivors and non-survivors.

Features analyzed:

- Age
- Fare
- FamilySize

---

## Chi-Square Test

Used Chi-Square analysis to evaluate relationships between categorical features and survival.

Features analyzed:

- Sex
- Embarked
- Passenger Class
- Title
- Deck

---

# 5. Data Encoding

Categorical features were converted into numerical values using:

- One-Hot Encoding

Applied to:

- Sex
- Embarked
- Title
- Deck

---

# 6. Handling Class Imbalance

Applied:

## SMOTE (Synthetic Minority Oversampling Technique)

SMOTE was used on the training data to balance survivor and non-survivor classes.

---

# 7. Machine Learning Models

The following classification algorithms were trained:

| Model |
|---|
| Logistic Regression |
| Decision Tree |
| Random Forest |
| K-Nearest Neighbors |
| Support Vector Machine |

---

# Model Evaluation

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix
- Classification Report

---

# Results

Final model performance:

| Model | Train Accuracy | Test Accuracy | F1 Score |
|---|---:|---:|---:|
| Logistic Regression | 83.26% | 82.12% | 77.78% |
| Random Forest | 85.99% | 81.56% | 77.24% |
| KNN | 84.51% | 81.56% | 75.56% |
| Decision Tree | 85.42% | 80.45% | 76.82% |
| SVM | 84.16% | 79.89% | 75.67% |

---

# Best Performing Model

Based on the evaluation results:

**Logistic Regression achieved the highest testing accuracy:**

```
82.12%
```

with a balanced performance between precision and recall.

---

# Technologies Used

Python

Libraries:

- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Imbalanced-learn

---

# Project Structure

```
Titanic-Survival-Prediction/

│
├── Titanic.csv
│
├── Titanic_Project.ipynb
│
└── README.md
```

---



Machine Learning Project - Titanic Survival Prediction
