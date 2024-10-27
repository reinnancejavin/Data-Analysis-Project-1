# Hotel Booking Analysis and Visualization
## Project Overview
This personal project aims to explore hotel booking data to uncover insights, trends, and patterns that can help in understanding booking behavior and optimizing operations. Through data analysis using SQL and PowerBI, it provides actionable insights for decision-making in the hospitality industry.

## Data Sources
Hotel Bookings Data: The primary dataset used for this analysis is the "hotel_bookings.csv" file, containing detailed information about each bookings made by the company. 

## Tools
- SQL Server Management Studio - Data Cleaning and Data Analysis
- Microsoft PowerBI - Dashboards and Reporting

### Data Cleaning/Preparation
In the inital data preparation phase, I performed the following tasks:
1. Data loading and inspection
2. Handling missing values
3. Data cleaning and formatting
4. Creating Database

### Exploratory Data Analysis
EDA involved exploring the hotel bookings to answer the following key questions, such as:
1. Is our hotel revenue growing by year? (We have two hotel types so it would be good to segment revenue by hotel type)
2. Should we increase our parking lot size? (We want to understand if there is a trend is guest with personal cars)
3. What trends we see in our data? (Focus on average daily rate and guests to explore seasonality)

### Data Analysis
```sql
with hotels as (
select * from dbo.['2018$']
union
select * from dbo.['2019$']
union
select * from dbo.['2020$'])

select
arrival_date_year,
hotel,
round(sum((stays_in_week_nights+stays_in_weekend_nights)*adr),2) as revenue
from hotels
group by arrival_date_year, hotel
```
### Data Visualization
In this segment, I created the overall look of the dashboard to highlight the project overview and gain insights from the Exploratory Data Analysis.

![Dashboard#1](https://github.com/user-attachments/assets/e7f36101-9251-40cc-b399-d8e534964147)

By using Microsoft PowerBi, I utilized different tools such as line chart, slicer, donut chart and table to showcase the visual of the data made from the query from SQL. 
In this part of my learning process, I showcase and discovered how easily PowerBI interpret the data through visualization and maximize your insights base on the query. 

Here are some examples:
1. By using donut chart, it showcase the different revenue of types of hotel and distinguished City or Resort Hotel, which can be answered and reflect from the EDA.
   
![Photo2](https://github.com/user-attachments/assets/d0107ca9-7d3f-4e58-aba4-0c5274572f7f)

2. By using the slicer, this can filter the data visualization by which you would like to know, from year, sum of revenue, required car parking spaces and and parking percentage as well.

![Photo1](https://github.com/user-attachments/assets/529df37a-f345-4e79-9f41-bc08e6249c57)






