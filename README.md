# Data Science portfolio by Nick Sarka
This portfolio is a compilation of notebooks which I created for data analysis. I use separate categories for indicating separate projects.

# Table of Contents

## 1. [Project 1: Home Credit / Loan Default Risk](#Project-1:-Home-Credit-/-Loan-Default-Risk)

## 2. [Project 2: CocaCola Swire Case Competition](#Project-2:-CocaCola-Swire-Case Competition)

# [Project 1: Home Credit / Loan Default Risk](https://github.com/NickSarka2000/MSBA-Repo)

## 1. Introduction
In the financial services sector, extending credit presents both an opportunity and a risk. The Home Credit Default Risk project, hosted by Kaggle, aims to address this risk by developing predictive models to assess an applicant's ability to repay loans. Our project leverages data science and machine learning methodologies to create a model that accurately identifies potential defaulters, helping lenders make informed decisions and extend credit responsibly.

## 2. Business Problem
Home Credit's mission is to expand financial inclusion for the underbanked, who often lack access to traditional banking services due to limited credit history. By leveraging alternative data sources such as transactional and telco information, Home Credit seeks to improve its predictive models to accurately gauge an individual's ability to repay loans. This project aims to develop such models, ensuring fair and equitable access to credit, particularly for underserved communities.

## 3. Data Description
The dataset comprises seven CSV files detailing various aspects of loan applications and client credit history:

1. **application_train/application_test**: These files contain records of loan applications. The training data includes a TARGET column indicating repayment status (0 for no problems, 1 for problems).
2. **bureau**: Provides information on previous credits from other financial institutions.
3. **bureau_balance**: Contains monthly details on these credits.
4. **previous_application**: Covers past loan applications at Home Credit.
5. **POS_CASH_BALANCE**: Monthly details on past POS or cash loans.
6. **credit_card_balance**: Monthly data on past credit cards.
7. **installments_payments**: Tracks the payment history for previous loans.

## 4. Data Cleaning and Imputation
Due to extensive missing data in both the train and test datasets, the following strategies were employed:

1. **Row Removal**: Rows with over 50% missing data were removed.
2. **Column Removal**: Columns with over 65% missing data were removed.
3. **Imputation**: Remaining missing data was imputed using iterative techniques for numeric features and one-hot encoding for categorical features.

## 5. Exploratory Data Analysis (EDA)
The EDA phase provided several key insights:

1. **Class Imbalance**: 91.9% of the loans in the training data were repaid, indicating a significant class imbalance.
2. **Feature Correlations**: Several features showed notable correlations with the target variable:
   - **DAYS_BIRTH** and **AGE_GROUP**: Older applicants tend to have lower default rates.
   - **DAYS_EMPLOYED**: Longer employment duration correlates negatively with default rates.
   - **External Scores**: Scores from external sources negatively correlate with default likelihood.

## 6. Feature Engineering
To enhance model performance, several new features were engineered:

1. **Yearly Interest Rate**: Calculated by dividing the annual annuity amount by the loan amount.
2. **Income Ratios**: Income-to-annuity and income-to-credit ratios were added.

## 7. Model Training and Evaluation
We trained a CatBoostClassifier with 5-fold cross-validation, achieving the following results:

- **AUC Score**: 0.7705
- **Accuracy**: 91.98%

These results demonstrate the model's strong discriminative power, aiding in responsible lending decisions. When accepting future applications, the use of this model can be extremely helpful in process automation to help reduce the time needed for human review of applications. Automating this process will increase the number of loans that the company will be able to hold as the reduction in time from human work to the model's work is drastic. This will save the firm money on labor and increase their potential for profit growth with the new ability to accept more applicants. Given the accuracy, this model should be used in tandem with human workers so that the rejected applications can be handled by humans to verify the results. 

## 8. Results
The model's performance highlights its utility in differentiating between likely defaulters and reliable borrowers. This work supports Home Credit's mission by ensuring accurate and fair assessments of creditworthiness, contributing to inclusive financial services.

## 9. Lessons Learned
This project taught us the importance of:

1. **Handling Missing Data**: Removing rows and columns with excessive missing values and applying imputation strategically.
2. **Feature Selection and Engineering**: Selecting relevant features and creating new ones can greatly improve model performance.
3. **Understanding Business Context**: Thoroughly understanding the business problem ensures that the data analysis and model development align with real-world needs.

