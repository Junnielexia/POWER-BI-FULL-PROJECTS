# FIFA 2021 DATA CLEANING PROJECT USING POWER-BI
![image](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/2dbc1264-309f-4786-b391-023c4a5393e3)


## Title: Data Cleaning using Power BI: A Comprehensive Guide

# Introduction

Welcome to the Idiot's Guide to Data Cleaning and Analysis with Power BI! In this guide, we will explore the importance of data cleaning in the data analysis process and introduce you to Power BI, a powerful tool for both data cleaning and analysis. By following the steps outlined here, even someone with little to no prior experience can learn how to prepare and analyze data effectively. 
***

## Overview of the Importance of Data Cleaning in the Data Analysis Process

Data cleaning plays a vital role in the data analysis process. It involves identifying and resolving issues such as missing values, inconsistencies, inaccuracies, and outliers in datasets. By cleaning the data, we ensure that it is accurate, reliable, and suitable for analysis. Without proper data cleaning, the results obtained from data analysis can be misleading or incorrect, leading to flawed conclusions and decisions.
***

## Introduction to Power BI as a Powerful Tool for Data Cleaning and Analysis

Power BI is a popular business analytics tool developed by Microsoft. It provides a user-friendly interface and powerful features for data cleaning, visualization, and analysis. With Power BI, you can connect to various data sources, transform and clean your data, create interactive visualizations, and gain valuable insights from your data.

![Screenshot (124)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/57da219c-e96b-46a9-9be3-2803ee96e6fa)

***

## 1. Data Preparation

Before we dive into data cleaning, we need a dataset to work with. In this guide, we will be using the FIFA 2021 dataset, which contains information about football players from around the world. You can download this dataset from [KAGLE].

**Importing the FIFA 2021 Dataset into Power BI**

To import the FIFA 2021 dataset into Power BI, follow these steps:

1. Launch Power BI Desktop.
2. Click on "Get Data" in the Home tab.

![Screenshot (123)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/107aed6f-ab5e-413d-90c4-116707ae407a)

3. Select the appropriate file format for your dataset (e.g., Excel, CSV, etc.).
   
![Screenshot (126)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/af96a72c-4a43-4153-9c36-3158c92b1ddd)

4. Locate and select the FIFA 2021 dataset file on your computer.
5. Click "Load" to import the dataset into Power BI.
   
![Screenshot (121)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/2834c742-64e4-49b2-9457-f117cc82fdce)


**Opening the Power Query Editor for Data Cleaning Tasks**

Once the dataset is imported, Power BI will open the Power Query Editor, which is a powerful tool for data transformation and cleaning. In the Power Query Editor, you can perform various data cleaning tasks, such as removing duplicates, handling missing values, renaming columns, and more.

To open the Power Query Editor, follow these steps:

1. In Power BI Desktop, go to the Home tab.
2. Click on "Edit Queries" in the External Data group.
3. The Power Query Editor will open, displaying a preview of your dataset.

![Screenshot (127)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/cc279749-a383-4b4f-8470-dc99526878ac)


**Initial Data Exploration and Understanding the Dataset Structure**

Before diving into data cleaning, it's essential to explore and understand the structure of your dataset. This exploration helps you identify any potential issues and plan your cleaning strategies accordingly. In Power Query Editor, you can perform the following tasks for initial data exploration:

1. View the dataset preview: The Power Query Editor displays a preview of your dataset, allowing you to see the first few rows and columns.

2. Examine column headers: Check the column names and ensure they are meaningful and correctly labeled.

3. Check data types: Verify that the data types assigned to each column are appropriate. For example, numeric values should be recognized as numbers, dates as dates, and text as text.

4. Identify missing values: Look for any blank cells or placeholders that indicate missing values. Missing values need to be handled appropriately during the data cleaning process.

By performing these initial exploration tasks, you will gain a better understanding of the dataset's structure and identify potential areas that require data cleaning.
***

## FIFA 2021 Dataset

The FIFA 2021 dataset is a valuable resource obtained from Kaggle, providing detailed information on 18,979 football players. With 77 columns capturing player statistics and demography for the year 2021, you can explore a wide range of data, including unique identification numbers, names, ages, nationalities, positions, overall ratings, wages, contracts, and more. This comprehensive dataset offers valuable insights for analyzing player performance, studying demographics, and exploring various attributes within the footballing world of 2021.

**Project Goals**

To facilitate effective data analysis, this project sets out to accomplish the following goals:

1. **Identify and resolve duplicate entries:** Detect and eliminate redundant records in the dataset to ensure data accuracy and integrity.

2. **Handle missing values:** Address incomplete or missing data points through appropriate techniques such as imputation or strategic decision-making.

3. **Rectify incorrect data types:** Ensure each data field is assigned the appropriate data type to enable accurate analysis and interpretation.

4. **Correct calculation errors:** Identify and rectify discrepancies or errors in calculations across rows and columns to ensure reliable analysis outcomes.

5. **Address spelling and value errors:** Identify and rectify inconsistencies or inaccuracies in spellings or values to enhance data quality and integrity.

