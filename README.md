# ICU-Mortality-Risk-Prediction

### Summary and Recommendations

#### 1. Overview

This project aims to predict heart disease based on patient data such as blood pressure, cholesterol levels, age, etc. 

#### 2. Steps

1. Data Loading: The heart disease dataset is loaded from a zip file.

2. Data Cleaning: Missing or erroneous values (like 0 in RestingBP and Chohttps://github.com/MiltonGreat/ICU-Mortality-Risk-Prediction/tree/mainlesterol) are replaced with the median value of their respective columns.

3. Feature Engineering: Categorical variables like Sex, ChestPainType, RestingECG, etc., are transformed using one-hot encoding, creating binary columns.

4. Data Preprocessing: Data is split into features (X) and target labels (y) and is then split into training and test sets (80% training, 20% testing). The features are scaled using StandardScaler to improve the model's performance.

5. Model Training: Three models—Logistic Regression, Random Forest, and Support Vector Machine (SVM)—are trained on the training data.

6. Model Evaluation: The performance of each model is evaluated using several metrics, including:

- Accuracy: How often the model correctly predicts heart disease.
- Precision: Of the patients the model predicted as having heart disease, how many actually had heart disease.
- Recall: Of the patients who had heart disease, how many were correctly identified by the model.
- F1-Score: The harmonic mean of precision and recall.
- AUC (Area Under the Curve): A measure of the model's ability to distinguish between classes.

7. ROC Curves: The Receiver Operating Characteristic (ROC) curve is plotted for each model to show the trade-off between the true positive rate (sensitivity) and false positive rate.

8. Hyperparameter Tuning: Random Forest is optimized using GridSearchCV to find the best parameters (e.g., number of estimators, maximum depth, etc.).

9. Feature Importance: The importance of each feature in Random Forest is plotted, showing which features contribute most to the model's predictions.

10. Model Persistence: The best model is saved to a file using joblib for future use.

#### 3. Key Findings
      
- Overall Churn Rate: 26.54%.
- Churn Rate by Contract Type: Month-to-month contracts show the highest churn (42.7%), while two-year contracts have the lowest churn (2.8%).
- Churn Rate by Payment Method: Electronic check payments are associated with a much higher churn rate (45.3%) compared to automatic payment methods.
- Churn Rate by Internet Service: Fiber optic customers have the highest churn rate (41.9%), while those with no internet service have the lowest (7.4%).
- All models achieved an accuracy of around 85-86%. This suggests that the data contains meaningful patterns for predicting heart disease.
- Logistic Regression, Random Forest, and SVM all performed similarly in terms of accuracy, precision, recall, and F1-score.
- The ROC curves showed that the models are able to distinguish between positive and negative classes fairly well, with AUC scores close to or above 0.90 for all models.
