# Predicting Stroke Risk Using Machine Learning Models

## Project Overview

Stroke is a significant global health issue, contributing to substantial morbidity and mortality. This project aims to develop a predictive model to assess stroke risk by analyzing healthcare data, including demographics, lifestyle, and medical history. By leveraging machine learning techniques, the project seeks to uncover key risk factors and support proactive healthcare management.

## Objectives

- **Analyze the dataset**: Identify factors contributing to stroke occurrences.
- **Preprocess the data**: Ensure high quality and relevance of the dataset.
- **Build machine learning models**: Create reliable predictive systems with high accuracy.
- **Deliver actionable insights**: Provide tools to support stroke prevention strategies.

## Dataset Overview

- **Features**: Gender, age, hypertension, heart disease, marital status, work type, residence type, average glucose level, BMI, smoking status, and stroke status (target variable).
- **Size**: 5,110 records with 12 features.
- **Target Variable**: `stroke` (1 = stroke, 0 = no stroke).

## Data Preprocessing

### Key Steps

1. **Exploration**:
   - Identified missing values in the `bmi` column (~3.93%).
   - Removed duplicates (none found).
   - Analyzed stroke rates by gender.

2. **Handling Missing Values**:
   - Option 1: Dropped rows with missing `bmi` values (reduced dataset to 4,909 rows).
   - Option 2: Imputed missing `bmi` values using the mean (28.89).

3. **Data Encoding**:
   - Binary encoding for `Residence_type` and `ever_married`.
   - One-hot encoding for `gender`, `work_type`, and `smoking_status`.

4. **Final Dataset**:
   - Transformed all categorical features into numeric for machine learning compatibility.

## Data Visualization

- **Age Distribution**: Bimodal with peaks at 40–60 and 80 years.
- **Hypertension and Stroke**: Most hypertensive patients did not have a stroke.
- **BMI vs. Glucose Levels**: Stroke patients cluster at higher glucose levels.
- **Age, Glucose, and BMI Interaction**: Stronger correlation with stroke for age and glucose than BMI.

## Model Training and Evaluation

### Models Used

1. **Linear Regression**
   - Accuracy: 9.10%
   - RMSE: 22.76%
   
2. **Lasso Regression**
   - Accuracy: 0.94%
   - RMSE: 23.76%
   
3. **Ridge Regression**
   - Accuracy: 9.10%
   - RMSE: 22.76%
   
4. **Logistic Regression** (Best performing model)
   - Accuracy: 93.93%
   - Precision: 0.50
   - Recall: 0.02
   - F1 Score: 0.03

### Key Observations

- **Class Imbalance**: Stroke cases form only 5% of the dataset.
- **Logistic Regression**:
  - Performs well on non-stroke predictions.
  - Fails to detect stroke cases (low recall and F1 score).
- **Precision-Recall Curve**: Shows limited predictive power (AP = 0.16).

## Recommendations

1. **Address Class Imbalance**:
   - Use SMOTE or undersampling techniques.
2. **Focus on Relevant Metrics**:
   - Prioritize precision, recall, and F1 score over accuracy.
3. **Improve Model Performance**:
   - Experiment with Gradient Boosting or class-weighted logistic regression.
4. **Expand Feature Analysis**:
   - Investigate additional factors influencing stroke risk.

## Conclusion

Logistic Regression demonstrates high accuracy but struggles with stroke case detection due to class imbalance. To build an effective predictive system, addressing imbalance and focusing on minority class metrics is critical.

---

## Future Work

- Explore advanced algorithms (e.g., XGBoost, Random Forest).
- Perform hyperparameter tuning.
- Integrate additional datasets for enhanced predictions.

---

## Acknowledgments

This project was developed as part of a comprehensive effort to leverage machine learning for healthcare improvements.

---
