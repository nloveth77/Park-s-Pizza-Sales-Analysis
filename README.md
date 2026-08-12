# Park-s-Pizza-Sales-Analysis



This project successfully transformed one year of raw transactional data into a flexible Star Schema data model and a two-page interactive dashboard in Power BI. The analysis revealed a healthy core business with $817,860.05 in total revenue, but identified clear operational bottlenecks and menu inefficiencies.

The major dataset used for this analysis is the Pizza Sales Data for Park’s Pizza. The key methodology used are a CSV File, SQL, and the Power BI tool was the major tool used to address and answer all of the project questions. The dashboards are interactive for easy and quick comprehension of the audience.




Project Objective


The major aim for this analysis is to analyze the operations and sales report of Park’s Pizza for the year 2015, and this analysis further shades more analysis on the of March 2015 to help the stakeholders of this project make data-driven decisions for the business in the next coming year.





<img width="1364" height="758" alt="Park&#39;s Pizza Dasboard" src="https://github.com/user-attachments/assets/b079e053-f990-48bc-b9e5-20c7344b5f90" />





Story of Data:


The dataset was derived from a consolidated Kaggle file and it has a total number of 48620 rows and 12 columns. While convenient for quick review, this structure is inefficient for detailed BI analysis. The first step was to use PgAdmin4 to apply a crucial data warehousing concept: Normalization.
This Normalization separates data into smaller, much more manageable, and distinct tables (Dimensions and Facts), eliminating data redundancy and ensuring data integrity.
With the use of CREATE TABLE AS SELECT DISTINCT queries, i was able to decompose the wide source table (pizza_sales) into four distinct tables to form a Star Schema:


Table Name
Type
Core Content
Primary Key

### Data Warehouse Structure

| Table Name | Type | Core Content | Primary Key |
|---|---|---|---|
| **pizza_id** | Fact (The Event) | Records quantity and the calculated (`line_item_revenue`). | `pizza_id` |
| **orders** | Dimension (Time) | Records the unique (`order_id`, date, and time) of the transaction. | `order_id` |
| **pizzas** | Dimension (Product SKU) | Records the (`pizza_id`, size, and `unit_price`). | `pizza_id` |



Analytical Querying For KPIs
Before uploading my dataset into Power BI for visualization, I had to write and execute several SQL codes to validate my key metrics and data integrity as a foundation for my PowerBI visualization.
The major KPIS includes:

KPI Title
SQL Code
Result


### Key Performance Indicators

| KPI | Calculation | Result |
|---|---|---:|
| **Total Revenue** | `SUM(total_price)` | **$817,860.05** |
| **Average Order Value** | `SUM(total_price) / COUNT(DISTINCT order_id)` | **38.307** |
| **Total Orders** | `COUNT(DISTINCT order_id)` | **21,350** |
| **Total Pizza Sold** | `SUM(quantity)` from `pizza_sold` | **50K** |
| **Average Pizza per Order** | `COUNT(DISTINCT order_id) / COUNT(DISTINCT order_date)` | **59** |



Data Modeling and Visualization Using Power BI
I had to connect the four normalized to Power BI, and by this action the immediate creation of a Star Schema model was activated, where the order_details Fact table sits in the center, linked to all Dimension tables.

 Key Relationships Between SQL and Power BI
The PgAdmin4 database (SQL) and Power BI work in aligned perfectly:
SQL's Role (Data Transformation): I used SQL to break down the analysis, did some extractions, minor cleanings, and Normalization. SQL is optimized for defining relationships and aggregating data directly from the source.
Power BI's Role (Data Modeling, DAX expression and Visualization): Power BI being a visualization tool, helped me define the model relationships, create dynamic/new DAX Measures (like comparing revenue Year-over-Year), and build the user-friendly visuals that deliver the final narrative.
Appending New Columns with Power Query Editor: so, i used the Power Query editor to append new columns like Days of the Week (DOW) column and transform details in order_date column and pizza_size column. 
Structural Report & Visualization
I imputed a two-page structured report focusing on the dynamics in client's objectives and preference, whilst being conscious of the maximum 6-chart limit per page:
Page 1:  An Overview of Executive Sales & Performance;
In this page I recorded this important point: "What Pizza is actually selling and where exactly is the huge revenue coming from?"
Visual Title
Focus
Result/Observation


