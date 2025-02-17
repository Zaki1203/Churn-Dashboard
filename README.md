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

## Data Source
Dataset used for this task was presented by [PWC](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and [Churn dashboard](https://github.com/Zaki1203/Churn-Dashboard/blob/main/02%20Churn-Dataset.xlsx)

## Data Preparation
Open Microsoft Power BI, navigate to Get Data, and select Excel. Locate and open the file named "02 Churn-Dataset.xlsx". Once the data is loaded, click on Transform Data to access Power Query and perform basic data transformations.

Upon inspecting the dataset, I observed that it contains 24 columns 
I reviewed the data types of all columns to ensure accuracy and consistency. Additionally, I added a conditional column named tenure in yrs on tenure if my tenure is less than 12 then <1 yr, else if my tenure is 24 then <2yrs nad elseif my tenure is less than 36 then <3yrs


