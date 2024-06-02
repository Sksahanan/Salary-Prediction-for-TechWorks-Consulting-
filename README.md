# Salary-Prediction-for-TechWorks-Consulting-
**Goal:** The task at hand is to develop a machine learning model that can predict the salary of potential new hires at TechWorks Consulting. This model will be used to streamline the recruitment process by providing an initial estimate of a candidate's expected salary based on their qualifications and experience

**Approach:** 

1. Data Preprocessing:
   Clean and prepare data: This involves transforming categorical features like "College Name" and "City" into numerical representations. For example, college tiers can be assigned numerical values (Tier1 = 3, Tier2 = 2, Tier3 = 1) to reflect their reputation. Similarly, city types can be encoded as binary values (Metro = 1, Non-Metro = 0) to account for cost-of-living differences.  

   The "Role" feature can be transformed using one-hot encoding, creating dummy variables for each job position (e.g., Manager, Executive) to capture the varying salary ranges associated with different roles. We will also identify and address outliers in numerical features like "Previous CTC" and "Experience in Months" using techniques like z-scores or IQR (Interquartile Range).  

   Depending on the impact and business context, we will choose a suitable method (winsorization, capping, or removal) for handling outliers. Finally, we will address missing values in any features using techniques like mean/median imputation or more advanced methods like k-Nearest Neighbors (KNN) imputation, considering the nature of the missing data and the feature itself. 

2. Feature Selection:

   After data preprocessing, we will employ feature selection techniques to identify the most relevant features for salary prediction. This can be done using correlation analysis to assess the strength of linear relationships between features and salary. We can also leverage feature importance scores from models like Random Forest or use Lasso regularization, which performs feature selection by shrinking coefficients to zero, resulting in a sparse model with fewer features. By selecting the most relevant features, we can reduce model complexity and potentially improve prediction accuracy. 

3. Model Training and Evaluation:

   We will train and evaluate various regression models suitable for this task. Some potential options include Linear Regression, Ridge Regression, Lasso Regression, Decision Tree Regression, Random Forest Regression, Gradient Boosting Machine Regressor, and XGBoost. Each model has its strengths and weaknesses, so we will use metrics like Mean Squared Error (MSE), R-Squared (R²), and Adjusted R-Squared to compare model performance and select the one that delivers the most accurate salary predictions. Additionally, when dealing with many features, we may consider metrics like AIC (Akaike Information Criterion) for model selection. 

4. Model Tuning: Once we choose the best model, we'll fine-tune its settings to improve accuracy. This involves adjusting hyperparameters that control how the model learns. 

**Benefits:** 
Streamline recruitment by providing initial salary estimates. Offer competitive salaries while staying within budget constraints. Make data-driven decisions during the hiring process. 

**Key Insights** 

* Analysis of Machine Learning Models for Salary Prediction 

  1. Top Performers: Random Forest (Test R²: 0.66) and Gradient Boosting (Test R²: 0.63) achieved the highest accuracy on unseen data (test set) based on R² score.
  2. Reason for the top performance: Random Forest is an ensemble model that combines multiple decision trees, reducing variance and handling non-linear relationships between features and salary better than linear models. It can capture complex interactions between features without overfitting as easily as single decision trees.
  3. Overfitting: XGBoost models (1.0 & 0.99 Train R², 0.59 & 0.52 Test R²) overfit the training data, performing poorly on unseen data.
  4. Regularization: Ridge & Lasso Regression (Test R²: 0.53) show promise but might benefit from feature selection and tuning.
  5. Multi-Linear Regression: Investigate training issues (missing R² score) to potentially improve its performance. 
