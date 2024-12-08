# **Capstone Practice Project: Predicting Loan Default Risk HomeCredit**

## **1. Business Problem and Project Objective**

Home Credit strives to provide a more inclusive banking experience and broaden financial inclusion for the unbanked population.  To provide this experience Home Credit must be able to accurately assess the risk of default by customers, the majority of which have limited or no formal credit history. Home Credit wants to further the inclusivity of its lending by reducing the risk of lending to potentially high-risk clients while maintaining accessibility, accurately predicting the default risk of clients is crucial to maintaining its mission. 

This project aims to unlock the full potential of Home Credit’s client data to give loans with a principal, maturity, and repayment calendar that will empower their clients to be successful.

**Objective:** 
Create a predictive model that classifies loan applicants as likely to default or not, based on their demographic, financial, and behavioral data. The project focuses on balancing AUC and recall to ensure that the model minimizes defaults as much as possible. 

---

## **2. Our Solution**
To solve the business problem, we implemented an iterative machine-learning process with the following steps. 
1. **Data Cleaning and Preprocessing**:
We handled missing data, removed outliers, and selected the most relevant features for prediction. Standouts from this process were that 45 variables were missing over 48% of their data, there were outliers such as really large families and very high-income earners, and there were what seemed to be data entry issues, where some values had to be removed as they were nonsensical. We also spent some time working with the external source vairables for thier missing vlaue imputation, we engineered binary indicators for missiness across all three external sources as well as a indicator for those missing a value across all three external source values. Other engineered terms that were of importance, were the simple debt to income ratio using the individusal income and credit, as well as credit duration which was made up from the credit and annuity values. 
4. **Exploratory Data Analysis (EDA)**:
The exploratoty data analysis process involved visualizing key relationshispin the data to better understand which variables impact the likelihood of default. As well as examinign the impact of the signficnat class imabalance that existed.
6. **Model Development**:
We worked through an iterative process in modeling, starting with baseline peromrace measured with a simple logisitc regression model
 Random Forest, XGBoost, and Support Vector Machines (SVM).
8. **Model Evaluation**:
We evaluated models using precision, recall, and AUC-ROC to ensure a balance between avoiding defaults and approving as many loans as possible.
9. **Implementation**:
The best-performing model was selected for use in predicting applicant default risk.

---

## **3. My Contribution**
My specific contributions to the project included:
- **Data Wrangling**: I cleaned and preprocessed the raw data, handling missing values, outliers, and categorical variables.
- **Feature Engineering**: I created new features and selected the most relevant predictors for model training.
- **Model Development and Tuning**: I built models using Logistic Regression, Random Forest, and XGBoost. I also fine-tuned hyperparameters to optimize model performance.
- **Evaluation and Insights**: I evaluated models using performance metrics (precision, recall, AUC-ROC) and selected the best-performing model.
- **Report and Documentation**: I prepared this README and ensured that the RMarkdown files followed best practices, with proper commenting, labeled visualizations, and clear interpretation of results.

---

## **4. Business Value of the Solution**
The solution provides clear business value by:
- **Reducing Risk**: The model predicts which applicants are likely to default, allowing the lender to make more informed decisions.
- **Increasing Efficiency**: Automating the risk assessment process reduces manual review time for loan applications.
- **Promoting Financial Inclusion**: By accurately identifying creditworthy applicants, the institution can approve more loans while reducing the risk of default.
- **Cost Savings**: Early identification of high-risk applicants reduces the cost of delinquency and default.

---

## **5. Challenges Encountered**
While working on this project, we encountered several challenges, including:
- **Handling Missing Data**: Many features in the dataset had missing values, and we had to carefully decide on imputation strategies.
- **Feature Selection**: With hundreds of features available, it was difficult to select the most predictive features for the model.
- **Imbalanced Classes**: The dataset was imbalanced, with far fewer defaults than non-defaults. We addressed this using upsampling and threshold tuning.
- **Hyperparameter Tuning**: Finding the right hyperparameters for models like Random Forest and XGBoost required significant time and computational resources.

---

## **6. What I Learned**
Through this project, I learned several key lessons, including:
- **Feature Engineering**: The importance of creating and selecting the right features to improve model performance.
- **Model Selection**: How to compare different machine learning models and choose the best one using performance metrics like precision, recall, and AUC-ROC.
- **Data Imbalance Techniques**: How to handle imbalanced datasets using upsampling, downsampling, and threshold adjustments.
- **Robust Reporting**: I learned how to prepare clear, reproducible reports using RMarkdown with proper comments, clear headings, and well-labeled visualizations.
- **Collaboration**: Collaborating with a team required strong communication, version control (Git), and clearly defined roles and responsibilities.

---

## **7. Project Files**
Here is a brief explanation of the project files in this repository:



## Visualization Highlights
![D5E0BC9F-0444-48AE-96FD-E49DE723E8E6_1_105_c](https://github.com/user-attachments/assets/30f8f7d7-aecd-43d9-a620-ffe2f4f44af8)
![89D5ECCE-DC55-48F0-B12F-32CC4092F96D_1_105_c](https://github.com/user-attachments/assets/4cdf63c7-cf6b-46d3-9ffa-bd82726e0a44)
