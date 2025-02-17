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






