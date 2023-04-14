# Survival Analysis and Prediction for Patients suffering from Brain Metastatic Cancer

#### Team
[Young Zeng](github.com/youngzyx), [Anish Mukherjee](https://github.com/anmuai)

## 1. Dataset

Tabular data of patients suffering from Brain Metastatic Cancer and clinical attributes of the patients such as Age, Sex etc.

The target variable was time of death 

## 2. Survival Analysis
### 2.1 Movivation

This project was executed as a part of our internship at UCSF. Superduto et all developed a clinical methodology(Diagnosis-specific Graded Prognostic Assessment) to segment patients by the severity of cancer so that they have well-separated survival times and develop an estimated time for each patient. However, for UCSF patients, we observed the following:

1) Patients lived far longer than predicted 
2) There was a significant overlap in the patient survival times between the GPA classes.

Our objective was to show that the old model did not fit the observed data, and develop a new model. 


### 2.2 Model

We used a `decision tree` model to predict the time of death. The predictions from the model were used to decide which classes the patient belonged to. For instance, if the tree predicted two leaves, the patient belonging to the leaf node with a lower mean survival time would be assigned class zero and the patient belonging to the other leaf node class one.

We then fit a `Kaplan Meier Survival curve` on the classes produced to see a graphical/statistical separation of survival times.

#### 2.2.1 For Lung cancer

- Original
<img src = 'images/Lung_old.png' width = '500'>


-  Our Model: 3 Classes
<img src = 'images/Lung_3class.png' width = '500'>

## 3. Survival Prediction

Besides the traditional survival analysis above, we also use machine learning models for survival prediction. [Random Forest](https://github.com/youngzyx/Survival-Analysis-and-Prediction/blob/main/notebooks/Random_Forest.ipynb) models and [XGBoost](https://github.com/youngzyx/Survival-Analysis-and-Prediction/blob/main/notebooks/xgb.ipynb) models had been constructed toward the following target variables:

1. survival time (regression)
2. 1-year survival (classification)
3. 2-year survival (classification)

### 3.1 Results
#### 3.1.1 Random Forest Model
For Random Forest model, we use out of bag (OOB) $R^2$ for regressor or OOB score for classifier.

- Target: Survival Time (Regressor)
|Tumor Site|Sample size|OOB $R^2$/score|Feature|
|:---------|:-------------:|:-----------:|------:|
|Breast|307|0.036|All|
|Breast|307|-0.018|Top 5|
|Melanoma|309|0.036|All|
|Melanoma|309|-0.037|Top 5|
|Lung|502|0.066|All|
|Lung|502|0.047|Top 5|
|Kidney|74|-0.013|All|
|Kidney|74|-0.037|Top 5|
