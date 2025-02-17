# Churn-Dashboard

## Project Overview
Developed a Power BI dashboard to analyze churn drivers, predict at-risk customers, and suggest retention strategies. The project identifies key factors influencing churn, flags likely churners, and provides actionable insights to improve customer retention

## Objectve 
The purpose of this task is to:  

1. Define appropriate KPIs to measure customer retention.  
2. Develop a dashboard for the retention manager to track these KPIs.  
3. explaining engagement partner summarizing findings, highlighting key insights, and providing actionable recommendations for improvement.  

The analysis will focus on:  
- Customers who churned in the past month.  
- Services subscribed to (e.g., phone, internet, streaming).  
- Account details (tenure, contract type, payment method, billing, charges, and support tickets).  
- Demographic data (gender, age, partner/dependents status

## Tools
I utilized Excel for data cleaning and Power BI for developing the dashboard.

## Data Source
Dataset used for this task was presented by [PWC](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and Churn Dashboard dataset:[Churn dashboard](https://github.com/Zaki1203/Churn-Dashboard/blob/main/02%20Churn-Dataset.xlsx)

## Data Preparation
Open Microsoft Power BI, navigate to Get Data, and select Excel. Locate and open the file named "02 Churn-Dataset.xlsx". Once the data is loaded, click on Transform Data to access Power Query and perform basic data transformations.

Upon inspecting the dataset, I observed that it contains 24 columns 
I reviewed the data types of all columns to ensure accuracy and consistency. Additionally, I added a conditional column named tenure in yrs on tenure if my tenure is less than 12 then <1 yr, else if my tenure is 24 then <2yrs nad elseif my tenure is less than 36 then <3yrs

## Data Modeling

And then dataset was cleaned and transformed, it was ready to the data modeled.

The customer churn tables as show below:

<img width="503" alt="image" src="https://github.com/user-attachments/assets/22a1f649-7e5e-4f39-a3cb-7d33feca7c90" />


## Dax
-% of dependents = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Dependents]),'01 Churn-Dataset'[Dependents]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[Dependents]),'01 Churn-Dataset'[Churn]="Yes"),0)

-% of Device Protection = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]),'01 Churn-Dataset'[DeviceProtection]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]),'01 Churn-Dataset'[Churn]="Yes"),0)

-% of NO multi lines = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[MultipleLines]="NO",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[Churn]="Yes",'01 Churn-Dataset'[MultipleLines] <> "No phone services"),0)

-% of Online Backup = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]),'01 Churn-Dataset'[OnlineBackup]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]),'01 Churn-Dataset'[Churn]="Yes"),0)

-% of online sec = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]),'01 Churn-Dataset'[OnlineSecurity]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]),'01 Churn-Dataset'[Churn]="Yes"),0)

-% of partners = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Partner]),'01 Churn-Dataset'[Partner]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[Partner]),'01 Churn-Dataset'[Churn]="Yes"),0)

-% of phone services = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]),'01 Churn-Dataset'[PhoneService]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]),'01 Churn-Dataset'[Churn]="Yes"),0)

-% of senior citizen = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[SeniorCitizen]=1,'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[Churn]="Yes"),0)

-% of Streaming Movies = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]),'01 Churn-Dataset'[StreamingMovies]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]),'01 Churn-Dataset'[Churn]="Yes"),0)

-% of Streaming TV = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]),'01 Churn-Dataset'[StreamingTV]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]),'01 Churn-Dataset'[Churn]="Yes"),0)

-% of Tech Support = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]),'01 Churn-Dataset'[TechSupport]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]),'01 Churn-Dataset'[Churn]="Yes"),0)

-% of Yes multi lines = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[MultipleLines]="Yes",'01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]),'01 Churn-Dataset'[Churn]="Yes",'01 Churn-Dataset'[MultipleLines] <> "No phone services"),0)

-Churn Rate = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Churn]),'01 Churn-Dataset'[Churn]="Yes"),COUNT('01 Churn-Dataset'[Churn]),0)


## Data Visualisation

I have made 2 pages for the analysis namely
-Churn Analysis dashboard
-Customer Risk Analysis

![image](https://github.com/user-attachments/assets/cccdd82a-4901-4b45-9175-b56d71c43345)

![image](https://github.com/user-attachments/assets/a3dc947b-427c-4d3c-b49d-d47d1ea40965)

## Analysis

<img width="203" alt="image" src="https://github.com/user-attachments/assets/60618cc7-abe9-44d5-85e3-6131381b217f" />


Customers with less than 1 year of subscription showed the highest churn rate (55.48%) followed by those with less than 2 years (15.73) and less than 3 years (9.63%) In contrast, customers with less than 6 years of tenure had the lowest churn rate at 4.98%

![image](https://github.com/user-attachments/assets/336e8e65-ff04-418d-aa22-fcf076e7fad8)

Customers using fiber optics are more likely to churn compared to those using DSL

![image](https://github.com/user-attachments/assets/e7c7e814-948b-4282-b2a4-fbd6835c5c7b)

Customers with month-month type of contract are more likely to churn due high payment amount

## Insights
From the data visualization, it is evident that:  
- Customers on two-year contracts  tend to have longer tenure, while most month-to-month contract customers are newer.  
- The company is at risk of losing recently joined customers, especially those on month-to-month contracts.  
- 7,043 customers are at risk of churn, with a churn rate of 27%, resulting in $16.06M in yearly charges and $456.12K in monthly charges.  
- 2,955 tech tickets and 3,632 admin tickets were opened.  
- Most churned customers did not subscribe to Online Security, Tech Support, or Phone Services.  
- 42% of churned customers used Fiber Optic as their internet service, indicating potential issues with this service.  

## Recommendations
1. Encourage customers to switch to one-year or two-year contracts, as month-to-month contracts are less favorable and lead to higher churn.  
2. Offer discounts or incentives for specific tasks, particularly for month-to-month customers, to improve retention.  
3. Educate customers on the benefits of subscribing to Online Security and Tech Support, as these services are critical for retention.  
4. Address issues with Fiber Optic services to reduce dissatisfaction.  
5. Aim to increase sales of 1-year and 2-year contracts by 5% each and grow automatic payments by 5% yearly. incentives for specific tasks, particularly for month-to-month customers, to improve retention.  


