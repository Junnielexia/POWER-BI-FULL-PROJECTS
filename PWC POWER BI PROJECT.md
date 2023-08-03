# TASK 1: What do you hope to learn from this Experience

As a beginner data analyst, the Digital Accelerator programme's PowerBI journey offers an exciting opportunity for growth. My main focus is mastering data visualization, enabling me to transform complex data into interactive visualizations for better client understanding and informed decision-making. Additionally, I am eager to explore automation in PowerBI to enhance process efficiency, freeing up time for strategic initiatives. Integrating machine learning into PowerBI excites me as it opens doors to intuitive problem-solving. Furthermore, I plan to develop strong skills in digital storytelling to effectively communicate data insights and drive positive change. I am enthusiastic about this transformative experience and eager to contribute to the organization's digital transformation.

# TASK 2 CALL CENTRE TREND ANALYSIS

## Introduction

The **Introduction** section provides a brief overview of the document, setting the context for the reader. It explains the purpose of the document and introduces the virtual internship with PwC Switzerland. As part of this internship, I have been provided with a dataset that plays a crucial role in accomplishing the second internship task.
***
## Data Description

The **Data Description** segment provides essential information about the dataset, such as its structure and contents. The dataset is represented as a tabular form with 10 columns and 5001 rows. Each column serves as a distinct attribute of the data, facilitating a comprehensive understanding of the information at hand. The columns are labeled as follows:

1. **Call Id:** A unique identifier for each call made.
2. **Agent:** The name or identifier of the customer service agent handling the call.
3. **Date:** The date on which the call was received or made.
4. **Time:** The timestamp of the call.
5. **Topic:** The subject or category of the call's purpose.
6. **Answered (Y/N):** A binary indicator denoting whether the call was answered or not.
7. **Resolved:** Indicates whether the issue or query raised during the call was resolved or not.
8. **Speed of Answer in seconds:** The time taken to answer the call, measured in seconds.
9. **AvgTalkDuration:** The average duration of the call in seconds.
10. **Satisfaction Rating:** A rating given by the caller to express their satisfaction with the service provided.
***
## Initial Data Exploration

 During this phase, I examined the dataset using powequerry feature in POWER BI to gain insights into its composition, identifying any potential issues such as missing values, outliers, or data inconsistencies. This preliminary exploration helps lay the foundation for further data analysis and processing.
 
 ![Screenshot (192)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/a36682cc-fe30-4a6e-be8d-f88c18c23d65)

***
## Data Preparation

 During this phase, I will perform various data cleaning and transformation tasks, such as handling missing values, standardizing data formats, and removing any redundant or irrelevant information. This meticulous preparation is essential to ensure the dataset's quality and integrity, ultimately leading to more reliable and meaningful analytical results.

 ![Screenshot (193)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/28be1d34-2d1b-419a-9e8c-0c771524096e)

 ### Fixing Abbreviations
 
 ![Screenshot (191)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/407bc776-e9ef-4e15-867d-b037ea274e81)
 
 I addressed the issue of abbreviations in the dataset using Power Query. Specifically, I replaced the abbreviation "Y" with "Yes" and "N" with "No." This transformation was executed systematically across the relevant columns, ensuring improved data interpretability and maintaining consistency for subsequent data analysis tasks.

![Screenshot (195)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/25c76b18-cf02-4ee3-9e14-374b67517657)

Sure! Here's the text written in Markdown format:

### Fixing Empty Cells

In order to enhance data completeness and ensure accuracy in the dataset, I addressed the presence of empty cells using Power Query. By leveraging this tool, I systematically identified and filled in missing values with appropriate data, replacing "null" values with "0." This approach ensures a more robust analysis and avoids potential pitfalls associated with incomplete data.

![Screenshot (196)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/5e0f52cd-b907-4b03-82d0-b9e533de004a)

#### Procedure

![Screenshot (198)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/54caae8f-7c1f-47b8-bc49-b494f7f8c0f8)

#### Result

![Screenshot (199)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/bc5f01dc-8c24-45ed-90e1-90ef92fe670d)

Here's the "New Measure" table with explanations in Markdown format:
***
# Creating New Measure
I created a New Measure Table TO ADD all the new measures I created for clarity and ease of the report.

