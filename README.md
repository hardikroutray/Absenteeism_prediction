This module tries to predict excessive absenteeism at office given a set of features using various supervised learning techniques. The problem initially appeared on Udemy data science course and this module tries to solve the problem and predict absenteeism as accurately as possible. Given the original dataset is balanced, accuracy is used as a model-optimizing measure here though precision and recall are also evaluated for each model considered in the module. Depending on the business purpose, different measures can be used for model selection. 

## Problem Statement 

Based on employee survey and internal office data, absenteeism time in hours is obtained alongwith various other attributes relating to the absence and the person. Some particular features are distance to work, age, transportation expense, daily average work load, body mass index, education, children, pets, as well as reasons for absence. Can we predict excessive absenteeism given the data?

## Brief note on pre-processing 

The targets are labelled one (or zero) depending on whether the absenteeism time in hours is more (or less) than the median value. Imputation of missing values is also performed. Categorical features are used to make dummy variables. Multicollinearity affects the coefficients and p-values, but it does not influence the predictionsor precision of the predictions. However, since we are also interested in the coefficients (for feature importance), we also reduce correlated columns by simple removal, linearly combining them or using PCA. Reasons for absence are broadly grouped into 4 categories (Reason - 1 for diseases, Reason - 2 for pregnancy related issues, Reason - 3 for medical appointments, Reason - 4 for rest all). Standardization is also done on the columns prior to model fitting.  

## Final remarks 

Logistic regression, boosted decision tree, random forest, k-nearest neighbor, naive bayes models are implemented after performing grid search cross-validation. Feature importances are studied to identify major contributing causes so that those employee pain points can be addressed.

Check model_exploration notebook for details on the model fitting. An absenteeism class performing ETL and returning predictions for a trained model has also been created for simplicity can be seen in the integration notebook. 