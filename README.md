# Data Science portfolio by Nick Sarka
This portfolio is a compilation of notebooks which I created for data analysis. I use separate categories for indicating separate projects.

# Table of Contents

## 1. [Project 1: Home Credit / Loan Default Risk](#Project-1:-Home-Credit-/-Loan-Default-Risk)

# [Project 1: Home Credit / Loan Default Risk](https://github.com/NickSarka2000/MSBA-Repo)
  #### 1. [Introduction](#Introduction)
  #### 2. [Description of the data](#Description-of-the-data)
  #### 3. [Disccusion of the missing data](#Discussion-of-the-missing-data)
  #### 4. [Exploratory visualizations and/or summary tables](#Exploratory-visualizations-and/or-summary-tables)
  #### 5. [Results section](#Results-section)


#### 1. Introduction
In the financial services sector, extending credit presents both an opportunity and a risk. The Home Credit Default Risk project, hosted by Kaggle, aims to address this risk by developing predictive models to assess an applicant's ability to repay loans. Our project leverages data science and machine learning methodologies to create a model that accurately identifies potential defaulters, helping lenders make informed decisions and extend credit responsibly.

#### 2. Business Problem
Home Credit's mission is to expand financial inclusion for the underbanked, who often lack access to traditional banking services due to limited credit history. By leveraging alternative data sources such as transactional and telco information, Home Credit seeks to improve its predictive models to accurately gauge an individual's ability to repay loans. This project aims to develop such models, ensuring fair and equitable access to credit, particularly for underserved communities.

#### 3. Data Description
The dataset comprises seven CSV files detailing various aspects of loan applications and client credit history:

1. **application_train/application_test**: These files contain records of loan applications. The training data includes a TARGET column indicating repayment status (0 for no problems, 1 for problems).
2. **bureau**: Provides information on previous credits from other financial institutions.
3. **bureau_balance**: Contains monthly details on these credits.
4. **previous_application**: Covers past loan applications at Home Credit.
5. **POS_CASH_BALANCE**: Monthly details on past POS or cash loans.
6. **credit_card_balance**: Monthly data on past credit cards.
7. **installments_payments**: Tracks the payment history for previous loans.

#### 4. Data Cleaning and Imputation
Due to extensive missing data in both the train and test datasets, the following strategies were employed:

1. **Row Removal**: Rows with over 50% missing data were removed.
2. **Column Removal**: Columns with over 65% missing data were removed.
3. **Imputation**: Remaining missing data was imputed using iterative techniques for numeric features and one-hot encoding for categorical features.

#### 5. Exploratory Data Analysis (EDA)
The EDA phase provided several key insights:

1. **Class Imbalance**: 91.9% of the loans in the training data were repaid, indicating a significant class imbalance.
2. **Feature Correlations**: Several features showed notable correlations with the target variable:
   - **DAYS_BIRTH** and **AGE_GROUP**: Older applicants tend to have lower default rates.
   - **DAYS_EMPLOYED**: Longer employment duration correlates negatively with default rates.
   - **External Scores**: Scores from external sources negatively correlate with default likelihood.

#### 6. Feature Engineering
To enhance model performance, several new features were engineered:

1. **Yearly Interest Rate**: Calculated by dividing the annual annuity amount by the loan amount.
2. **Income Ratios**: Income-to-annuity and income-to-credit ratios were added.

#### 7. Model Training and Evaluation
We trained a CatBoostClassifier with 5-fold cross-validation, achieving the following results:

- **AUC Score**: 0.7705
- **Accuracy**: 91.98%

These results demonstrate the model's strong discriminative power, aiding in responsible lending decisions.

#### 8. Results
The model's performance highlights its utility in differentiating between likely defaulters and reliable borrowers. This work supports Home Credit's mission by ensuring accurate and fair assessments of creditworthiness, contributing to inclusive financial services.

#### 9. Lessons Learned
This project taught us the importance of:

1. **Handling Missing Data**: Removing rows and columns with excessive missing values and applying imputation strategically.
2. **Feature Selection and Engineering**: Selecting relevant features and creating new ones can greatly improve model performance.
3. **Understanding Business Context**: Thoroughly understanding the business problem ensures that the data analysis and model development align with real-world needs.

#### 10. Project Contributors
Our team's contributions include:

- Data cleaning, exploration, and visualization
- Feature engineering and model development
- Evaluation and interpretation of results

#### 11. Conclusion
This project has shown that predictive modeling can significantly enhance the ability of financial institutions to lend responsibly, while also promoting financial inclusion by accurately assessing creditworthiness. This work underscores the impactful role of data science in advancing equitable financial services.
