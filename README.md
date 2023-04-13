Predicting Sepsis Risk in ICU Patients
This project develops a machine learning model to predict the risk of sepsis in intensive care unit (ICU) patients. Early prediction of sepsis has significant benefits for both patient outcomes and hospital resource management.

Data
The dataset contains information of patients who have undergone treatment in ICU. There are 11 columns including patient demographic information, vital signs, and blood work results. The target variable is Sepsis, indicating whether the patient developed sepsis during their stay (1 = Sepsis Positive, 0 = Sepsis Negative).

Data cleaning and preprocessing steps included:

Checking for missing values, invalid values and outliers
Imputing missing values using the mean
Encoding categorical variables (Sepsis) using binary encoding
Removing invalid values and outliers outside Q1 - 1.5IQR to Q3 + 1.5IQR
Dropping ID and Insurance columns which have no predictive value
Exploratory Data Analysis
Exploratory analysis revealed:

Most variables exhibit a skewed distribution with PL (1) being the most significant predictor of Sepsis.
No single feature has a clear separation between Sepsis Positive and Negative patients, indicating a multivariate approach is needed.
The data is imbalanced with a 1:2 ratio of Sepsis Positive to Negative cases. Oversampling may be required.
Several variables have a large number of outliers that must be addressed.
No linear correlation above 0.53 between variables; PL (1) is most strongly correlated with Sepsis.
Modeling
Two machine learning models were tested on the data:

Logistic Regression: A univariate model tested with just PL (1) and a multivariate model with all features. L1 and L2 regularization were used to prevent overfitting.
Random Forest: A ensemble method using multiple decision trees. Hyperparameters were tuned using grid search.
Models were evaluated using:

Accuracy, AUC, Sensitivity, Specificity, PPV, NPV, F1 Score
10-fold cross validation
Log loss (for Logistic Regression)
The final tuned Random Forest model achieved an accuracy of 80.17% and AUC of 0.8026 on cross validation.

Conclusions
While both Logistic Regression and Random Forest are viable for predicting Sepsis risk, Random Forest showed superior performance on most metrics. However, test set evaluation is still needed to definitively determine the optimal approach for implementation.

Future work should focus on:

Test set evaluation using new external data
Improving model performance through oversampling, feature selection, ensemble methods or neural networks
Optimizing hyperparameters and modeling techniques
Exploring alternative metrics to maximize, such as precision or positive predictive value
The full report is available in the Report.pdf file. Code is located in the Code.py file. Please let me know if you have any questions!
