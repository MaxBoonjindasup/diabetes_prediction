# Diabetes Prediction
Full breakdown on [Kaggle](https://www.kaggle.com/code/maxboonjindasup/diabetes-prediction).

## Introduction
Diabetes, with its potential for severe health complications, represents a significant challenge for individuals and a substantial economic burden on healthcare systems. Early identification not only improves health outcomes but also presents a strategic business opportunity. Proactive management reduces healthcare costs and fosters a healthier patient population. This dual impact of improving health outcomes and optimizing healthcare economics underscores the compelling business case for leveraging machine learning in diabetes identification and management.

Here I present 2 models trained off of 100,000 entries encompassing the following medical and demographic details:

| #   | Feature              |
| --- | -------------------- |
| 1   | gender               |
| 2   | age                  |
| 3   | hypertension         |
| 4   | heart_disease        |
| 5   | smoking_history      |
| 6   | body mass index (BMI)|
| 7   | HbA1c_level          |
| 8   | blood_glucose_level  |
| 9   | diabetes             |

## EDA

![](https://github.com/MaxBoonjindasup/diabetes_prediction/blob/main/age_vs_bmi.png)

![](https://github.com/MaxBoonjindasup/diabetes_prediction/blob/main/blood_glucose.png)

![](https://github.com/MaxBoonjindasup/diabetes_prediction/blob/main/diabetes_bmi_sex.png)

## Model Building
1. Label encoded categorical variables: gender & smoking history
2. Partitioned data into train-test split (20% test size)
3. Balanced dataset by upsampling minority class (91.2% Normal class vs 8.8% Diabetic class)
4. Trained Random Forest and Gradient Boost models (GB results shown below) and compared performances

![](https://github.com/MaxBoonjindasup/diabetes_prediction/blob/main/confusion_matrix_gradient_boosting.png)

|               | Precision | Recall | F1-Score | Support |
|--------------|-----------|--------|----------|---------|
| Non-Diabetic |   0.99    |  0.90  |   0.94   | 17,525  |
|   Diabetic   |   0.48    |  0.92  |   0.63   |  1,701  |
|    Accuracy  |           |        |   0.90   | 19,226  |
|  Macro Avg   |   0.73    |  0.91  |   0.79   | 19,226  |
| Weighted Avg |   0.95    |  0.90  |   0.92   | 19,226  |

![](https://github.com/MaxBoonjindasup/diabetes_prediction/blob/main/roc_curve_gradient_boosting.png)
