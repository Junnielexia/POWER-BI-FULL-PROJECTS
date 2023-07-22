# DATA STRUCTURE

The Olist dataset is a comprehensive e-commerce dataset from Brazil, comprising multiple interconnected tables, capturing various aspects of the customer journey, product information, and seller performance in the marketplace.

![Screenshot (167)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/1c2bb14a-2725-48a3-b02a-b2312825e796)

# Importing Dataset into Power_Bi

To import a dataset into Power BI, you can use the "Get Data" option in Power BI Desktop, connect to your data source, and select the appropriate file format or data connection method to load the dataset into your Power BI project for analysis and visualization.

![Screenshot (162)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/42341aa0-1ed4-4dc6-a411-cdda20b339b6)

# Renaming the Data 
I renamed the data within Power BI by utilizing the 'Transform Data' option in Power Query Editor. I selected the columns and tables I wanted to rename, right-clicked on them, and chose 'Rename.' By doing this, I improved the dataset's field names to make them more meaningful and aligned with my data analysis objectives, enhancing the overall clarity and interpretability of the data. 

![Screenshot (165)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTSvisua546/440bafeb-c0ff-4440-87ee-731760796670)

# DATA CLEANING
Data cleaning is a crucial step in the data analysis process where I ensure the dataset is accurate, consistent, and free from errors or inconsistencies. By removing duplicates, handling missing values, standardizing formats, and correcting inaccuracies, I improve the quality of the data, enabling more reliable and meaningful insights during the analysis phase.

# BUILDING THE MODEL

When building the model in Power BI, I focus on structuring and transforming the data to create a cohesive foundation for analysis and visualization. 

![Screenshot (163)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/0fb90d77-fc64-44d0-8e5d-fa597cc6108c)

## creating connections to all table

Power BI's data modeling capabilities allow me to establish relationships between tables, enabling seamless data navigation and insights. By building the model, I can efficiently explore data patterns, identify trends, and gain valuable business insights, empowering data-driven decision-making processes for stakeholders and end-users.

![Screenshot (164)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/0e378c04-febe-4563-b696-9ada25efdc11)


# CREATING NEW TABLE

When creating a new table in Power BI, I use DAX (Data Analysis Expressions) to define calculated tables based on existing data or custom tables using data from various sources. These new tables help enrich the data model by incorporating additional insights, summarizations, or aggregations that facilitate more comprehensive analysis and reporting within Power BI.

## 1. Calendar Table

Creating a calendar table is essential for time-based analysis and reporting. This table contains a sequence of dates with associated attributes like year, month, quarter, and day of the week. By using DAX functions or Power Query to generate the calendar table, I can leverage it as a date dimension to create date-related calculations, time intelligence functions, and support visualizations with time-based filtering capabilities, enabling more insightful and time-aware data analysis in the report.

Formula
Calendar = CALENDAR(DATE(2016, 9, 4), DATE(2018, 10, 17))

![Screenshot (170)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/1c90c562-9ba5-464b-a311-fba0f2645fb3)

### Connecting the new table to the model

Establishing a relationship between the new calendar table and the root table used to create it enables its responsivity for a seamless connection in the model. 

![Screenshot (169)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/d33e7b35-03e0-4300-a78d-1322601b150d)

## 2. New Measure Table

I created a new measure table to help me add all the new measures in one place. This makes the report comprehensive, and also the analysis to be more organized.

![Screenshot (171)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/cdfda7c4-a778-4d33-9303-5870bcbc7177)

### table of all measures n formula used

