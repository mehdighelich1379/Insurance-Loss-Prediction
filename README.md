*** Insurance Claim Prediction using CatBoost ***

1) ## Objective
The goal of this project was to predict insurance claims based on various features in the dataset. The project used CatBoost to handle categorical and continuous features efficiently without requiring manual label encoding or one-hot encoding. The main focus was on improving the prediction accuracy by transforming the target variable and utilizing advanced machine learning techniques.

2) ##  Dataset:
The dataset used for this project is train.csv, which contains various features related to insurance claims. The dataset includes both categorical and continuous features that describe the policies and claims.

3) ##  Dataset Features:
categorical features: Features that represent categories, like policy type, region, etc.
continuous features: Numerical features, such as the claim amount, age, and other variables.

###  Steps Taken in the Project:

4) ##  Exploratory Data Analysis (EDA):
I performed an initial EDA to explore the structure of the data, identify missing values, outliers, and visualize the relationships between the features and target variable (insurance claims).
Handling Categorical and Continuous Features:
To avoid manually using label encoding or one-hot encoding, I used the CatBoost algorithm which can natively handle categorical features without any need for preprocessing.
I utilized the re library to automatically identify the categorical and continuous features in the dataset.

5) ##  Data Splitting:
I split the data into training and testing sets using a typical 70/30 ratio to ensure proper model validation.
Initial Model Building with CatBoost:
I used CatBoost for the initial model building. While the first Mean Absolute Error (MAE) was high, the model provided a good baseline.

6) ##  Target Transformation:
To reduce the error, I applied a logarithmic transformation on the target variable (insurance claims) to stabilize variance and make the model fit more effectively.
The column with the claim amount was transformed using the natural logarithm and passed as the target variable y.
y = np.log(y) 

7) ##  Re-training the Model:
After transforming the target, I retrained the model with CatBoost. This led to a significant decrease in MAE, showing that the transformation helped improve the model’s performance.

8) ##  Final Prediction:
After obtaining the predictions, I applied np.exp to the results to revert the logarithmic transformation and obtain the final predicted values for the insurance claims.
y_pred = np.exp(y_pred_log) 

9) ##  Results:
The initial model built with CatBoost resulted in a MAE that was relatively high.
After transforming the target variable using logarithmic transformation, the MAE decreased significantly to 1.5 dollars, which is a considerable improvement.
The final model effectively predicted insurance claims with reduced error, thanks to CatBoost's handling of categorical

10) ## Model Comparison:
- Random Forest: High MAE, not as effective as CatBoost.
- XGBoost: Good performance, but CatBoost outperformed in terms of speed and accuracy.
- CatBoost: Achieved the best performance with a MAE of 1.5 dollars, making it the optimal choice for this project.

11) ##  Conclusion:
By combining CatBoost with advanced techniques such as automatic feature handling, logarithmic transformation of the target variable, and careful preprocessing, I was able to significantly reduce the error in predicting insurance claims. The final model is efficient and demonstrates how targeted data transformations and algorithmic features can greatly improve predictive performance.

12) ##  Techniques Used: 
CatBoost, Target Transformation (Logarithmic Transformation), EDA, Feature Engineering.
Performance: Reduced MAE after target transformation, improving model prediction accuracy.

13) ##  Skills:
Data Preprocessing, Model Evaluation, Machine Learning, Feature Engineering, CatBoost.
