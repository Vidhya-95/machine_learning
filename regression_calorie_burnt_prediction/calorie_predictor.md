# Regression_Calorie_Burnt_Prediction

> Objective : Predict calories burnt during physical activity, comparing multiple model's accuracy through systematic feature engineering on physiological attributes such as age, weight, heart rate, and exercise duration.

---

## 📌 Table of Contents
- [Project Overview](#project-overview)
- [Problem Statement](#problem-statement)
- [Dataset](#dataset)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Feature Engineering](#feature-engineering)
- [Modeling](#modeling)
- [Evaluation Metrics](#evaluation-metrics)
- [Results](#results)
- [Future Work](#future-work)
- [Author](#author)

---

## Project Overview

<!-- Provide a brief summary of the project. What are you predicting? What is the business or research motivation? -->

**Goal:** Predict `calories burnt` using `Gender,Age,Height,Weight,Duration,Heart_Rate,Body_Temp`.

**Type:** Supervised Learning — Regression

**Domain:** `Healthcare`

---

## Problem Statement

<!-- Describe the problem clearly. What question are you trying to answer? -->

> *"Given data on person's physical feature and activity, can we accurately predict the calories burnt?"*

- **Input:** `[Gender,Age,Weight,Duration,Heart_Rate,Body_Temp]`
- **Output:** `[Calories]`

---

## Dataset

| Property         | Details                            |
|------------------|------------------------------------|
| **Source**       | `Custom`    |
| **Size**         | `15000 rows × 9 columns`             |
| **Target**       | `Calories-Continuous range of values of calories burnt`    |


### Key Features
| Feature Name | Type | Description |
|--------------|------|-------------|
| `feature_1`  | Numerical | `[Description]` |
| `feature_2`  | Categorical | `[Description]` |
| `...`        | ...  | ... |

---

## Exploratory Data Analysis

<!-- Summarize your EDA findings. Add plots or links to notebooks. -->

### Key Findings
- `As the duration increases the calories burnt increases`
- `Same is the trend observed with heart rate and body temperature`
- `Both height and weight have similar impact`

### Visualizations
| Plot | Insight |
|------|---------|
| Distribution of `Calories` | `There is not much difference based on gender, duration plays a important role` |
| Correlation Heatmap | `The duration has high correlation with calories which might lead to data leakage - our model will perform well for training dataset but will fail to apply on real world usecases.` |

---

## Feature Engineering

<!-- Describe any transformations, new features, or encodings applied. -->

- **Missing Value Strategy:** `Since it is a clean dataset, no missing value is present.`
- **Encoding:** `One-Hot Encoding-Applied on Gender column`
- **Scaling:** `StandardScaler applied to numerical features`
- **New Features Created:**
  - `Gender_male = Derived from one hot encoding`
- **Features Dropped:** 
   - `Both height and weight have similar impact-we can drop one of these columns`
   - `Duration - dropped due to data leakage`

---

## Modeling

### Models Tried
- Linear Regression,Ridge and Lasso

### Hyperparameter Tuning
- **Method:** `GridSearchCV `
<!-- - **Best Parameters:**
```python
best_params = {
    "param_1": value,
    "param_2": value,
    # add yours
}
``` -->

---

## Evaluation Metrics

| Metric | Description |
|--------|-------------|
| **MSE** | Mean Squared Error | 
| **R² Score** | Coefficient of Determination | 


---

## Results

### Model Comparison
| Model | Test RMSE |  Test R² |
|-------|-----------|----------|
| Linear Regression | `0.8708` | `521.36` | 
| Ridge | `0.8707` | `521.47` | 
| Lasso | `0.8708` | `521.36` | 

<!-- ### Best Model Summary
- **Model:** `[Model name]`
- **Test RMSE:** `[Value]`
- **Test R²:** `[Value]`
- **Key Insight:** `[What did you learn from the best model?]` -->

<!-- ### Feature Importance
> _(Add a feature importance chart or table here)_

| Feature | Importance Score |
|---------|-----------------|
| `feature_1` | `0.XX` |
| `feature_2` | `0.XX` | -->


---

## Future Work

- [ ] `Implement XGBoost`
- [ ] `Determine which model works the best`


---

## Author

**Vidhya Shinde**
- GitHub: [@Vidhya-95](https://github.com/Vidhya-95)
- LinkedIn: [vidhya-shinde](https://linkedin.com/in/vidhya-shinde)
- Email: `your.email@example.com`

---

