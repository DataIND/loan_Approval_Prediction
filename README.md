# loan_Approval_Prediction


Overview - 
This repository contains a machine learning project aimed at predicting loan approval outcomes based on various applicant features. The project utilizes advanced classification algorithms, specifically LightGBM and CatBoost, to analyze the relationship between input features and the target variable, which indicates whether a loan is approved or not.




Dataset - 
The dataset used in this project was generated from a deep learning model trained on the original Loan Approval Prediction dataset. While the feature distributions are similar to the original dataset, they are not identical. Users are encouraged to explore the original dataset to understand the differences and assess whether incorporating it into the training process improves model performance.


Methodology :- 

1. Data Preparation: The dataset is preprocessed and scaled to ensure that all features are on a similar scale, which is crucial for the performance of many machine learning algorithms.
2. Model Selection: Two classification models are employed:
LightGBM: A gradient boosting framework that uses tree-based learning algorithms.
CatBoost: A gradient boosting library that is particularly effective with categorical features.
3. Cross-Validation: Stratified K-Fold cross-validation is used to ensure that each fold of the training and validation sets maintains the same proportion of classes as the original dataset. This helps in obtaining a more reliable estimate of model performance.
4. Model Training:
For LightGBM, the model is trained with specific hyperparameters, including n_estimators, learning_rate, and max_depth. The model is evaluated using the AUC metric.
For CatBoost, the model is trained with its own set of hyperparameters, including depth, learning_rate, and iterations, also evaluated using the AUC metric.
5. Predictions: The models generate predictions for both the validation and test datasets. The predictions are stored for further analysis.
Combining Predictions: The final loan approval status is determined by combining the predictions from both models. The formula used is:
python

Copy Code
df_sub['loan_status'] = lgbm_test_predictions * 0.2 + catboost_test_predictions * 0.8
This weighted average gives more importance to the CatBoost model's predictions, reflecting its performance in the validation phase.



Results :- 
The results of the predictions from both models can be analyzed to determine the effectiveness of each approach. The performance metrics, such as AUC, can be compared to assess which model provides better predictive accuracy.

Conclusion :- 
This project demonstrates the application of advanced machine learning techniques for predicting loan approval outcomes. The use of LightGBM and CatBoost allows for effective handling of complex datasets, and the results can be further improved by hyperparameter tuning and feature engineering.

Usage :-
To run this project, ensure you have the necessary libraries installed, including LightGBM and CatBoost. You can clone this repository and execute the provided scripts to replicate the results.


