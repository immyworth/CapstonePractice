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
We handled missing data, removed outliers, and selected the most relevant features for prediction. Standouts from this process were that 45 variables were missing over 48% of their data, there were outliers such as large families and very high-income earners, and there were what seemed to be data entry issues, where some values had to be removed as they were nonsensical. We also spent some time working with the external source variables for their missing value imputation, we engineered binary indicators for missingness across all three external sources and an indicator for those missing a value across all three external source values. Other important engineered terms were the simple debt-to-income ratio using the individual income and credit, as well as credit duration made up from the credit and annuity values.

4. **Exploratory Data Analysis (EDA)**:
The exploratory data analysis process involved visualizing key relationships in the data to better understand which variables impact the likelihood of default. As well as examining the impact of the significant class imbalance that existed.

6. **Model Development**:
We worked through an iterative process in modeling, starting with baseline performance measured with a simple logistic regression model, here we were able to understand the effect the class imbalance had on our model training and selection process. After establishing a majority classifier model, we worked with a logistic model with some features found to be important, as well as including the engineered terms to determine their importance. This model still had issues identifying the defaulters in the data set, so we then moved to a random forest model which improved in performance. After the RF model, we worked on improving some XGBoost models, with tuned hyperparameters and upsampled training data to expand our model's familiarity with the minority class of defaulters. 

8. **Model Evaluation**:
We evaluated models using precision, recall, and AUC-ROC to ensure a balance between avoiding defaults and approving as many loans as possible. Our best-performing model had a high AUC and high recall, however, some models had a higher AUC but did not have a good recall rate. This model was also evaluated on the testing data and received a Kaggle score of about 0.74.

10. **Implementation**:
The best-performing model was the XGBoost model with tuned parameters trained with upsampled data. We recommend that HomeCredit implement this model in order to be able to identify applicants who have a higher risk of defaulting. Implementing this model would allow HomeCredit to identify 50% more of their applicants who are at risk of defaulting, which would save the company time and money on risky applicants. 

---

## **3. My Contribution**
My specific contributions to the project included:
- **Data Wrangling**: I worked on my personal EDA assignment to explore variable relationships and examine the missing data. For the group work, I assisted with the clean-up of the data as well as the imputation of missing values.  
- **Feature Engineering**: I worked to create new values to indicate missing values for the External Credit scores, so that their missing-ness was utilized but also allowed for us to impute the missing values on the external source values. Other variables that were created to examine the nonlinear relationships were a simple debt-to-income value, calculated from an applicant's credit and income, as well as a credit duration rate which was the individual's credit over their annuity, which helped capture the expected payment timeline. 
- **Model Development and Tuning**: I worked on developing a baseline XGBoost model, then used random search to find the best hyperparameters that improved the model's AUC and recall, and finally worked with upsampling the training data and training a new model on the upsampled data. The upsampling process involved working with both upSample as well as scale_pos_weight, with upSampling resulting in the best-trained model. 
- **Evaluation and Insights**: I evaluated the models between their AUC and recall performance, as well as deployed the best model (XGBoost upsampled with tuned parameters) on the Kaggle data to determine the Kaggle score. I also developed various visualizations to better understand the improvement and change in performance over the models.
- **Report and Documentation**: I worked to develop visualizations for the presentation portion of the assignment in order to explain our modeling process and the impact it would have for HomeCredit. 

---

## **4. Business Value of the Solution**
The solution provides clear business value by:
- **Reducing Risk**: The model better predicts which applicants are likely to default, allowing the lender to make more informed decisions.
- **Increasing Efficiency**: Automating the risk assessment process reduces manual review time for loan applications, and would allow HomeCredit to approve more applicants faster and with increased confidence. 
- **Promote Financial Inclusion**: By accurately identifying creditworthy applicants, the institution can approve more loans while reducing the risk of default.
- **Cost Savings**: Early identification of high-risk applicants reduces the cost of delinquency and default.

---

## **5. Challenges Encountered**
While working on this project, we encountered several challenges, including:
- **Handling Missing Data**: Many features in the dataset had missing values, and we had to carefully decide on imputation strategies, as well as understand the effect of removing features due to missingness. 
- **Feature Selection**: With hundreds of features available, it was difficult to select the most predictive features for the model.
- **Imbalanced Classes**: The dataset was significantly imbalanced, with far fewer defaults than non-defaults. This made it very difficult for our model to learn who would be likely to default, we were able to address this issue by upsampling the data to give the model more familiarity with the defaulters.  
- **Hyperparameter Tuning**: Finding the right hyperparameters for models like Random Forest and XGBoost required significant time and computational resources. In order to tune for the best parameter I had started with a cross-validation approach, this turned out to be highly computationally expensive and took a very long time to run - and I was never able to achieve an output. In order to address this we utilized Random Search over 20 combinations to limit the scope of the search and reduce run time.
- **Quantifying Impact**: We struggled to explain and quantify the impact to HomeCredit. In our presentation our group did not explain the impact that this would have in a business context, I think we could have worked better to understand the costs associated with a client defaulting, and how early identification of risky applicants would improve HomeCredits business. 
---

## **6. What I Learned**
Through this project, I learned several key lessons, including:
- **Feature Engineering**: The importance of creating and selecting the right features to improve model performance.
- **Model Selection**: How to compare different machine learning models and choose the best one using performance metrics like precision, recall, and AUC-ROC.
- **Data Imbalance Techniques**: How to handle imbalanced datasets using upsampling, downsampling, and threshold adjustments.
- **Robust Reporting**: I learned how to prepare clear, reproducible reports using RMarkdown with proper comments, clear headings, and well-labeled visualizations.
- **Collaboration**: Collaborating with a team requires strong communication, the ability to share work (GitHub), communication of key findings, as well as how to combine individual coding efforts into a succinct group portfolio.
- **Time Management**: Another important aspect I learned throughout this project was how I should schedule my time to break out computationally expensive and complicated tasks, this gave me a really good understanding of what is expected next semester. 
---

## **7. Project Files**
Here is a brief explanation of the project files in this repository:
This README document explains my project process and outcomes.
CapstonePractice documents my individual EDA process
The Modeling Updates Capstone -Imogen Version file was my contribution to the improved modeling that we worked on between the submission of the modeling assignment and the presentation. 
Modeling_Assignment (2) file is the group submission to Canvas for the modeling assignment. 


## Visualization Highlights
Below are some stand-out visualizations that I developed for the presentation:
![D5E0BC9F-0444-48AE-96FD-E49DE723E8E6_1_105_c](https://github.com/user-attachments/assets/30f8f7d7-aecd-43d9-a620-ffe2f4f44af8)
![89D5ECCE-DC55-48F0-B12F-32CC4092F96D_1_105_c](https://github.com/user-attachments/assets/4cdf63c7-cf6b-46d3-9ffa-bd82726e0a44)
![Confusion Matrix Plot Without Gridlines](https://github.com/immyworth/ImogenHoldsworth/blob/main/confusion_matrix_plot_no_gridlines.png?raw=true)