| Measure Name                 | DAX Expression                                                                                                 | Explanation                                                                                                  |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Abandonment Rate             | `DIVIDE(CALCULATE(COUNTROWS(Sheet1), Sheet1[Answered (Y/N)] = "N"), COUNTROWS(Sheet1)) * 100`                 | Calculates the percentage of calls abandoned by dividing the count of unanswered calls by the total call count and multiplying by 100.                                  |
| Average Handle Time          | `AVERAGEX(ADDCOLUMNS(Sheet1, "AHT", ([Speed of answer in seconds] + [AvgTalkDuration]) / 2), [AHT])`            | Calculates the average handle time by averaging the speed of answer and average talk duration for each call. |
| Average Speed of Answer (ASA)| `AVERAGE('Sheet1'[Speed of answer in seconds])`                                                               | Computes the average speed of answer in seconds for all answered calls.                                    |
| Average Talk Duration        | `AVERAGE(Sheet1[AvgTalkDuration])`                                                                            | Computes the average talk duration for all calls.                                                            |
| First Call Resolution Rate   | `DIVIDE(CALCULATE(COUNTROWS(Sheet1), Sheet1[Resolved] = "Y"), COUNTROWS(Sheet1)) * 100`                       | Calculates the percentage of calls resolved on the first attempt.                                           |
| Overall Customer Satisfaction| `AVERAGE('Sheet1'[Satisfaction rating])`                                                                      | Computes the average satisfaction rating to gauge overall customer satisfaction.                          |
| Positive Satisfaction Count  | `CALCULATE(COUNTROWS(Sheet1), FILTER(Sheet1, Sheet1[Satisfaction rating] >= 4 && Sheet1[Satisfaction rating] <= 5))` | Counts the number of positive satisfaction ratings (ratings from 4 to 5).                                 |
| Total Call Answered          | `COUNTX(FILTER('Sheet1', 'Sheet1'[Answered (Y/N)] = "YES"), 'Sheet1'[Answered (Y/N)])`                         | Counts the number of calls that were answered.                                                              |
| Total Calls                  | `CALCULATE('NEW MEASURE'[Total Call Answered] + 'NEW MEASURE'[Total Unanswered Calls])`                        | Computes the total number of calls (answered and unanswered) by summing up the counts of each.               |
| Total Unanswered Calls       | `COUNTX(FILTER('Sheet1', 'Sheet1'[Answered (Y/N)] = "NO"), 'Sheet1'[Answered (Y/N)])`                           | Counts the number of unanswered calls.                                                                      |


![Screenshot (200)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/f034a339-2b9d-423c-af4b-b9d454ee2393)

****
# Data Visualisation

## Key Performance Indicators (KPIs)

![Screenshot (202)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/7a161a3e-49bd-43d6-a0c8-f66970988007)

## Sum of answer speed in seconds by Agent
  Visualizing the "Sum of Answer Speed in Seconds by Agent" allows the business to gain valuable insights into individual agent performance and identify areas for improvement, leading to enhanced call center operations and customer service.
  
![Screenshot (205)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/09dbf55a-83dc-43b8-abd7-b0299c77b394)

## Sum of Satisfaction Rating by Agent

Visualizing the "Sum of Satisfaction Rating by Agent" enables the business to assess the overall customer satisfaction for each agent, identifying top-performing agents and areas for improvement to enhance customer service and build stronger client relationships.

![Screenshot (206)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/1a14f70a-85a0-4389-956b-f95d31f72314)

## Total Calls by Topic and Resolved Yes/No":

Visualizing the "Total Calls by Topic and Resolved Yes/No" allows the business to understand call volume distribution across different topics and evaluate the resolution rate, helping identify trending issues, measure agent performance, and enhance overall customer support efficiency.
![Screenshot (207)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/cc762639-7020-4b34-8f60-ac380ed4aee7)

## Abandonment Rate by Topic":

Visualizing the "Abandonment Rate by Topic" provides crucial insights into customer behavior and pain points, enabling the business to prioritize improvements in specific topics and reduce abandonment rates, ultimately enhancing customer satisfaction and call center performance.

