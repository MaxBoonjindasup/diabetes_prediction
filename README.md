# Diabetes Prediction
Full breakdown on [Kaggle](https://www.kaggle.com/code/maxboonjindasup/diabetes-prediction).

## Introduction
Diabetes affects 537 million people globally, straining healthcare systems with costs exceeding $760 billion annually in the US alone. Studies indicate that early detection reduces complications by 50%, dramatically improving patient care. Further, leveraging machine learning for diabetes identification and management presents a path to significantly enhance health outcomes and reduce healthcare costs.

Here I present 3 models trained off of 100,000 entries encompassing the following medical and demographic details:

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
4. Trained Logistic Regression, Random Forest, and Gradient Boost models

## Results
Performance Criteria:
1. Highest recall (because detecting all the diabetic patients is the aim)
2. Highest AUC (indicative of best performing model)

Best Performing Model: **Gradient Boost (shown below)**

![](https://github.com/MaxBoonjindasup/diabetes_prediction/blob/main/confusion_matrix_gradient_boosting.png)

|               | Precision | Recall | F1-Score | Support |
|--------------|-----------|--------|----------|---------|
| Non-Diabetic |   0.99    |  0.90  |   0.94   | 17,525  |
|   Diabetic   |   0.48    |  0.92  |   0.63   |  1,701  |
|    Accuracy  |           |        |   0.90   | 19,226  |
|  Macro Avg   |   0.73    |  0.91  |   0.79   | 19,226  |
| Weighted Avg |   0.95    |  0.90  |   0.92   | 19,226  |

![](https://github.com/MaxBoonjindasup/diabetes_prediction/blob/main/roc_curve.png)
