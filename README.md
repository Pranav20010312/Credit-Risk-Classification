# 🏦 Credit Risk Classification

## 📌 Problem Statement

Credit risk modeling is a critical area in finance that helps institutions assess the risk of lending to individuals or businesses. In this project, is to build a machine learning model to predict the likelihood of a borrower defaulting on a loan, based on historical loan data.

## 🧰 Technologies & Tools Used

- **Python**
- **Pandas, NumPy** – Data Manipulation
- **Matplotlib, Seaborn** – Visualization
- **Scikit-learn** –  To build Machine Learning Models
- **XGBoost** – Gradient Boosting 
- **Optuna** – Hyperparameter Tuning
- **Imbalanced-learn** – Handling Class Imbalance (SMOTE-Tomek, Under-sampling)
- **Statsmodels** – VIF Calculation
- **Weight of Evidence /Information Value  Analysis** – Feature selection for categorical variables

## 🧪 Project Workflow

### 1. 🧼 Data Leakage Prevention
- Performed **train-test split before EDA** to ensure that the test set does not influence decisions during EDA and feature engineering.

### 2. 🧹 Data Cleaning
- Handled **missing values** using **mode imputation**.
- **No duplicate entries** found.
- Used **boxplots** to detect outliers.

### 3. 📊 Exploratory Data Analysis (EDA)
- Performed **bivariate analysis** using the target column.
- Used **KDE plots** to observe patterns.
- Identified strong predictors:
  - `loan_tenure_months`
  - `delinquent_months`
  - `total_dpd`
  - `credit_utilization`
- These variables showed clear separability for defaulters.
🔍 Features like `loan_amount` and `income` did not show strong individual signals, but combining them into **Loan-to-Income (LTI) ratio** proved insightful.

### 4. 🛠️ Feature Engineering
- Generated new features likely to impact credit risk:
  - **Loan to Income (LTI) Ratio**
  - **Delinquency Ratio**
  - **Average DPD per Delinquency**

### 5. 🎯 Feature Selection & Encoding
- Dropped irrelevant or redundant features.
- Used **VIF (Variance Inflation Factor)** to detect multicollinearity in numerical features.
- Applied **Min-Max Scaling** to normalize numerical data.
- For categorical features:
  - Used **WOE (Weight of Evidence)** and **IV (Information Value)** for selection.
  - Applied **One-Hot Encoding** to selected features.
 
## 6. 🤖 Model Training

### Models Trained:
- **Logistic Regression**
- **Random Forest**
- **XGBoost Classifier**

### Handling Imbalanced Classes:
- Applied **under-sampling** and **SMOTE-Tomek** techniques to handle imbalance in the dataset.
- Compared performance of models under different balancing techniques.


## 7. 🛠️ Model Fine-Tuning

- Used **Optuna**, a powerful hyperparameter optimization framework.
- Efficiently tuned model parameters to achieve optimal performance.

8. ## 📈 Evaluation Metrics

-Accuracy: Correctly predicted instances

-Precision: Proportion of positive predictions that are correct

-Recall: Proportion of actual positives that were predicted

-F1 Score: The harmonic mean of Precision and Recall

-AUC-ROC Curve: Measures the ability to distinguish between classes

-Gini Coefficient: Shows how well the model is performing 

 -**AUC of 0.98**: Indicates excellent separation of defaulters from non-defaulters  
-**Gini Coefficient of 0.96**: Suggests strong rank ordering and predictive power

## 📊 Results
The model exhibits **high recall** and **lower precision**, which aligns with the business goal of minimizing financial risk. In credit risk modeling, **recall is more important**, as failing to identify a defaulter (false negative) is more costly than incorrectly flagging a good borrower (false positive).

The machine learning model achieves a **high level of accuracy**  in predicting credit risk. Among the algorithms tested, **Logistic Regression** emerged as the best choice due to its balance of performance and interpretability.

## 💼 Business Impact
-Reduces default risk by accurately identifying high-risk borrowers, helping minimize financial losses.
-Improves loan portfolio quality by ensuring approved borrowers are more likely to repay.

