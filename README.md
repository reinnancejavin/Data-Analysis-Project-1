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

3. By using line chart with slicer and dropdown menu, this illustrates the trend of your data, which I included different variety of elements related to which you can sort, select, refine and deselect based on what data you are looking for. 

![Photo4](https://github.com/user-attachments/assets/19931a9b-f63e-4e67-a048-ef58325a5312)

### Results/Findings:

The analysis resuslts are summarized as follows:
1. The company's overall growth shows there is a clear upward trend in revenue over the analyzed years. The cumulative revenue by the hotel was $10.23M from 2018-2020, indicating positive business growth.
   From the segmented hotel type:
   - City Hotel: Higher in revenue, steady year-round growth, with moderate seasonal variations.
   - Resort Hotel: Spikes during summer, July to August are the peak travel seasons, but with more variability in the off-season.
   Both hotel types contribute to growth, but the resort hotel shows stronger dependence on seasonal demand, while the city hotel ensures stability throughout the year.

2. Expanding the parking lot is not an issue on both hotels, since the data allows us to understand that every year, there is an increasing number of cars that visited or parked on the hotels, but the parking percentage is still enough to supply the demand for spaces.

3. ADR peaks during holiday seasons and summer, reflecting strong demand during these periods, especially at the resort hotel. The city hotel maintains a relatively stable ADR, with slight increases during conferences and business travel seasons.
   - Understanding these seasonal patterns allows for optimized pricing strategies, targeted marketing efforts, and operational adjustments to align with guest demand.
  
### Recommendations:

1. - Resort Hotel: Capitalize on seasonal peaks by offering premium packages and experiences (e.g., wellness retreats, special events). Implement advanced booking campaigns to lock in early reservations.
   - City Hotel: Introduce corporate partnerships and loyalty programs to maintain steady revenue streams from business travelers. Expand marketing efforts during non-peak periods to boost occupancy.
  
2. Implement dynamic pricing strategies to maximize ADR during high-demand periods while offering competitive discounts during off-seasons.
3. Use seasonal promotions to attract guests during slower periods, such as bundling room rates with local attractions or dining packages.


### References:

1. https://absentdata.com/data-analysis/where-to-find-data/


OCTOBER 2024

Prepared and Analyzed by:

Reinnance Rafael S. Javin

Data Analyst & Registered Mechanical Engineer 💻
