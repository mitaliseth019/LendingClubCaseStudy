#Lending Club Case Study

Lending Club is a consumer finance company which specialises in lending various types of loans to urban customers. When the company receives a loan application, the company has to make a decision for loan approval based on the applicant’s profile. The objective of the case study is to identify high-risk loan applicants, which would enable a reduction in such loans and subsequently minimize the overall credit loss. The primary focus of this case study is to achieve the identification of these applicants through exploratory data analysis (EDA) using the provided dataset.


# Table of Contents

* Problem Statement
* Objectives
* Raw Data Analysis
* Data Cleaning
* Case Study Analysis
* Technologies Used
* Conclusions
* Acknowledgements



Lending Club operates as a consumer finance marketplace specializing in providing various types of loans to urban customers. It facilitates the connection between borrowers seeking loans and investors seeking opportunities to lend their funds and earn returns. When the company receives a loan application, the company has to make a decision for loan approval based on the applicant’s profile. Two types of risks are associated with the bank’s decision:
If the applicant is likely to repay the loan, then not approving the loan results in a loss of business to the company.
If the applicant is not likely to repay the loan, i.e. he/she is likely to default, then approving the loan may lead to a financial loss for the company.

# Problem Statement

The goal is to identify risky loan applicants, then such loans can be reduced thereby cutting down the amount of credit loss. Identification of such applicants using EDA using the given dataset, is the aim of this case study.
If one is able to identify these risky loan applicants, then such loans can be reduced thereby cutting down the amount of credit loss. Identification of such applicants using EDA is the aim of this case study.
In other words, the company wants to understand the driving factors (or driver variables) behind loan default, i.e. the variables which are strong indicators of default. The company can utilise this knowledge for its portfolio and risk assessment.

This is a Group project assigned as a module in Exploratory Data Analysis


# Data Set
The data given contains the information about past loan applicants and whether they ‘defaulted’ or not. The aim is to identify patterns which indicate if a person is likely to default, which may be used for taking actions such as denying the loan, reducing the amount of loan, lending (to risky applicants) at a higher interest rate, etc.

# Raw data quick summary
No header or footer rows in the dataset
No summary rows were there in the dataset
No column number, indicators etc. found in the dataset
No duplicate rows are there in the dataset


# Data Cleaning
Drop unnecessary rows:
Rows where the loan_status = CURRENT will be dropped as CURRENT loans are in progress and will not contribute in the decision making.

Drop unnecessary columns:
Drop those columns where all values are only zero or NA.
Drop columns where all values are constant such as application_type
Drop unnecessary columns (id, member_id, url, emp_title, desc, purpose, title,  zip_code, addr_state, next_pymnt_d, mths_since_last_record, policy_code,pymnt_plan,initial_list_status,pub_rec,delinq_2yrs,out_prncp,out_prncp_inv,total_rec_late_fee,recoveries,collection_recovery_fee,pub_rec_bankruptcies,inq_last_6mths,mths_since_last_delinq which wont add significant value in analysis

Standardizing the data:
Removing % sign from int_rate values and converting the data type into float 

Remove Outlier data:
Basis boxplot of annual income, we realize that that 99% of the data lies below 1,000,000. So, considering annual income above 1,000,000 as Outliers and removing them from the data



#Case Study Analysis:
Loan Status vs Grades: Lending Club may consider adjusting its portfolio management strategies based on the analysis of loan grades. For example, it may allocate a smaller portion of funds to higher-risk grades (B and C) or more stringent approval criteria or higher interest rates may be applied to higher-risk grades (B and C) to mitigate the risk of defaults.

Home Ownership Impact: The data suggests that home ownership may be a factor influencing credit risk. Borrowers with "MORTGAGE" and "RENT" home ownership appear to have a higher likelihood of loan defaults (Charged Off) compared to those with "OWN," "OTHER," or "NONE.“

Loan Status vs Debt to income ratio: Charged off loans for 36 months loan term is 25% higher compared to 60 months loan term which indicates that portfolio should be managed in a way that loan disbursal is higher for 36 months loan term.

Loan Status vs Installment Amount: The fact that Charged Off loans have a higher mean and median installment amount suggests that, on average, loans that default tend to have slightly larger installment amounts

Loan Status vs Interest Rates: The higher mean, median and standard deviation in interest rates for Charged Off loans suggest that loans with higher interest rates may be associated with a higher risk of default. 

Loan Status vs Debt to income ratio: With minor difference in dti median amount for charged off loans compared to Fully paid and higher variation, the result indicates that dti on a standalone basis is not a significant factor for identifying defaulters.



#Insight Summary:

Grade:  Loan grades can be indicative of credit risk. Grades B and C have a relatively higher number of loans categorized as "Charged Off" compared to grades A and D. This suggests that grades B and C may represent higher credit risk.

Interest Rate : The higher mean, median and variation in interest rates for Charged Off loans suggest that loans with higher interest rates may be associated with a higher risk of default. 

Home Ownership Impact: The data suggests that home ownership may be a factor influencing credit risk. Borrowers with "MORTGAGE" and "RENT" home ownership appear to have a higher likelihood of loan defaults (Charged Off) compared to those with "OWN," "OTHER," or "NONE.“

Annual Income: Applicants in low incomes range( below 60k) have a greater share of defaulted loans.

Debt to Income ratio (dti) - From the correlation analysis we can realise that dti is negatively corelated to annual income and hence dti becomes another key driving factor behind loan default. 

Correlation Analysis: For profiles with low annual income, loan amount and funded amount disbursed should be kept low so as to reduce the magnitude of loss. Additionally, interest should be kept higher to balance out the portfolio and minimize losses.

Inferences:
In conclusion we can realize that factors like Loan term, Grade, Home ownership , Annual income and interest rate become the key driving factors  behind loan default,. Certain other variables like debt to income ratio, verification status, issue year etc. becomes additional driving factors when combined with these. Although this is just limited to univariate and bivariate analysis of key variables, the mentioned variables should be carefully analysed to ensure loan portfolio is hedged properly. Certain variables like interest rate(higher for risky applicants), loan amount (lower for risky applicants) should be adjusted properly for new applicants ( basis existing charged off customer profile)



#Technologies Used:
Python - Version 3.12.0
numpy - Version 1.26.0
pandas - Version 2.1.1
Jupyter Notebook - Version 6.5.2
JupyterLab - Version 3.5.3
Anaconda - Version 2.4.2


#Acknowledgements and References:
The project references insights and inferences from Stackoverflow
The project reference course materieals from upGrads curriculm


#Team:
Mitali Seth
Bharat Kalra

This project is open source