- Average Rating = AVERAGE(Review[review_score])
- Averag| Metric                    | Calculation                                                                                  |
|---------------------------|----------------------------------------------------------------------------------------------|
| Average Rating            | AVERAGE(Review[review_score])                                                               |
| Average Shipping Time     | AVERAGEX('Order_Delivery', DATEDIFF('Order_Delivery'[order_purchase_timestamp], 'Order_Delivery'[order_delivered_customer_date], DAY)) |
| Sales by Product Category | SUM('Order_Items'[payment_value]) / COUNTROWS(DISTINCT('Products'[product_category_name]))  |
| Total Customers           | COUNT(Customers[customer_id])                                                               |
| Total Freight Cost        | SUM('Order'[freight_value])                                                                 |
| Total Orders              | COUNT('Order'[order_id])                                                                     |
| Total Products Sold       | SUM('Order_Items'[count])                                                                    |
| Total Revenue             | SUM(Order_Items[payment_value])                                                              |


# Calculated Column

A calculated column in Power BI is created by using DAX to define a new column based on calculations performed on existing columns, which enhances the dataset with additional insights and enables more flexible and dynamic analysis in reports.

1. Hour of the day column from the Order purchase timestamp.
   HourOfDay = HOUR('Order_items'[Order_Purchase_timestamp])

# KPI

Key Performance Indicators (KPIs) i
are metrics or measures that help track and evaluate the performance of specific aspects of a business or project, providing valuable insights for decision-making by visually representing the progress towards achieving goals and objectives. They are typically displayed as dynamic visualizations on Power BI reports and dashboards, allowing users to monitor performance in real-time and identify areas that require attention or improvement.

card visual- using the Card Visuals, I generated KPI's from the new measures created

## Result 1:

![Screenshot (172)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/d5093394-430c-4a7f-86ee-b32d81a840e6)

## Result 2:

![Screenshot (173)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/9b4236bf-b697-4c88-8093-56b6d86272b2)

# Report

A report is a visual representation of data analysis and insights derived from various data sources. It typically includes interactive charts, tables, graphs, and other visualizations that communicate key findings, trends, and patterns in the data. Power BI reports enable users to explore data, gain valuable insights, and make data-driven decisions by providing a clear and intuitive representation of complex information.


## 1. Total Freight by State
"Total Freight by State" refers to the cumulative cost of shipping goods for each individual state, and it is important because it provides insights into regional shipping expenses, helping businesses optimize logistics, identify cost-saving opportunities, and make informed decisions on distribution strategies.

   
![Screenshot (174)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/dc320614-a027-4c02-9a52-120f2ee36ca6)

## 2. Total Customers by City

"Total Customers by City" represents the count of unique customers residing in each city, and it is important for businesses to understand their customer distribution, target specific regions for marketing efforts, and tailor strategies to meet the unique needs and preferences of customers in different cities.

![Screenshot (175)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/de5d2364-6b19-4734-874d-aea6c93f34b0)

## 3. Total Product Sold by Royalty Category
"Total Products Sold by Royalty Category" indicates the quantity of products sold in each royalty category, and it is valuable for analyzing the popularity and demand for different product categories, guiding inventory management, and identifying revenue-generating product segments for maximizing profitability.

![Screenshot (176)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/a5c6dbf8-5840-4f37-a185-0be936e45a4f)
 
## 4. Average Rating by Product Category

"Average Rating by Product Category" calculates the mean rating given by customers for each product category, providing insights into customer satisfaction levels across different product types and guiding businesses in understanding which categories perform well or need improvement to enhance overall customer experience.

![Screenshot (178)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/32da237b-93c7-4b1c-84cf-14d3dcca704d)

## 5. Average Rating by Order_Status

"Average Rating by Order_Status" calculates the mean rating provided by customers for each order status, allowing businesses to gauge customer satisfaction levels at various stages of the order process, identify potential issues affecting customer experience, and take corrective actions to improve overall service quality and customer retention.

![Screenshot (179)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/1c44eaeb-38df-4c92-ad99-b9422c0b174b)

## 6. Sum of Payment Value by Payment Method

"Sum of Payment Value by Payment Method" calculates the total payment amount received for each payment method used by customers, providing insights into the most preferred payment methods, potential trends in transaction volumes, and guiding businesses in optimizing payment processing options to enhance customer convenience and efficiency.

