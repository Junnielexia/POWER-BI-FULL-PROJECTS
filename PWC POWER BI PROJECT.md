# TASK 1: What do you hope to learn from this Experience

As a beginner data analyst, the Digital Accelerator programme's PowerBI journey offers an exciting opportunity for growth. My main focus is mastering data visualization, enabling me to transform complex data into interactive visualizations for better client understanding and informed decision-making. Additionally, I am eager to explore automation in PowerBI to enhance process efficiency, freeing up time for strategic initiatives. Integrating machine learning into PowerBI excites me as it opens doors to intuitive problem-solving. Furthermore, I plan to develop strong skills in digital storytelling to effectively communicate data insights and drive positive change. I am enthusiastic about this transformative experience and eager to contribute to the organization's digital transformation.

# TASK 2 CALL CENTRE TREND ANALYSIS

## Introduction

The **Introduction** section provides a brief overview of the document, setting the context for the reader. It explains the purpose of the document and introduces the virtual internship with PwC Switzerland. As part of this internship, I have been provided with a dataset that plays a crucial role in accomplishing the second internship task.

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

## Initial Data Exploration

 During this phase, I examined the dataset using powequerry feature in POWER BI to gain insights into its composition, identifying any potential issues such as missing values, outliers, or data inconsistencies. This preliminary exploration helps lay the foundation for further data analysis and processing.
 
 ![Screenshot (192)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/a36682cc-fe30-4a6e-be8d-f88c18c23d65)


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

# Creating New Measure
I created a New Measure Table TO ADD  all the new measures i created for clarity and easy of report.

| Measure Name                 | DAX Expression                                                                                                 | Explanation                                                                                                  |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Abandonment Rate             | `DIVIDE(CALCULATE(COUNTROWS(Sheet1), Sheet1[Answered (Y/N)] = "N"), COUNTROWS(Sheet1)) * 100`                 | Calculates the percentage of calls abandoned by dividing the count of unanswered calls by the total call count and multiplying by 100.                                  |
| Average Handle Time          | `(AVERAGE(Sheet1[Speed of answer in seconds]) + AVERAGE(Sheet1[AvgTalkDuration])) / 2`                        | Calculates the average handle time by averaging the speed of answer and average talk duration for each call. |
| Average Speed of Answer (ASA)| `AVERAGE('Sheet1'[Speed of answer in seconds])`                                                               | Computes the average speed of answer in seconds for all answered calls.                                    |
| Average Talk Duration        | `AVERAGE(Sheet1[AvgTalkDuration])`                                                                            | Computes the average talk duration for all calls.                                                            |
| First Call Resolution Rate   | `DIVIDE(CALCULATE(COUNTROWS(Sheet1), Sheet1[Resolved] = "Y"), COUNTROWS(Sheet1)) * 100`                       | Calculates the percentage of calls resolved on the first attempt.                                           |
| Overall Customer Satisfaction| `AVERAGE('Sheet1'[Satisfaction rating])`                                                                      | Computes the average satisfaction rating to gauge overall customer satisfaction.                          |
| PositiveSatisfactionCount    | `CALCULATE(COUNTROWS(Sheet1), FILTER(Sheet1, Sheet1[Satisfaction rating] >= 4 && Sheet1[Satisfaction rating] <= 5))` | Counts the number of positive satisfaction ratings (ratings from 4 to 5).                                 |
| Total Call Answered          | `COUNTX(FILTER('Sheet1', 'Sheet1'[Answered (Y/N)] = "YES"), 'Sheet1'[Answered (Y/N)])`                         | Counts the number of calls that were answered.                                                              |
| Total Calls                 | `CALCULATE('NEW MEASURE'[Total Call Answered] + 'NEW MEASURE'[Total Unanswered Calls])`                        | Computes the total number of calls (answered and unanswered) by summing up the counts of each.               |
| Total Unanswered Calls       | `COUNTX(FILTER('Sheet1', 'Sheet1'[Answered (Y/N)] = "NO"), 'Sheet1'[Answered (Y/N)])`                           | Counts the number of unanswered calls.                                                                      |


![Screenshot (200)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/f034a339-2b9d-423c-af4b-b9d454ee2393)



  
 