### Business Performance Insights

| Visual Title | Focus | Result/Observation |
|---|---|---|
| **Monthly Revenue Trend** | Seasonality | Sales are relatively stable, with peak sales in **May and July** (ca. $71K–$72K) and obvious declines in **Sep/Oct** (ca. $64K). |
| **Top 5 Bestsellers** | Menu Profitability | The **Thai Chicken Pizza** and **BBQ Chicken Pizza** generate the highest revenue for the business. |
| **Bottom 5 Performers** | Menu Inefficiency | The **Brie Carre Pizza** generates the lowest revenue ($11.6K) and is an inventory liability. |
| **Revenue by Category** | Product Mix | Categories are well-balanced, with **Classic** leading the revenue contribution. |
| **Quantity by Size** | Customer Preference | The **Large (L) size** is overwhelmingly dominant (38% of quantity). XL/XXL are marginal. |



Page 2: Operational Efficiency & Demand Analysis
In this second page I recorded this important point: "When is the busiest time of the business, and the need for proper staffing?"
Visual Title
Focus
Result/Observation


### Operational Efficiency & Demand Analysis

| Visual Title | Focus | Result/Observation |
|---|---|---|
| **Orders by Day of Week** | Daily Traffic | **Friday** is the clear peak day for orders; **Sunday** is the slowest day. |
| **Quantity by Day of Week** | Labor Allocation | **Friday** sells the most pizzas (**8,242 units**), requiring maximum preparation and staffing. |
| **Revenue by Day of Week** | Daily Financials | **Sunday** revenue is the lowest, providing a safe day for scheduled deep cleaning or maintenance. |





<img width="1368" height="776" alt="Time-Based Dashboard Park&#39;s Pizza" src="https://github.com/user-attachments/assets/2847f12a-d9a9-4564-b2ab-9701a96c0ee7" />





 Data Preprocessing 

Data cleaning
I got the dataset downloaded from kaggle.com and uploaded it into my Excel Workbook for further  analysis. Basic checks and observations were made in the dataset to ensure it was clean and consistent for analysis. Checks for duplicates, empty cells, inconsistencies in letter casing and spacing were made and corrected.  To retain the raw dataset for another use, I had to duplicate the dataset and use one for the analysis.


Industry Context and Stakeholders

The project is for a Pizza Store with Revenue Means. The data is telling a story around sales of Pizza and the operations at Park’s Pizza.
The  major stakeholders for this project are the Chief Executives and Marketing Team.
To this industry, generating more revenue while satisfying their customers is exactly what success means to this industry.



Post-Analysis Observation





<img width="1336" height="752" alt="Obsevation Board Park&#39;s Pizza" src="https://github.com/user-attachments/assets/5a9ffe2b-d4bf-41dc-9d60-c4bb0daf1b44" />





Overall Business Performance

Observation
The business generated $817.9K in total revenue from 21K orders.
The average order value is $38.31 with customers buying 2.32 pizzas per order.
This indicates customers typically purchase 2 pizzas per transaction, suggesting potential to increase basket size


Top Performing Pizzas

Observation
The Thai Chicken and Barbecue Chicken pizzas generate the highest revenue ($43K each).
These products clearly drive a large portion of total pizza revenue.
Demand for chicken-based pizzas appears strong.


Low Performing Pizzas

Observation
Pizzas such as Spinach, Mediterranean, and Brie-based options generate the lowest revenue.
These products may not align with the majority of customer taste preferences.
Pizza Size Demand
Observation
• Large pizzas dominate sales (19K units)**.
• Medium and small sizes follow but with noticeably lower demand.
• Extra Large and XX-Large pizzas have almost no sales**, suggesting limited market demand.


Revenue by Pizza Category

Observation
Classic pizzas generate the highest revenue ($220K)**.
• Supreme and Chicken categories follow closely.
• Veggie pizzas generate the **lowest revenue among the main categories**.