![Screenshot (180)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/998cf387-b1f7-4a36-9d8d-bb44efeb83f4)

## 7. Order by Hour of the Day

"Order by Hour of the Day" groups and counts the number of orders placed for each hour of the day, helping businesses identify peak hours and trends in customer buying behavior, enabling better resource allocation, and optimizing operations to meet demand fluctuations efficiently.

![Screenshot (181)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/de7f71f2-5a5c-4daa-a992-3db6cd3d81e6)

## 8. Total Revenue by Customer City

"Total Revenue by Customer City" sums the revenue generated from sales for each customer city, enabling businesses to analyze revenue distribution across different cities, identify high-value customer locations, and tailor marketing strategies to target specific regions for increased sales and business growth.

![Screenshot (182)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/c20165f0-d265-400e-b4f0-60c02765143d)

## 9. Total Order by Product Category
"Total Order by Product Category" counts the number of orders placed for each product category, helping businesses understand the popularity and demand for different product types, optimize inventory management, and make data-driven decisions to meet customer preferences and increase overall sales.

![Screenshot (183)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/b0d6ec62-0288-4658-b772-0ed4cbd59ff3)

## 10.Sum of Review by State

"Sum of Review by State" represents the total count of reviews received for each state, allowing businesses to assess customer feedback and satisfaction levels on a regional basis, identify areas for improvement, and make data-driven decisions to enhance the overall customer experience in different states.

![Screenshot (184)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/1f6c8d2b-702a-44a4-b191-bcbcd539e6fb)

## 11. Total Order by State

"Total Order by State" calculates the count of orders placed for each state, providing insights into regional sales performance, customer demand, and enabling businesses to focus on specific states for targeted marketing efforts and effective resource allocation to maximize sales and growth opportunities.

###Insight from Data
- At 47433, SP had the highest Total Orders and was 91,117.31% higher than RR, which had the lowest Total Orders at 52.
- ﻿SP accounted for 42.18% of Total Orders.
- Across all 27 geolocation_state, Total Orders ranged from 52 to 47433.

![Screenshot (185)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/46428740-12a6-4975-bee4-b014e3c160f0)

## 12. Total Order by Order status

- At 110197,the status delivered had the highest Total Orders and was 20,231.55% higher than canceled, which had the lowest Total Orders at 542. delivered had the highest Total Orders at 110197, followed by shipped at 1185 and canceled at 542.
- ﻿delivered accounted for 98.46% of Total Orders.
- ﻿delivered had 110197 Total Orders, shipped had 1185, and canceled had 542.

![Screenshot (186)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/f9651bbc-2d26-4d90-8c89-3ce84cc62319)

## 13. Total Revenue by Year
"Total Revenue by Year" computes the sum of revenue generated for each year, enabling businesses to analyze annual sales performance, identify growth trends, and make strategic decisions based on historical revenue data to drive business success and achieve financial objectives.

![Screenshot (187)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/fef1abe5-49fe-4ee6-96bc-9ce9bd5261b2)

## 14. Total Revenue by Month

"Total Revenue by Month" calculates the sum of revenue generated for each month, allowing businesses to analyze monthly sales performance, identify seasonal trends, and make informed decisions based on revenue fluctuations throughout the year to optimize operations and marketing strategies for increased profitability.

### Insight from data
- at 1,661.28, September had the highest Total Revenue and was 1,798.17% higher than October, which had the lowest Total Revenue at 87.52.
- September accounted for 23.41% of Total Revenue.
- Across all 12 Month, Total Revenue ranged from 87.52 to 1,661.28.

![Screenshot (188)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/d6833b80-0005-4307-bf9b-068737245691)

# Dashboard
## first Dashbaord

![Screenshot (189)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/29cbc6f2-167e-4631-94a6-9e64329ba7b1)

## Second Dashboard

![Screenshot (190)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/75692f0f-9438-485a-bb48-39a93022e85d)



