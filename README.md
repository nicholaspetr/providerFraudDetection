# providerFraudDetection
Health Analytics Final Project. Team 5: Nicholas Petr, Dylaan Cornish, Sid Reddy. Classification problem attempting to identify provider fraud via claims analysis. This GitHub repository contains the following scripts used for the project: 

The previousIterations folder includes code used to develop the final copies of code used for the project, which includes all code files in the maian providerFraudDetection folder.

DataCleaning: Imports, merges, and cleans training datasets. This includes beneficiary, inpatient, outpatient, and fraud indicator datasets. 

EDA: Imports cleaned and merged dataset output from the DataCleaning script for the purpose of exploratory data analysis. This includes fraud indicator distribution, fraudulent claims broken out by state, number of claims by amount reimbursed, distribution of deductible amount paid, distribution of inpatient stay duration, feature correlation heatmap, and distribution of patient race.

Preprocessing + Feature Engineering3: Imports cleaned and merged dataset output from the DataCleaning script and the Fraud indicator training dataset for the purpose of data preprocessing and feature engineering. This includes generation of mean, median, and maximum columns for several numeric features, imputation of features with NA values, conversion of categorical data to numeric data, addition of features of interest, and identification/selection of features to be used in modeling. Features with a correlation with fraud > .20 were selected for modeling.

ModelBuilding_FinalProject_v2-withSMOTE: Imports finalized training dataset from the Preprocessing + Feature Engineering3 script for the purpose of building and comparing models. First, we split the training data 80-20. Each model will test on the 20%, and the model that performs the best on that set will be used on the actual test set. We then run the training data through SMOTE to address the imbalanced dataset. For each model, we create set of model parameters to iterate through and find the best set of parameters to fit the 80% training data, determined by lowest RMSE values. We then save those models to a pickle file, using the first three models as inputs to the voting regressor model. Each model is then run through the test dataset and scored using several different metrics. The following models were tested: Decision Tree, K-Nearest Neighbors Regression, Random Forest, XGBoost, CatBoost, and Voting Regressor. 

ModelBuilding_FinalProject_v2: This includes the same logic found in the ModelBuilding_FinalProject_v2-withSMOTE script, but does not run the training dataset through SMOTE. 
