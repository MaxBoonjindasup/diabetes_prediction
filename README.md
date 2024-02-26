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

| Category          | Amount of Individuals | % of Individuals |
|-------------------|-----------------------|------------------|
| Normal Female     | 51,714                | 53.8             |
| Normal Male       | 35,932                | 37.4             |
| Diabetic Female   | 4,447                 | 4.6              |
| Diabetic Male     | 4,035                 | 4.2              |

![](https://github.com/MaxBoonjindasup/diabetes_prediction/blob/main/blood_glucose.png)

![](https://github.com/MaxBoonjindasup/diabetes_prediction/blob/main/age_vs_bmi.png)

![](https://github.com/MaxBoonjindasup/diabetes_prediction/blob/main/diabetes_bmi_sex.png)

## Model Building
1. Label encoded categorical variables: gender & smoking history
2. Partitioned data into train-test split (20% test size)
3. Balanced dataset by upsampling minority class (91.2% Normal class vs 8.8% Diabetic class)
4. Trained Logistic Regression, Random Forest, and Gradient Boosting models

## Results
**Gradient Boosting** stood out with its ability to identify the most diabetic patients (*highest recall of 92%*). Additionally, it demonstrated strong overall performance (*highest AUC of 91%*).

![](https://github.com/MaxBoonjindasup/diabetes_prediction/blob/main/confusion_matrix_gradient_boosting.png)

| Model               | Precision | Recall | F1 Score |
|---------------------|-----------|--------|----------|
| Logistic Regression | 0.39      | 0.86   | 0.54     |
| Random Forest       | 0.85      | 0.69   | 0.76     |
| Gradient Boosting   | 0.48      | 0.92   | 0.63     |

![](https://github.com/MaxBoonjindasup/diabetes_prediction/blob/main/roc_curve.png)