6. **Handle null entries:** Identify and manage instances of null entries to ensure data completeness and reliability.

By accomplishing these project goals in a systematic manner, we will achieve a clean and reliable dataset that can be effectively utilized for further analysis and insightful decision-making.

***

### Insight from Column

Enabling column profile distribution and quality in the View tab is essential for gaining insights into data distribution, assessing data quality, identifying discrepancies, validating data, and improving data exploration capabilities. This feature allows you to understand the distribution of data in a column, evaluate its quality, and identify any issues that need attention.

![Screenshot (132)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/d013e5dd-74be-4420-bcdf-549877f43c37)
***

**Removing Irrelevant Columns**
To remove the Photo URL column in Power Query using Power BI, follow these steps:

1. Open the Power Query Editor in Power BI by selecting the relevant table or query and clicking on the "Edit Queries" button.
2. Locate the Photo URL column in the list of columns.
3. Right-click on the Photo URL column header and select "Remove" or "Delete."
4. Power Query will eliminate the Photo URL column from the dataset, ensuring that it no longer appears in your analysis.

By removing irrelevant columns like the Photo URL, you can streamline your data cleaning process and focus on the essential attributes that drive meaningful insights and analysis.

![Screenshot (121)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/43093f88-d506-45e5-8da2-0930d2c98419)

**Removing Whitespace**

To remove whitespace and make the spreadsheet appear normal-sized, follow these steps:

1. Click on the View tab.
2. Uncheck the "Whitespace" button.
***

### Standardizing Data Formats

**ID Column: Conversion from Numeric to Text**

Treating the ID column as text aligns with its purpose, which is typically to serve as a unique identifier or reference rather than a value for mathematical calculations. By preserving the textual nature of IDs, it becomes easier to interpret and maintain their intended purpose throughout data analysis or integration with other systems.

To convert the ID column from number to text in Power Query within Power BI, follow these steps:

1. Open the Power Query Editor in Power BI by selecting the relevant table or query and clicking on the "Edit Queries" button.

2. Locate the ID column that you want to convert.

3. Right-click on the ID column header and select "Change Type."

4. Choose "Text" as the data type for the ID column.

5. Power Query will automatically convert the ID column from number to text format.

![Screenshot (130)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/259cee0a-d689-4950-8d43-2f0a77aed4c0)

***

### Extracting Names from Player URL

Due to the presence of special characters in some of the player names columns, it was decided to extract their names from the player URLs. To extract names from a player URL in Power Query within Power BI, follow these steps:

1. Open the Power Query Editor and select the column containing the player URLs.
2. Right-click on the column header and choose "Split Column" -> "By Delimiter." Specify the delimiter (such as "/") and choose the option to split into separate columns.
3. Delete the unnecessary columns, keeping only the column that contains the player names.
4. To remove the dash between each name, right-click on the column header and choose "Replace Values." Replace the dash with an empty value.
5. To capitalize the first letter of each name, right-click on the column header, choose "Transform," and then select "Capitalize Each Word." Also, rename the column to FullName for better clarity.
 
![Screenshot (135)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/d364ae11-9695-48af-b98d-dc32238c68d1)

### Age and Nationality Column

The Age and Nationality columns are intact and will remain untouched as they have no duplicate data, missing data, or errors.

![Screenshot (136)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/9a0fc23c-9a04-4650-96a1-4e3c1db9d54e)
***

### Overall Rating (OVA) and Potential Rating (POT)

To convert the Overall Rating (OVA) and Potential Rating (POT) columns into percentages, follow these steps:

1. In the Power Query Editor, go to the Transform tab and select Divide from the mathematics pack.
2. Enter 100 as the variable to divide the columns with.
3. Convert the data type to percentage.

![Screenshot (138)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/7789d1eb-16ca-496b-a1e2-f2cf11d46b5b)
***

### Contract Column

The Contract column contains information about the start and end dates of players' contracts, indicating their duration in years. However, there is a diversity of contract types, including paid contracts, loan agreements, and free transfers.

![Screenshot (139)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/515034af-a637-4cbc-bdaa-a0bf12110615)

To gain more insight from the data, it is important to create a Player Status column to determine whether a player is currently on a contract, loan, or free transfer. A conditional column called Player_status was created for this purpose.

![Screenshot (140)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/33b9ecd7-1839-4cd6-94b5-1262ac315c80)

**Final Result**

![Screenshot (142)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/f734467d-e7f7-46ff-a277-e1dd0256d16a)

TO Further break the data into a abetter detailed format its advisable to split the contract date column into contract begin date and contract end date.

![Screenshot (143)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/c6cb3dc4-0cba-4d11-85fa-0504ee317523)

**Replacing Error**

- To solve the arising error from the empty data cells, I replaced errors with null values.
- I also added another custom column to calculate the duration of the contract.

**Results**

![Screenshot (146)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/2a40a978-da76-4b4d-a613-a329c119eadb)

***

### Height Column