![Screenshot (208)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/78498d41-0027-4ce9-9475-8b9a53a184a8)
 
## Firt Call Resolution by Agent

Visualizing "First Call Resolution by Agent" is vital for the business to evaluate individual agent performance in resolving customer issues on the initial call, helping to identify top-performing agents and areas for improvement, leading to increased customer satisfaction and operational efficiency.

![Screenshot (209)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/6adb38c0-d27c-49e1-b185-fac09bd5a9ca)

# Agent Performance Quadrant

Visualizing the "Agent Performance Quadrant" allows the business to categorize agents based on key performance metrics, such as call resolution rate and customer satisfaction, helping to identify high-performing agents, areas for improvement, and coaching opportunities to optimize overall call center performance and customer experience.

![Screenshot (210)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/607b1121-99c5-4e3b-886b-7dbc34d8ecee)

# Dashboard
![Screenshot (211)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/4665e3f2-1615-4220-af62-fb65272373cf)

# Task 3 Customer Retention

## Customer demographics and insights.

# Here is your task
Your colleague, the engagement partner, asks you to do the following tasks:
- Define proper KPIs
- Create a dashboard for the retention manager reflecting the KPIs
- Write a short email to him (the engagement partner) explaining your findings, and include suggestions as to what needs to be changed
***

## Sample Data Analysis - Telecommunication Customer Churn

### Overview

In this data analysis, we will be working with a dataset containing information about customers from a telecommunication company. Our objective is to understand customer churn and derive actionable insights to improve retention.

### Dataset Description


| Column Name       | Description                                      |
| ----------------- | ------------------------------------------------- |
| customerID        | Unique identifier for each customer              |
| gender            | Gender of the customer (e.g., Male, Female)      |
| SeniorCitizen     | Whether the customer is a senior citizen (1/0)   |
| Partner           | Whether the customer has a partner (Yes/No)      |
| Dependents        | Whether the customer has dependents (Yes/No)     |
| tenure            | Number of months the customer has been with the company |
| PhoneService      | Whether the customer has phone service (Yes/No)  |
| MultipleLines     | Whether the customer has multiple phone lines (Yes/No/No phone service) |
| InternetService   | Type of internet service (DSL, Fiber optic, None) |
| OnlineSecurity    | Whether the customer has online security (Yes/No/No internet service) |
| OnlineBackup      | Whether the customer has online backup (Yes/No/No internet service) |
| DeviceProtection  | Whether the customer has device protection (Yes/No/No internet service) |
| TechSupport       | Whether the customer has tech support (Yes/No/No internet service) |
| StreamingTV       | Whether the customer has streaming TV (Yes/No/No internet service) |
| StreamingMovies   | Whether the customer has streaming movies (Yes/No/No internet service) |
| Contract          | Type of contract (Month-to-month, One year, Two year) |
| PaperlessBilling  | Whether the customer has opted for paperless billing (Yes/No) |
| PaymentMethod     | Payment method used by the customer (e.g., Electronic check, Credit card, Bank transfer) |
| MonthlyCharges    | Monthly charges billed to the customer          |
| TotalCharges      | Total charges billed to the customer            |
| numAdminTickets   | Number of administrative tickets raised by the customer |
| numTechTickets    | Number of technical tickets raised by the customer |
| Churn             | Whether the customer churned (Yes/No)            |

![Screenshot (212)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/05dc3fc0-427b-43bd-bfe8-11d4b2d9b787)

***
### Data Cleaning and Preprocessing

Before performing any analysis, we conducted data cleaning and preprocessing steps. This included handling missing values, converting categorical variables into appropriate formats, and scaling numerical features as needed.


#### Churn column
I replaced Yes to churned and No to stayed

![Screenshot (213)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/567885ba-6061-4671-b741-39f8488cdd0c)
***

#### Partner column
I replaced Yes to Partner and NO to No Partner

![Screenshot (214)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/b83230ab-d959-4934-8098-5fcd0b73e408)

***
#### Tenure Column
I used the tenure column showing the number of months a customer has stayed to create a custom column (Duration) grouping them into number of years.

##### Formula
![Screenshot (214)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/91bc537d-c642-42cf-b66a-48f0b3a115bc)