During my groups time with this project we encountered a few problems with the data. Being this is the first time many of us had seen a dataset this large it was daunting to know where to begin and how to go about cleaning and preparing our data for the model. Specifically seing that lots of the data was empty poised a huge challenge on us as to reevaluate what rows were important and unimportant and how to gage that. Then further more deciding on a proper strategy for how to impute the data. For most of these we took a mean approach, it seemed to be the safest option. Meaning that if columns or rows were missing above the mean amount of data on average, they would be removed. With imputing, I employed a strategy of imputing based on mean value of the column. While this biased the data towards the middle, the amount of mising data in the dataset was drastically reduced before imputing therefore reducing the impact of the imputation. Additionally, understanding how to combine the transactional data with our train/test datasets was a common problem amongst our group as the transactional data needed to be of the same grain as our train/test data.

## 10. Project Contribution
I was responsible for creating and running my own exploratory data analysis and modeling notebooks. In these notebooks I was able to draw deeper understanding of the data by cleaning the data and investigating features that are used in general loan application decisions or those that had high correlations with acceptance/denial. Additionally I assisted in developing the catboost model that we deployed to help predict whether a candidate will default on their loans or not. Some of my contributions in the model development were: feature engineering, feature importance testing, and model selection.

## 11. Conclusion
This project has shown that predictive modeling can significantly enhance the ability of financial institutions to lend responsibly, while also promoting financial inclusion by accurately assessing creditworthiness. This work underscores the impactful role of data science in advancing equitable financial services.


# [Project 2: CocaCola Swire Case Competition](https://github.com/NickSarka2000/MSBA-Capstone-Fall-2024)

## Business Problem
Swire Coca-Cola's six production plants, which serve 13 states and a demand of 192 million beverage cases, are currently meeting only 94.4% of the demand. This shortfall is largely due to unplanned machine downtime caused by maintenance, mechanical failures, wear and tear, and other issues. These downtimes lead to work orders with long lead times, costing the company approximately $60 million annually in production losses.

## Project Objective
The project aims to develop a predictive model to identify machines at risk of failure. By anticipating these failures, Swire Coca-Cola can implement predictive maintenance strategies, optimize machine maintenance schedules, and proactively procure critical parts to reduce downtime and associated costs.

## Benefits of the Solution
- **Lifecycle Management**: Understand and quantify the lifecycle of machine parts.
- **Production Optimization**: Improve scheduling to maximize output.
- **Inventory Management**: Develop reorder quantities for critical machine components.

## Analytics Approach
- **Regression Techniques**: To estimate downtime duration.
- **Descriptive Analytics**: To understand maintenance strategies for critical parts.

The project will be deemed successful if the predictive model can explain causes and effects and predict failures with a higher accuracy than random chance (50/50). Deliverables include the predictive model, a detailed report on findings, and a GitHub repository with all relevant code.

## Contribution
My contribution on this project was that of at times a project manager that organized the group and established meetings for the group to engage in discussions on how to proceed with our project and stay on the same page. A larger portion of my contribution was on the development of the unsupervised machine learning models we employed (like PCA, K Means Clustering, and Rule Association Mining) and in the analysis of the missing data that we were presented with in our dataset.

## Business Value
The predictive model aims to significantly reduce the financial losses associated with unplanned machine downtime, currently costing Swire Coca-Cola $60 million annually. By identifying machines at risk of failure, the solution will enable:

- **Cost Savings**: Minimized production losses through timely maintenance and part replacement.
- **Operational Efficiency**: Improved production scheduling, leading to higher plant utilization rates.
- **Inventory Optimization**: Reduction in overstocking or shortages of critical components by accurately forecasting part requirements.

## Difficulties Encountered

- **Data Quality Issues**:
   - The dataset contained missing values and inconsistencies, which required extensive preprocessing to ensure model accuracy.
   - Cleaning time-series data was particularly challenging due to irregular intervals and outliers.

- **Model Selection**:
   - Identifying the most suitable model for time-series forecasting and failure prediction required iterative testing and evaluation.

- **Resource Constraints**:
   - Limited time and computational resources impacted the team's ability to test a wider range of advanced models.

- **Integration Challenges**:
   - Designing a seamless integration of the predictive model into existing workflows and systems posed logistical and technical challenges.

## What We Learned
- **Importance of Data Preprocessing**:
   - The project reinforced the critical role of data cleaning and normalization in enhancing model performance.

- **Iterative Model Development**:
   - Experimenting with different analytical approaches deepened the team's understanding of the strengths and limitations of time-series and classification models.

- **Collaboration Skills**:
   - Effective communication and task delegation were key to overcoming project bottlenecks and meeting deadlines.

- **Business-Driven Analytics**:
   - Understanding the business implications of the solution guided model development and ensured alignment with organizational objectives.
