# Diabetes detector: Project Overview 
* Created a tool that detects diabetes (Accuracy ~ 72%) from Pima Indians Diabetes Database.
* Found an important insight about the data: the positive cases are diabetes type 2. 
* Modeling with Random Forest, Balanced Random Forest and XGBoost Classifier. 

## Code and Resources Used 
**Python Version:** 3.6  
**Packages:** pandas, numpy, sklearn, matplotlib, seaborn, xgboost, imblearn.

## Data Cleaning and Standardize
Before using the data, I needed to clean it up so that it was usable for our model. I made the following changes:

*	Convert zero values to the mean of the distribution. There were zero values on important biological variables.
* Removed outliers by the z-score criteria ( > 3 ).
* Standardize data using StandardScaler method from sklearn.

## EDA
I looked at the correlations of the columns and use scatter plot for some relationships. Below are a few highlights. 

![alt text](https://github.com/chrisferreyra13/PredictDiabetes/blob/master/correlation.png "Correlations")
![alt text](https://github.com/chrisferreyra13/PredictDiabetes/blob/master/relationships.png "Relationships")
![alt text](https://github.com/chrisferreyra13/PredictDiabetes/blob/master/insulin_glucose.png "Insulin vs Glucose")

## Model Building 

First, I splitted the data into train and tests sets with a test size of 20%.   

I tried three different models and evaluated them using Accuracy and Matrix confusion.  

Models:
*	**Random Forest**

![alt text](https://github.com/chrisferreyra13/PredictDiabetes/blob/master/cm_rf.png "Random forest confusion matrix")
![alt text](https://github.com/chrisferreyra13/PredictDiabetes/blob/master/rf_report.png "Random forest report")
* Precision and Recall: The model isn't good. Precision of 58% is not safety.

*	**Balanced Random Forest**

![alt text](https://github.com/chrisferreyra13/PredictDiabetes/blob/master/cm_brf.png "Balanced random forest confusion matrix")
![alt text](https://github.com/chrisferreyra13/PredictDiabetes/blob/master/brf_report.png "Balanced random forest report")
* Precision and Recall: Detection of diabetes class is acceptable, but precision is not good.

*	**XGBoost**

![alt text](https://github.com/chrisferreyra13/PredictDiabetes/blob/master/cm_xgb.png "XGBoost confusion matrix")
![alt text](https://github.com/chrisferreyra13/PredictDiabetes/blob/master/xgb_report.png "XGBoost report")
* Warning: 72% of Accuracy but recall and precision is under 70%. 