```
= 
if [tenure] <= 12 then "0-1 year"
else if [tenure] <= 24 then "1-2 years"
else if [tenure] <= 36 then "2-3 years"
else if [tenure] <= 48 then "3-4 years"
else "4+ years"
```
##### Result

![Screenshot (216)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/ec7924a1-8713-4602-812d-2e8a26edffb8)

***
### Exploratory Dat
.a Analysis (EDA)
I created a NEW MEASURE table to carefully arrange all my new measures for the KPIs 

![Screenshot (218)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/42c68250-e3ee-4b3d-91fb-309c179180b7)


| Measure Name                    | DAX Formula                                                                                      |
|---------------------------------|--------------------------------------------------------------------------------------------------|
| AverageTenure                   | AVERAGE('Churn-Dataset'[tenure])                                                                 |
| Avg Monthly Revenue Churned     | CALCULATE(AVERAGE('Churn-Dataset'[MonthlyCharges]), 'Churn-Dataset'[Churn] = "Churned")          |
| Avg Monthly Revenue Female      | CALCULATE(AVERAGE('Churn-Dataset'[MonthlyCharges]), 'Churn-Dataset'[gender] = "Female")          |
| Avg Monthly Revenue Male        | CALCULATE(AVERAGE('Churn-Dataset'[MonthlyCharges]), 'Churn-Dataset'[gender] = "Male")            |
| Avg Monthly Revenue NonChurned  | CALCULATE(AVERAGE('Churn-Dataset'[MonthlyCharges]), 'Churn-Dataset'[Churn] = "Stayed")           |
| Churn Rate                      | DIVIDE(CALCULATE(COUNTROWS(FILTER('Churn-Dataset', 'Churn-Dataset'[Churn] = "Churned"))), COUNTROWS('Churn-Dataset'), 0) |
| Customer Count CreditCard       | COUNTROWS(FILTER('Churn-Dataset', 'Churn-Dataset'[PaymentMethod] = "Credit Card (automatic)"))   |
| Customer Count FiberOptic       | COUNTROWS(SUMMARIZE(FILTER('Churn-Dataset', 'Churn-Dataset'[InternetService] = "Fiber Optic"), 'Churn-Dataset'[customerID])) |
| Customer Count NoInternet       | COUNTROWS(SUMMARIZE(FILTER('Churn-Dataset', 'Churn-Dataset'[InternetService] = "No"), 'Churn-Dataset'[customerID]))         |
| Customer Count ElectronicCheck  | COUNTROWS(FILTER('Churn-Dataset', 'Churn-Dataset'[PaymentMethod] = "Electronic check"))         |
| Customer Count MailedCheck      | COUNTROWS(FILTER('Churn-Dataset', 'Churn-Dataset'[PaymentMethod] = "Mailed check"))             |
| Customer Retention Rate         | DIVIDE(COUNTROWS(FILTER('Churn-Dataset', 'Churn-Dataset'[Churn] = "Stayed")), COUNTROWS('Churn-Dataset'), 0) |
| Female Customers                | CALCULATE(COUNTROWS('Churn-Dataset'), 'Churn-Dataset'[gender] = "Female")                      |
| Male Customers                  | CALCULATE(COUNTROWS('Churn-Dataset'), 'Churn-Dataset'[gender] = "Male")                        |
| Total Churn                     | COUNTROWS(FILTER('Churn-Dataset', 'Churn-Dataset'[Churn] = "Yes"))                              |
| Total Non Senior Citizen        | COUNTROWS(SUMMARIZE(FILTER('Churn-Dataset', 'Churn-Dataset'[SeniorCitizen] = 0), 'Churn-Dataset'[customerID])) |
| Total Senior Citizen            | COUNTROWS(SUMMARIZE(FILTER('Churn-Dataset', 'Churn-Dataset'[SeniorCitizen] = 1), 'Churn-Dataset'[customerID])) |
| Total Loss                      | CALCULATE(SUM('Churn-Dataset'[MonthlyCharges]), 'Churn-Dataset'[Churn] = "Churned")            |

***
## KPI
During the EDA phase, we explored the dataset to gain valuable insights into customer churn. Here are some key findings:

![Screenshot (230)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/fce7331a-9941-4d88-9806-4056a9c23fd5)

### Count of Customer ID by Payment Method

The visual "Count of Customer ID by Payment Method" provides a comprehensive view of the number of customers associated with each payment method. By analyzing this distribution, we can identify which payment methods are more popular among the customer base, enabling us to tailor the payment options and promotional strategies to better suit customer preferences and potentially improve overall customer satisfaction and retention.

![Screenshot (219)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/f6924169-519e-4edf-b1e8-60101a4368d7)

### Count of Churn by patner and Dependents

The visual "Count of Churn by Partner and Dependents" allows us to examine the churn behavior based on whether customers have a partner and dependents. By comparing the count of churned customers within different segments (e.g., customers with partners and dependents, customers with partners but no dependents, customers with dependents but no partners, and customers with neither partners nor dependents), we can identify any patterns or trends that may influence customer churn. This insight can help us develop targeted retention strategies for specific customer segments to reduce churn and enhance overall customer loyalty.

![Screenshot (220)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/9ac6066c-06e2-4f32-9ba7-01bbf1773d96)

### Sum of Monthly Charges and TotalChurn by Internet Services

The visual "Sum of Monthly Charges and Total Churn by Internet Services" presents the total monthly charges generated by customers for each internet service type (e.g., DSL, Fiber Optic, and No Internet) along with the total number of churned customers within each service category. This allows us to assess the revenue contribution and churn rate associated with different internet service offerings, enabling us to identify potential opportunities for revenue growth and areas where customer churn may require further investigation or targeted interventions.

![Screenshot (221)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/6d99f1c0-7636-4514-ab1c-4e849b7645b1)

### Total Revenue by Duration

The visual "Total Revenue by Duration" displays the total revenue generated based on the duration of customer contracts (e.g., Monthly, 1 Year, and 2 Year). This visualization allows us to compare the revenue contributions from customers with different contract durations, helping us understand the financial impact of contract lengths on our business and identify which contract durations are more lucrative. By analyzing this data, we can make informed decisions on contract offerings and tailor our marketing strategies to optimize revenue and customer retention.


![Screenshot (222)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/ce1b99b9-d2e6-45e9-a17a-c18b3280571d)

### Total Loss, Total Churn, Total Revenue by Gender

The visual "Total Loss, Total Churn, Total Revenue by Gender" illustrates the following insights:

1. Total Loss: The cumulative loss in revenue due to customer churn categorized by gender. It provides a view of the total revenue lost from churned customers, separated by male and female customers.

2. Total Churn: The count of churned customers categorized by gender. This shows the total number of customers who have churned, broken down by male and female customers.

3. Total Revenue: The overall revenue generated from all customers categorized by gender. It allows us to compare the total revenue earned from male and female customers.

By analyzing these metrics, we can understand the financial impact of churn and customer gender on our business. It also helps us identify any gender-related patterns in churn behavior and revenue generation, guiding us in devising targeted retention strategies to reduce churn and enhance revenue from both male and female customers.

![Screenshot (223)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/95f9c26a-a87c-4f28-b9bf-5c10a31cf8c5)

### Average Tenure by Churn
The visual "Average Tenure by Churn" provides insights into the average tenure (duration of customer relationship) for both churned and retained customers. By comparing the average tenure of customers who churned with those who stayed, we can identify any significant differences in customer loyalty and engagement. This information is valuable for understanding the relationship between tenure and churn, enabling us to focus on improving customer retention strategies for different customer segments based on their tenure.

![Screenshot (224)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/6a6fa6af-a235-46c6-87d6-e15ff479c127)

### Non Senior Citizen and Senior Citizen by Churn 
The visual "Non Senior Citizen and Senior Citizen by Churn" presents a comparison of churn behavior between non-senior citizens and senior citizens. It allows us to observe the count of churned and retained customers in each category, helping us understand the differences in churn rates between these two demographic groups. This insight is crucial for tailoring retention strategies specifically for non-senior and senior customers, potentially addressing unique needs and concerns related to customer churn in each age group.

![Screenshot (226)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/0af17d78-04c1-4626-aae2-b0713e5a7431)

