# Maven Toys Challenge

### Dashboard Link : https://project.novypro.com/dfxxtl
## Problem Statement

### Analysis to be done
-	The Maven Toys Challenge involves analyzing toy store sales data to uncover key insights about revenue, profit, orders, and trends to help the business make informed decisions.
#### Key objectives for the project include:
-	Identifying Top Products and Categories: Analyze which products and categories are most profitable and have the highest sales volumes.
-	Understanding Seasonal Trends: Examine how sales fluctuate month-to-month or across seasons. This can help identify slow periods (e.g., February and August historically show lower sales) where targeted promotions may boost revenue.
-	Store and Location Performance: Explore store-level performance, such as which cities or store types (e.g., airports, residential) generate the most profit. Insights can guide decisions on opening new stores or optimizing existing ones.
-	Product Overview and Performance: Explore category - level performance, such as  Arts and Crafts,elctronics and specific products that generate the most profit. 
-	Stock Management: Assess inventory levels and profitability of products in stock, ensuring the business maintains optimal stock levels for high-performing items while addressing excess inventory.


### About the dataset
-	This dataset contains 4 tables, in CSV format:
-	The Products table contains the 35 products sold at Maven Toys (each record represents one product), with fields containing details about the product category, cost, and retail price
-	The Stores table contains the 50 Maven Toys store locations (each record represents one store), with fields containing details about the store location, type, and date it opened
-	The Sales table contains the units sold in over 800,000 sales transactions  (each record represents the purchase of a specific product at a specific store on a specific date)
-	The Inventory table contains over 1,500 records that represent the stock on hand of each product in each store.
-	The Targets for each metrics increases by 10% of the previous month.

