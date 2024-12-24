This project focuses on developing machine learning models to predict healthcare utilization and medical expenditures. The models were developed using data from the 2015 Medical Expenditure Panel Survey (MEPS), a comprehensive survey of the U.S. civilian noninstitutionalized population. <br>
**Data Exploration and Preprocessing**
* The dataset included pre-encoded categorical features, but the 'RACE' and 'UTILIZATION' variables needed to be converted to numerical format using LabelEncoder.

* A correlation analysis was performed to identify relationships between features, using a threshold of 0.85 to reduce dimensionality and identify potential multicollinearity.

* The dataset had a significant amount of missing data (35%), with 33% of the data points represented by the code -1.

* Missing data was handled using indicator columns and imputation methods. Discrete features were imputed using the mode, and continuous features were imputed using KNNImputer.

* Outliers were detected and removed using the Interquartile Range (IQR) method.

* Continuous features were scaled using StandardScaler.<br>
**Feature Categorization and Preprocessing**

* Features were categorized into categorical, discrete, and continuous groups for tailored preprocessing.

* Categorical features were one-hot encoded to prevent models from assuming false orderings.

* Indicator columns were created for numerical features to represent missing or inapplicable values.<br>
**Fairness Considerations**

* The project analyzed sensitive features such as RACE, SEX, REGION, and MARITAL STAT using fairness metrics like Demographic Parity, Equal Opportunity, and Equalized Odds.

* Disparities were found in the model's predictions across different demographic groups, indicating potential biases.<br>
**Machine Learning Models**

* Classification: The project used models such as Logistic Regression, XGBClassifier, LightGBM, BaggedSVC, and MLP. LightGBM was the top-performing model, with an F1 Score of 0.917 and a Balanced Accuracy of 0.758.

* Regression: The project used models such as Ridge Regression, XGBRegressor, HistGradientBoosting, BaggedSVM, and MLP. Ridge Regression was the top-performing model, with a Mean RMSE of 11008.40 and MAE of 4789.08.<br>
**Model Selection and Hyperparameter Tuning**

* A nested cross-validation strategy was used to ensure robust model selection and minimize overfitting.

* RandomizedSearchCV was used to optimize hyperparameters for both classification and regression tasks.

* Feature selection was performed using Lasso (L1-Penalty).

* The hyperparameter search space included key parameters such as max depth, min child samples, and num leaves for the LightGBM model and alpha, fit intercept, max iter, and positive for the Ridge Regression model.

* The final model pipelines for both LightGBM and Ridge Regression were constructed using optimized hyperparameters, which are detailed in the report.<br>
**Other Approaches Considered**

* Semi-supervised learning techniques were considered but not implemented due to concerns about overfitting.<br>
**Key Findings**

* The LightGBM model was selected for classification tasks.

* The Ridge Regression model was selected for regression tasks.