### Sum of Monthly Charges by Contract
The visual "Sum of Monthly Charges by Contract" showcases the total monthly charges generated by customers based on their contract types, such as monthly, 1-year, and 2-year contracts. This visualization enables us to understand the revenue contribution from different contract durations, facilitating better decision-making regarding contract offerings and pricing strategies. By analyzing the total monthly charges across various contract types, we can identify which contracts generate higher revenue and potentially design incentives to encourage customers to opt for longer-term contracts, resulting in increased revenue and improved customer retention.

![Screenshot (225)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/4682312b-8a89-4570-80c8-a82084a82283)

***
## Data Insight

- The churn rate for the company is approximately 27%, indicating a significant churn issue.
- Non-Senior citizens have a slightly higher churn rate compared to Senior customers.
- Customers with no partners and dependents are more likely to churn.
- Month-to-month contract holders have a higher churn rate than those with longer-term contracts.
- Customers with Fiber optic internet service have a higher churn rate than DSL users.
- Customers who have experienced technical issues (raised tech tickets) are more likely to churn.
  
***

### Dashboard for Retention Manager

Based on our analysis, we created an interactive dashboard using Power BI to monitor and track KPIs related to customer churn. The dashboard includes visualizations for the following KPIs:

-![Screenshot (229)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/e24cff48-ba4c-4600-9c85-1654b1a368af)


### Email to the Engagement Partner

Subject: Data Analysis - Telecommunication Customer Churn Insights

Dear Retention Manager.
I hope this email finds you well. As per your request, I have conducted a data analysis on the telecommunication customer dataset to understand customer churn and retention trends.

The churn rate for the company is approximately 27%, which indicates a notable churn issue. We have identified several factors influencing churn, including contract type, internet service, and technical support. To address these challenges and improve customer retention, I recommend the following actions:

1. **Contract Options:** Explore incentives for customers to opt for longer-term contracts, as these customers exhibit lower churn rates.

2. **Internet Service Quality:** Investigate the cause of higher churn among customers with Fiber optic internet service. Consider improving service quality and providing special offers to retain these customers.

3. **Tech Support Enhancement:** Enhance technical support services to reduce the number of raised tech tickets and improve customer satisfaction.

4. **Promotional Offers:** Introduce personalized promotional offers for customers who have been with the company for an extended period, encouraging loyalty and reducing churn.

The interactive dashboard I created using Power BI will allow the retention manager to monitor the defined KPIs and take timely actions to retain valuable customers.

Please find the attached Power BI report and the dataset for your reference.

If you have any questions or need further assistance, please feel free to reach out.

Thank you for entrusting me with this analysis. I believe implementing these recommendations will lead to improved customer retention and business growth.

Best regards,

(Name)
Data Analyst

***
## TASK 4 -Diversity and Inclusion Analysis Project

### Dataset Description:

The dataset used for this analysis contains employee information, including Employee ID, Gender, Age, Nationality, Job Level, Promotion status, Performance ratings, Hiring details, Turnover status, etc. The data covers a period from FY20 to FY21. The Dataset has 500 rows and 32 columns in total.

### Data Preparation:

1. Load the dataset into Power BI and create a data model.
   
![Screenshot (231)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/47c11baa-faaa-4803-bae8-14714f9d078f)

2. Clean the data by handling missing values, data type conversions, and formatting.

  Using Power Querry i replaced N to No and Y to Yes, i removed column that are not impoortant for the analysis.

4. Create calculated columns for relevant fields like 'Time to Fill,' 'Time in Job Level @01.07.2020,' etc., as needed for the analysis.

### Measures Table:

| Measure Name                   | DAX Formula                                                                                       |
|--------------------------------|---------------------------------------------------------------------------------------------------|
| Number of Hires                | COUNTROWS('YourTableName')                                                                        |
| Number of Men                  | CALCULATE(COUNTROWS('YourTableName'), 'YourTableName'[Gender] = "Male")                           |
| Number of Women                | CALCULATE(COUNTROWS('YourTableName'), 'YourTableName'[Gender] = "Female")                         |
| Diversity Hiring Rate          | DIVIDE(COUNTROWS(FILTER('YourTableName', 'YourTableName'[Target hire balance] = "Diverse")), COUNTROWS('YourTableName')) |
| Employees Promoted FY21       | COUNTROWS(FILTER('YourTableName', 'YourTableName'[Promotion in FY21?] = "Yes"))                    |
| Percentage of Women Promoted   | DIVIDE(COUNTROWS(FILTER('YourTableName', 'YourTableName'[Promotion in FY21?] = "Yes" && 'YourTableName'[Gender] = "Female")), COUNTROWS(FILTER('YourTableName', 'YourTableName'[Promotion in FY21?] = "Yes"))) |
| % of Women Hired              | DIVIDE(COUNTROWS(FILTER('YourTableName', 'YourTableName'[New hire FY20?] = "Yes" && 'YourTableName'[Gender] = "Female")), COUNTROWS(FILTER('YourTableName', 'YourTableName'[New hire FY20?] = "Yes"))) |
| % of Men Hired                | DIVIDE(COUNTROWS(FILTER('YourTableName', 'YourTableName'[New hire FY20?] = "Yes" && 'YourTableName'[Gender] = "Male")), COUNTROWS(FILTER('YourTableName', 'YourTableName'[New hire FY20?] = "Yes"))) |
| Average Performance Rating: Men   | CALCULATE(AVERAGE('YourTableName'[FY20 Performance Rating]), 'YourTableName'[Gender] = "Male")   |
| Average Performance Rating: Women | CALCULATE(AVERAGE('YourTableName'[FY20 Performance Rating]), 'YourTableName'[Gender] = "Female") |
| Employee Turnover Rate         | DIVIDE(COUNTROWS(FILTER('YourTableName', 'YourTableName'[FY20 leaver?] = "Yes")), COUNTROWS('YourTableName')) |
| Voluntary vs. Involuntary Turnover | SUMMARIZE('YourTableName', "Voluntary", CALCULATE(COUNTROWS('YourTableName'), 'YourTableName'[FY20 leaver?] = "Yes" && 'YourTableName'[In base group for turnover FY20] = "Yes"), "Involuntary", CALCULATE(COUNTROWS('YourTableName'), 'YourTableName'[FY20 leaver?] = "Yes" && 'YourTableName'[In base group for turnover FY20] = "No")) |


### Analysis Visualizations:

#### Hiring Analysis:

1. Number of Hires by Gender:
   - Visualize the number of male and female hires using a stacked bar chart.

2. Diversity Hiring Rate:
   - Display the percentage of diverse hires with a card visualization.

3. % of Women Hired:
   - Show the percentage of female hires among total hires using a donut chart.

4. % of Men Hired:
   - Show the percentage of male hires among total hires using a donut chart.

#### Promotion Analysis:

5. Employees Promoted in FY21:
   - Display the count of employees promoted in FY21 using a card visualization.

6. Percentage of Women Promoted:
   - Show the percentage of women among promoted employees using a donut chart.

#### Performance Analysis:

7. Performance Rating Distribution:
   - Visualize the distribution of performance ratings with a histogram.

8. Average Performance Rating by Gender:
   - Compare the average performance rating of men and women using a clustered bar chart.

#### Turnover Analysis:

9. Employee Turnover Rate:
   - Display the overall employee turnover rate using a card visualization.

10. Voluntary vs. Involuntary Turnover:
   - Show the breakdown of voluntary and involuntary turnover using a pie chart.

### Root Causes of Slow Progress:

- Limited Internal Mobility
- Bias in Hiring and Promotion
- Performance Management Issues
- Lack of Training and Development
- Inadequate Diversity and Inclusion Initiatives
- Poor Employee Engagement
- High Turnover and Loss of Talent
- Organizational Structure and Bureaucracy

### Conclusion:

In this Diversity and Inclusion Analysis Project, we analyzed various key performance indicators related to employee hiring, promotion, performance, and turnover with a particular focus on diversity and inclusion metrics. The dataset allowed us to gain insights into the organization's HR practices and identify areas for improvement in promoting diversity and inclusion within the workforce. The visualizations and root cause analysis provide valuable insights to help drive data-driven decisions and initiatives aimed at fostering a diverse and inclusive work environment.

*Note: The images used in this example are for illustrative purposes only and do not represent actual data or analysis.*