To change the height column containing inches and cm, use the formula:
```text
if Text.EndsWith([Height], "cm") then
    try Number.FromText(Text.Start([Height], Text.Length([Height]) - 2))
    otherwise null
else
    try Number.FromText(Text.Start([Height], Text.Length([Height]) - 2)) * 30.48
    otherwise null
```
***

### Weight Column

To change the weight from kg and lbs to only lbs entries, use the formula:
```text
if Text.Contains([Weight], "kg") then Number.From(Text.BeforeDelimiter([Weight], "kg")) * 2.20
else Text.BeforeDelimiter([Weight], "lbs")
```

![Screenshot (147)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/8e4fe35c-3d25-448c-8567-5ff869d67003)

***

## Handling Missing Values
In the data cleaning process, one crucial step is handling missing values effectively. Missing values can occur due to various reasons such as data entry errors, system issues, or incomplete data. It is essential to address these missing values to ensure the accuracy and reliability of the analysis.

### Loan Date End Column

To standardize the loan date end column, I replaced all the blank cells with "not on Row" using the Transform Data tab.

![Screenshot (148)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/ebd11e21-dd95-4b5b-ba39-6fb051aeae23)

***

### The Value, Wage, and Release Clause Column

In the Value, Wage, and Release Clause column, which indicates the market value, weekly wage, and release clause of players in FIFA 2021, I observed that some records use 'M' to denote millions and 'K' to denote thousands. To convert these values into currency format, I implemented a conditional statement. I removed the 'M,' 'K,' and '€' symbols, and then multiplied the column by 1,000,000 for 'M' values and by 1,000 for 'K' values using a Conditional Column.

![Screenshot (153)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/495b42b8-4d1c-4220-aa4b-3cb3a1b7791d)

### Final Results

![Screenshot (151)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/5e10b15c-76ac-4c8b-aab7-82e5d17d6134)
***

### Hits Column

In the Hits column, I noticed that some values contain 'k'. To convert these values from text to numeric format without errors, I replaced 'k' with 1000.

![Screenshot (157)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/aa52d6c3-e912-4948-bc2b-2e7e9257f65b)

**Solution used**

![Screenshot (160)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/600dd80c-33ac-4938-b529-fdb5d4b14a65)

**Final result**

![Screenshot (158)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/27e42718-7243-40c0-b833-67dfcca153fc)

***
### W/F, S/M, and IR Column

The W/F, S/M, and IR columns represent a player's weak foot rating, skill move rating, and international rating, respectively. The ratings range from 1 to 5. To simplify the data and change the data type to whole numbers, I replaced the star rating values and made the necessary adjustments.

![Screenshot (154)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/e1d92d99-7c33-427a-bf72-65916fb2ce94)

**Solution used**

![Screenshot (154)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/df1964cc-2473-4bc4-ba52-8ad7eb143d29)


**Final result after replacement and changing data type**

![Screenshot (156)](https://github.com/Junnielexia/DATA-ANALYSIS-TRAINING/assets/95970546/719122af-01c2-4acf-a631-d0dc2d5f814f)

***

## Standardizing Data Formats

In order to ensure accuracy and integrity, the following attributes were thoroughly reviewed:

| Attribute             | Attribute             | Attribute             | Attribute             | Attribute             |
|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|
| Attacking             | Crossing              | Finishing             | Heading Accuracy      | Short Passing         |
| Volleys               | Skill                 | Dribbling             | Curve                 | FK Accuracy           |
| Long Passing          | Ball Control          | Movement              | Acceleration          | Spring Speed          |
| Agility               | Reactions             | Balance               | Power                 | Shot Power            |
| Jumping               | Stamina               | Strength              | Long Shot             | Mentality             |
| Aggression            | Interception          | Positioning           | Vision                | Penalties             |
| Composure             | Defending             | Marking               | Standing Tackle       | Sliding Tackle        |
| Goalkeeping           | GK Handling           | GK Diving             | GK Kicking            | GK Positioning        |
| GK Reflexes           | Total Stats           | Base Stats            | Pace                  | Shooting              |
| Passing               | DRI                   | DEF                   | Physical              | Best Position         |
| Preferred Foot        | Attacking Work Rate   | Defensive Work Rate   |                       |                       |

During the thorough review, special attention was given to each attribute to ensure accuracy and integrity. The data types were carefully assigned, and any erroneous column names were rectified, guaranteeing data consistency and reliability throughout the analysis.

## Conclusion
In conclusion, the data cleaning process using Power BI has been instrumental in ensuring accurate and reliable analysis. Through techniques such as handling missing values, standardizing data formats, and transforming variables, the data has been prepared for meaningful insights and decision-making.

Data cleaning is a vital step in any analysis workflow as it enhances the quality of the data and reduces potential errors. Power BI provides powerful tools and functionalities that simplify and streamline the data cleaning process. By utilizing Power BI, analysts can efficiently handle missing values, transform variables, and standardize data formats, enabling them to draw accurate conclusions and make informed decisions based on reliable data.

By following this comprehensive guide, users can effectively utilize Power BI for data cleaning, transforming raw data into a clean and structured format, and uncover meaningful insights from the FIFA 2021 dataset.