Revenue by Pizza Category

Observation
•Classic pizzas generate the highest revenue ($220K)
• Supreme and Chicken categories follow closely.
• Veggie pizzas generate the **lowest revenue among the main categories**.


Revenue by Day of the Week

Observation
Friday generates the highest revenue ($136K).
Saturday and Thursday also perform strongly.
Sunday records the lowest revenue ($99K).
Revenue clearly increases toward the end of the week.


Quantity Sold by Day of the Week

Observation
Friday has the highest pizza sales (8.2K).
Saturday and Thursday follow closely (7.5K each).
Sunday has the lowest quantity sold (6.0K).
Demand strongly aligns with weekend dining behavior.


Total Orders by Day of the Week (Treemap)

Observation
Friday has the highest number of orders (4K).
Most other days record around 3K orders.
Order distribution shows consistent weekday demand but strong weekend spikes.


Pizza Sales by Category

Observation
Classic pizzas lead sales (15K).
Veggie and Supreme categories follow (12K each).
Chicken pizzas generate slightly lower sales (11K).




Post-Analysis Recommendation:




<img width="1361" height="771" alt="Recommendation Board Park&#39;s Pizza" src="https://github.com/user-attachments/assets/cecf40a1-f103-4d37-b5f3-446cab6ddadd" />





Overall Business Performance


• Introduce **bundle promotions (e.g., buy 2 pizzas + drink deals)** to increase the number of pizzas per order.

• Implement **upselling strategies at checkout** such as sides, beverages, or desserts.

• Create **loyalty programs or discounts for orders above $40** to increase average order value.
Top Performing Pizzas

• Promote these pizzas as **“Best Sellers” on the menu and marketing channels**.

• Ensure **consistent ingredient supply** to prevent stock shortages.

• Consider introducing **new variations of chicken pizzas** to capitalize on customer preferences.
Low Performing Pizzas

• Evaluate **pricing or recipe improvements** to make them more appealing.

• Test **limited-time promotions or discounts** to stimulate demand.

• If performance remains weak, consider **removing them from the menu and replacing them with new options**.
Pizza Size Demand

• Focus marketing on **large pizzas**, especially for **family or group meal deals**.

• Consider **revising pricing or promotions for XL sizes** to increase demand.

• Evaluate whether **XXL pizzas should remain on the menu**.
Revenue by Pizza Category

• Expand the **classic pizza menu with new variations**.

• Use classic pizzas as **anchor products in promotions and bundles**.

• Develop marketing campaigns targeting **veggie lovers** to grow that segment.
Revenue by Pizza Category

• Introduce **seasonal promotions during low-performing months**.

• Run **targeted marketing campaigns and discounts** during slower periods.

• Align **inventory and staffing levels with peak demand months**.


Revenue by Day of the Week
Increase staffing and inventory preparation for Fridays and Saturdays to handle peak demand.

Launch Sunday promotional deals such as “Sunday Family Pizza Specials” to boost sales.

Use Thursday promotions (e.g., “Pre-Weekend Deals”) to capture early weekend demand.

Quantity Sold by Day of the Week

Focus marketing campaigns and advertising around weekends.

Introduce weekend bundle deals to maximize revenue during high-traffic periods.

Encourage weekday orders with lunch or midweek discounts.

Total Orders by Day of the week

Optimize delivery logistics and staff scheduling for Friday evenings.

Implement fast-track ordering systems during peak hours to reduce delays.

Introduce weekday office lunch promotions to increase weekday orders.

Pizza Sales by Category

Expand the classic pizza menu, as it drives the most volume.

Create combo offers featuring classic pizzas.

Develop marketing campaigns targeting veggie lovers to grow that category.



Conclusion:
From the overall analysis, Park’s Pizza shows strong performance driven mainly by large size pizzas, chicken/classic varieties, and high weekend demand. To further sustain growth, the business needs to strengthen its best-selling products, improve low-performing items, and use targeted promotions and bundles to increase order value and weekday sales.


Reference: 
Reference: https://topmate.io/dat  (Youtube)