### Landing page
![landing page](https://github.com/user-attachments/assets/e3914d21-3899-4e04-951d-ec854d4a56b0)

### Report level Interactivity
![interactivity](https://github.com/user-attachments/assets/3ddf654c-1f71-4162-b713-88e0bd17651b)

You will find a page navigator  in every page to navigate to different pages of the report and a clear all slicer to see the unfiltered visuals in the page.




## Dashboards and reports and critical  visuals explained

## Executive dashboard
![Exec dash project](https://github.com/user-attachments/assets/1b7cbfa7-616d-4594-bbcd-8fbbd0d57c06)

### 1. Report Overview:
- Purpose: To provide an executive summary of the toy store’s financial and operational performance for a given period.

- Audience: This dashboard is designed for business managers and executives to quickly assess revenue, profit, orders, and top-performing products.

### 2. Key Metrics Highlighted (top right):
- Total Revenue: Shows the total revenue generated within the selected time frame.
-  Total Profit : Indicates the net profit after deducting expenses.
-Total Orders :Reflects the total number of customer orders processed during the period.
 - #### Includes a small trendline for visualizing performance fluctuations over time for all the above metrics.


### 3. Monthly Revenue Trends :
- Chart Description: A line chart showing month-by-month revenue trends.Provides clear insights into revenue spikes (e.g., March 2023 and July 2023) and declines (e.g., September 2023). Highlight months with the highest and lowest revenue.Discuss potential reasons for fluctuations, such as seasonal demand, promotions, or other factors.

### 4. Key Metrics for Comparison (bottom left):
 ####   Includes the variance to highlight underperformance or achievement against the target.
- Monthly Revenue: Shows the latest month’s revenue with a comparison to the previous month and target value.
- Monthly Profit: Highlights monthly profit and compares it to the target and previous performance.
- Monthly Orders: Reflects the order count for the most recent month, including target and actual differences.

### 5. Matrix for top 10 products:
- Shows top 10  performing product names with revenue,total orders and total profit figures.

### 6. Best perfroming Products:
Highlighting the the top perfroming category in terms of best selling and most ordered product.

## What-if analysis
![image](https://github.com/user-attachments/assets/14a65d42-f53c-4eb5-a639-777f3baa9837)



### Purpose of the Report
- This dashboard allows users to perform What-If analysis by altering metrics and filtering data based on cities or store locations and changes in metrics like quantities sold etc.
- It helps stakeholders understand the potential impact of changes on revenue, cost, profit, and quantities sold. 
### Key Features of the Dashboard
###  1. Filter Panel (Interactivity): 
- Select specific filters to focus on targeted data. Use the "Clear All" button to reset filters and return to the default view.
-  Product Category and Product Name: Interactive slicers allow users to focus on                             specific Product category and Product name.
-  Store City and Store Location: Interactive slicers allow users to focus on specific cities or store types (Commercial/Downtown).
-  Unit Measures/ measurements: You can experiment by changing the percent of units for products sold, cost and revenue changes.
-  Metrics: You can also change the comparisons not only with the same metrics like old cost and new cost but also with different metrics as well like old cost and new profit, new revenue etc. You can directly select which 2 metrics in the line chart you want. For example you  can see the variations between cost (unchanged) and Revenue (changed) values as per the changes in the values/units from the other sections of the filter.

### 2. KPI Cards (Top Row):
- Displayed current metrics (without any changes): Total Revenue, Total Cost, Total Profit, Quantities Sold, and Profit Percentage.

### 3. Changed Metrics (Middle Section):
- Shows recalculated values for Revenue, Cost, Profit, Quantities Sold, and Profit % after adjustments.
- Includes a comparison with the original values (Change in absolute value and %).
- Indicators (green for increase, red for decrease) emphasize trends.
- Trends of Original and New Values (Bottom):

### 4. Line chart compares the original metrics and updated metrics over time.
Useful for identifying seasonal patterns or fluctuations before and after adjustments.
## Product Overview

![Product Overview](https://github.com/user-attachments/assets/c02cd8f7-c63d-4f65-a767-f97260674fff)



### Purpose of the Report
- Objective: This dashboard provides an in-depth analysis of product performance by category, enabling users to assess revenue, orders, profit, and trends over time.Helps stakeholders identify high-performing and low-performing categories for strategic decision-making.
###  Key Features of the page
### 1. Total Revenue vs. Total Orders vs. Total Profit (Top Left)
Stacked area chart: Compares Total Revenue, Orders, and Profit across product categories (e.g., Art & Crafts, Electronics, Games, Toys, etc.). Visualizes proportional contributions of each category.
### 2. Product Categories Performance (Top Right)
- Category Tabs: Allows users to filter insights by category (e.g., Electronics, Games).
- Date Range Slider:Provides a custom time range to analyze category-specific performance.
- KPIs :
    1) Moving Average: Highlights trends by smoothing data for better forecasting. Taking 30 days as a parameter. 

             Moving AverageX = VAR Last_date = MAX('calendar'[Date])    
             VAR avg_days = 30  
             Var PeriodInVisual=FILTER(
                     ALL(
                        'calendar'[Date]
                     ),
                     AND('calendar'[Date] > Last_date -avg_days,
                     'calendar'[Date]<=Last_date
                     )
                     )
                     VAR Output = CALCULATE(
             AVERAGEX(
                'calendar',
                [Total Revenue]
             ),
             PeriodInVisual
             ) 
             RETURN Output



    2) Total Profit %: Provides a snapshot of profitability by category.
-  Product-Level Breakdown (Middle Right) A table showing: Product Categories: Total Revenue, Contribution %, and Profitability of individual products.
- Highlights how each product contributes to overall revenue and profit.
-    Revenue % selected:  shows the total revenue contribution only among the selected values of product categories.
                    
                    ALLselectedsales = CALCULATE([Total Revenue],ALLSELECTED()) 
                    Revenue % ALLSelected = [Total Revenue]/[ALLselectedsales]
-  Total Revenue and Moving Average (Bottom Left)

### 3.Line chart:
- Shows actual revenue over time compared with the Moving Average for trend analysis.
### 4. Profit % by Product Category (Bottom Right)
- Bar chart: Displays profitability percentage across categories.
-  Quickly identifies the most and least profitable segments.


### 5. Insights Derived
- Top-Performing Categories: Electronics has the highest profitability (44.57%), followed by Games and Art & crafts. Toys have the lowest profit percentage (21.20%).
- Revenue and Profit Trends:Revenue trends align closely with product categories; periods with higher Moving Average indicate consistent performance.
- Actionable Insights: Focus marketing efforts on Electronics and Games to maximize profit. Reassess Toys and Sports & Outdoors to improve profit margins.
### 6. Navigation and User Interactivity
- Dynamic Interactions: Users can switch between categories for granular insights.
- Adjusting the date range slider updates all visualizations, enabling custom period analysis.
- Drill-Down Analysis: Clickable elements (e.g., category tabs) allow for deeper exploration of data.

# Product Performance

![Product perfromance](https://github.com/user-attachments/assets/f3c47478-e719-4394-9d7d-57a263ed1ad3)



### Focus:
- Detailed breakdown of metrics like Month-over-Month (MOM), Quarter-to-Date (QTD), and Year-to-Date (YTD) performance.

###  Key Features of the page

#### 1. Product Metrics by Category and Time (Matrix Visual)
- Purpose: Displays key performance metrics over time, categorized by product and sub-time periods (e.g., months).
- Use Case: This visual allows for detailed analysis of trends, growth, and comparisons at granular (monthly) and aggregate levels.
- Interactivity: Users can expand/collapse categories to focus on specific product groups or months.


- Application: Ideal for operational teams to track and improve product performance.

#### 2. Category/Product Wise Breakdown of Performance (Waterall chart)

### purpose the visual :
 This chart provides clear insights into which product categories drove sales growth and which hindered progress, helping stakeholders make informed decisions for future strategies.

### Key Insights from the Chart for the selected measure (quantities sold)
- Starting Point (2022):

- The total quantities sold in 2022 began at 540K.
#### Major Increases in Sales:

- "Sports & Outdoors" was the most significant driver of increased sales, pushing quantities sold to over 620K.
#### Peak Sales:

- The total quantities sold reached their peak after "Sports & Outdoors," hitting approximately 640K.
#### Major Decreases in Sales:

- "Toys," "Games," and "Electronics" all contributed to a sharp decline in quantities sold.
- "Electronics" had the most substantial negative impact, nearly neutralizing the gains from earlier increases.
#### Net Result (2023):

- By the end of 2023, the total quantities sold returned to a level perfrom above the starting point of 2022, showing a minimal overall increase.


####  Critical visual Interactions: 

 - Products metrics and category and time visual  shows the different measures like
    -  current figures/numbers (for the metrix selected),
    -  previous month’s figure, MOM (month on month),
    -  MOM%, 
    - QTD (quarter to date),
    -  YTD(Year to date)
     for any metrics chosen in the slicer like Totals for revenue, profit,  orders, quantities sold and  cost.

- This visual is using the metric measure like revenue profit etc. as a parameter for the calculations groups which consists of time intelligence functions like QTD,YTD,MOM etc.

- Same measure will be selected for the waterfall chart on the right.

### Common measures used
- Calculation groups are used where in calculation items are defined for  the following measures. 
 - selected measure: 
                      
                      Current Measure = SELECTEDMEASURE().

 - Previous month measure

                Previous Month = CALCULATE(SELECTEDMEASURE(),
                 DATEADD(
                 'calendar'[Date],
                  -1,
                 MONTH
                 )
                 

- MOM (month over month).
       
       MOM = VAR CurrentValue =SELECTEDMEASURE()VAR PrevmonthValue = CALCULATE(
                     SELECTEDMEASURE(),
                     DATEADD(
                        'calendar'[Date],
                        -1,
                        MONTH
                     )
                     )
                     Return
                      CurrentValue - PrevmonthValue
- MOM%.

           MOM % Δ =
           VAR Uparrow=UNICHAR(129129)
           VAR Downarrow = UNICHAR(129131)
           
           VAR CurrentValue = SELECTEDMEASURE()
           VAR Previousvalue = CALCULATE(
                    SELECTEDMEASURE(),
                    DATEADD(
                            'calendar'[Date],-1,MONTH
                    )
                    )
                    VAR DiffValue=
                    CurrentValue - Previousvalue
                    VAR change= DIVIDE(DiffValue,
                    Previousvalue
                    )
                     
                     VAR k = IF(change<0,
                  FORMAT(change,"##.##%") & " " & Downarrow,
                  FORMAT(change,"##.##%") & " " & Uparrow
                  )
                  RETURN
                  k                

- Quarter to date performance:
            
            QTD = CALCULATE(SELECTEDMEASURE(),
                 DATESQTD(
                 'calendar'[Date]
                  )
                  )
                 

- Year to date : 

                YTD = CALCULATE(SELECTEDMEASURE(),
                 DATESYTD(
                 'calendar'[Date]
                  )
)                 
    


# Stores Overview
![Stores Overview](https://github.com/user-attachments/assets/f4981cc5-a635-4c57-b96b-4d14358cfaef)
###  Purpose of the Report
- This dashboard allows users to see the stores performance overview at a glance, showing key figures and lead/lag from the target, top perfroming stores by revenue and map visuals.

### 1. Key Performing Metrics (Left Panel)
- The left panel displays Key Performance Indicators (KPIs) comparing actual performance with targets.
#### a. Monthly Profit vs Target : 
- Actual Monthly Profit: $180K and Target: $198.49 . This KPI highlights how close the stores are to their monthly profit goal, represented through a semi-circle gauge chart. The actual value (blue portion) is short by approximately $18.49K from the target (grey portion).
#### b. Monthly Revenue and Target
•	Actual Monthly Revenue: $658.19K and Target: $724.01K. This metric compares total revenue to the target, again using a gauge chart for visual clarity. While revenue is significant, there is a shortfall of approximately $65.82K.
#### c. Monthly Orders and Target
•	Actual Monthly Orders: 41.83K and Target: 46.01K . This KPI represents order volumes, with a slight shortfall of about 4.18K orders. These metrics help stakeholders quickly identify areas for improvement across profits, revenues,orders
________________________________________
### 2. Top 5 Store Revenue and Profit (Top Right Panel)
This section visualizes the top 5 performing stores in terms of Total Revenue and Total Profit using a clustered column chart.
Store-wise Breakdown:
#### 1.	Maven Toys Ciudad de Mexico 2
- Revenue: $0.55M
- Profit: $0.17M
#### 2.	Maven Toys Guadalajara 3
- Revenue: $0.45M
The blue bars represent Total Revenue, while the orange bars highlight Total Profit.
Insight: Ciudad de Mexico stores lead in both revenue and profits, with notable contributions from Guadalajara and Toluca.
________________________________________
###  3. Top 5 Store City Revenue and Profit (Bottom Panel)
- This section analyzes store performance at a city level, comparing Total Revenue and Total Profit.The horizontal bars visually compare revenue (blue) and profit (orange) across different store locations.




- Insights:
	Downtown stores contribute significantly to both revenue and profit.
- Commercial and Residential areas follow, with relatively lower contributions from Airport stores.
________________________________________
### 4. Map Visualization (Bottom Right Panel)
- The interactive map highlights the geographical distribution of stores. Key locations are categorized using distinct labels: The visual placement on the map allows stakeholders to analyse regional performance trends and identify opportunities for growth.
________________________________________
### Overall Insights
- 	Revenue and Profit Shortfall: Current performance lags slightly behind targets across all KPIs.
- 	Top Stores:
	Maven Toys Ciudad de Mexico 2 leads revenue and profit rankings.
- 	Downtown stores dominate city-level performance.
-  Geographic Performance: Most stores are concentrated in Downtown and Commercial zones, with fewer located at Airports.


## Store performance
![store performance](https://github.com/user-attachments/assets/ab6d95d0-f2ec-4766-b81c-092734a13975)

###  Purpose of the Report
- This provides a high-level overview of the store's performance across different product categories.

### Key visuals :

### Revenue Metric (Matrix Visual)
Purpose:
-  Displays revenue performance for different product categories and subcategories.
Metrics Included:
- Total Revenue: Current total revenue for each product category.
- SPLY Revenue (Same Period Last Year): Revenue for the same period in the previous year for comparison.

                SPLY Revenue = CALCULATE([Total Revenue],SAMEPERIODLASTYEAR('calendar'[Date]))

- Revenue YOY: Year-Over-Year percentage change in revenue.
- Orders YOY: Year-Over-Year change in the number of orders.
Hierarchy:
- Product_Category → Subcategories (e.g., Toys → Sports & Outdoors → Nerf Gun).
Use Case:
- Track performance trends across product categories.
- Compare revenue and order growth against the previous year (YOY).
- Identify subcategories with the highest or lowest growth.
Interactivity:
-  Expand/collapse categories to view revenue details for specific subcategories.

### This Year vs Same Period Last Year (Line Chart)
Purpose:
- Compares Total Revenue across months for the current year and the same period in the previous year.
Metrics Included:
- Total Revenue (Current Year): Shown as an orange line.
- SPLY Revenue (Previous Year): Shown as a black line for comparison.
- X-Axis: Represents the time periods (e.g., months in 2023).
- Y-Axis: Represents revenue values.
Use Case:
 - Analyze revenue trends over months.
 - Identify peaks or drops in revenue compared to the same period last year.
 - Highlight improvements or areas needing attention.

### Yearly Performance Analysis (Decomposition Tree Visual)
- Purpose: Provides a hierarchical breakdown of yearly performance metrics.
Metrics Included:
- Yearly Revenue: $6.96M (Total revenue for the year).
- Yearly Orders: 408.42K (Total orders for the year).
- Yearly Revenue Change: 24% increase compared to the previous year.
- Yearly Order Change: 111,362 additional orders.
Hierarchy:
- Store_City 
- → Store_Name (e.g., Ciudad de Mexico → Maven Toys Ciudad...).
- Total Cost is displayed at each node.
Use Case:
- Drill down into city and store-level performance.
- Identify top-performing cities and stores in terms of revenue and cost.
- Analyze contributions to overall yearly performance.

#### Slicers Interactvity : You can among the metrics like  totals for  
- profit  
- revenue 
- orders 
- quantity sold and cost (currently selected)

### Page level filter pane 
- you can filter the options out of the 8 given fields for your analysis.
![Filter pane ](https://github.com/user-attachments/assets/ea38aadc-7ccf-4112-9b18-f452b4861e1f)

### Fitler counter
Filter counter not only shows the count of filters applied to the fields in the filter pane but also shows what values are selected (upto 3).

![filter counter](https://github.com/user-attachments/assets/d019e74b-9bd8-41c1-adf4-98ab68923b1d)



## Inventory analysis
![Inventory analysis](https://github.com/user-attachments/assets/59cdfd9c-ad5a-4d18-a2f4-d87942e3bf1e)

###  Purpose of the Report


- This dashboard provides insights into the store's inventory levels and product demand.
###  Key Features

#### Stock on hand by Product Category:
-  A pie chart showing the stock on hand for each product category (Art & Crafts, Toys, Games, Sports & Outdoors, Electronics)
-  Below that matrix which  includes a detailed breakdown of the stock on hand and quantities sold for each product category, grouped by store location.

#### Least stock on hand for Products and Quantities sold:
- Displays the products with the least stock on hand and the corresponding quantities sold, including Classic Dominoes, Uno Card Game, Mini Basketball Hoop, Monopoly, and Jenga.
#### Quantities Sold and Stock on hand by Product Category:
- A stacked bar chart showing the quantities sold and stock on hand for each product category.


##  Project Summary: Maven Toys Strategic Analysis 
 #### Revenue 

-  Total Revenue trended upward, boasting a remarkable 28.33% increase from January 2022 to July 2023.
-  The real turning point occurred in July 2022 when Total Revenue started a significant upswing, soaring by an impressive 31.64% (equivalent to $516,119) within four Quarters. 
#### Steepest Incline 📊
-  During the steepest incline between July 2022 and July 2023, Total Revenue witnessed a substantial jump, escalating from $1,631,301 to a peak of $2,147,420.
####  Regional Disparities 🌐
- Maven Toys Ciudad de Mexico 2 emerged as the revenue champion, raking in $554,553. This figure was 48.67% higher than the lowest revenue-generating store, Maven Toys Monterrey 2, which recorded $372,999.
####  Profit and Revenue Correlation 🔄
-  Total Revenue and Total Profit showcase a positive correlation, illustrating the symbiotic relationship between revenue generation and profitability.
####  Revenue Contribution 🌍
-  Maven Toys Ciudad de Mexico 2 played a significant role, contributing a substantial 24.96% to the overall Total Revenue.
#### Profit Variation Across Store Cities 💼
-  Sum of Profit displayed variation across all 5 Store City entities, ranging from $235,047 to $465,558.
####  Product Performance 🏆
- Lego Bricks stole the spotlight with the highest Sum of Revenue, reaching an impressive $2,388,882.63. Meanwhile, Color buds claimed the crown for the highest Sum of Profit, standing at a remarkable $834,944.
