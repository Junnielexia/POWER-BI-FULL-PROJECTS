# DATA STRUCTURE

![Screenshot (167)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/1c2bb14a-2725-48a3-b02a-b2312825e796)

# Importing Dataset into Power_Bi

![Screenshot (162)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/42341aa0-1ed4-4dc6-a411-cdda20b339b6)

# Renaming the Data 

![Screenshot (165)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/440bafeb-c0ff-4440-87ee-731760796670)

# DATA CLEANING
I ensured that there is no duplicate data,error,empty cells that might affect the accuracy of the analysis in power querry before loading it into power bi workbench.

# BUILDING THE MODEL

![Screenshot (163)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/0fb90d77-fc64-44d0-8e5d-fa597cc6108c)

## creating connections to all table

![Screenshot (164)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/0e378c04-febe-4563-b696-9ada25efdc11)


# CREATING NEW TABLE

## 1. Calendar Table

I created a calendar table using Order_Purchase_Timestamp this would be used to calculate weekly, monthly, quarterly and Yearly analysis 
Formula
Calendar = CALENDAR(DATE(2016, 9, 4), DATE(2018, 10, 17))

![Screenshot (170)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/1c90c562-9ba5-464b-a311-fba0f2645fb3)

### Connecting the new table to the model

![Screenshot (169)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/d33e7b35-03e0-4300-a78d-1322601b150d)

## 2. New Measure Table

I created a new measure table to help me add all the new measures in one place. This makes the report comprehensive, and also the analysis to be more organized.

![Screenshot (171)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/cdfda7c4-a778-4d33-9303-5870bcbc7177)

### table of all measures n formula used

- Average Rating = AVERAGE(Review[review_score])
- Average Shipping Time = AVERAGEX('Order_Delivery', DATEDIFF('Order_Delivery'[order_purchase_timestamp], 'Order_Delivery'[order_delivered_customer_date], DAY))
- Sales by Product Category = SUM('Order_Items'[payment_value]) / COUNTROWS(DISTINCT('Products'[product_category_name]))
- Total Customers = COUNT(Customers[customer_id])
- Total Freight Cost = SUM('Order'[freight_value])
- Total Orders = COUNT('Order'[order_id])
- Total Products Sold = SUM('Order_Items'[count])
- Total Revenue = SUM(Order_Items[payment_value])

# Calculated Column
1. Hour of the day column from the Order purchase timestamp.
   HourOfDay = HOUR('Order_items'[Order_Purchase_timestamp])

# KPI
using the Card Visuals, I generated KPI's from the new measures created

## Result 1:

![Screenshot (172)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/d5093394-430c-4a7f-86ee-b32d81a840e6)

## Result 2:

![Screenshot (173)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/9b4236bf-b697-4c88-8093-56b6d86272b2)

# Report

## 1. Total Freight by State
   
![Screenshot (174)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/dc320614-a027-4c02-9a52-120f2ee36ca6)

## 2. Total Customers by City

![Screenshot (175)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/de5d2364-6b19-4734-874d-aea6c93f34b0)

## 3. Total Product Sold by Royalty Category

![Screenshot (176)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/a5c6dbf8-5840-4f37-a185-0be936e45a4f)
 
## 4. Average Rating by Product Category

![Screenshot (178)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/32da237b-93c7-4b1c-84cf-14d3dcca704d)

## 5. Average Rating by Order_Status

![Screenshot (179)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/1c44eaeb-38df-4c92-ad99-b9422c0b174b)

## 6. Sum of Payment Value by Payment Method

![Screenshot (180)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/998cf387-b1f7-4a36-9d8d-bb44efeb83f4)

## 7. Order by Hour of the Day

![Screenshot (181)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/de7f71f2-5a5c-4daa-a992-3db6cd3d81e6)

## 8. Total Revenue by Customer City

![Screenshot (182)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/c20165f0-d265-400e-b4f0-60c02765143d)

## 9. Total Order by Product Category

![Screenshot (183)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/b0d6ec62-0288-4658-b772-0ed4cbd59ff3)

## 10.Sum of Review by State

![Screenshot (184)](https://github.com/Junnielexia/POWER-BI-FULL-PROJECTS/assets/95970546/1f6c8d2b-702a-44a4-b191-bcbcd539e6fb)







