# Coffee Shop Sales Analysis Power BI Dashboard

## Objective:
The primary goal of this project is to create a dynamic and insightful dashboard that visualizes key performance metrics related to coffee shop sales. 
Through the dashboard, users can monitor trends, compare performance metrics across months, and identify high-performing products and store locations. 
The project aims to empower stakeholders with actionable insights to optimize sales strategies and improve business outcomes.

## Data Source:
The data used for this project is derived from transactional records of coffee shop sales. 
This includes product categories, store locations, transaction details, quantities, and pricing.

## Key Features:

### 1. **Date Table Creation**:
A dedicated date table is created using DAX to facilitate time-based calculations and analysis. The table includes columns for:
- Month
- Month Number
- Month Year
- Day Name
- Week Number
- Day Number
- Weekday vs. Weekend Classification

### 2. **DAX Measures**:
The dashboard incorporates a variety of DAX measures to analyze the data effectively:
- **Current Month Orders, Sales, and Quantity**: Calculated using dynamic time intelligence functions to focus on the selected month.
- **MoM (Month-over-Month) Difference in Orders, Sales, and Quantity**: These measures show the percentage and actual difference compared to the previous month,allowing for easy trend identification.
- **Daily Average Sales**: Shows the average sales per day across the selected time period.
- **Color-Coded Sales Performance**: Compares total sales against daily average sales and classifies them as "Above AVG" or "Below AVG" based on performance.
  
### 3. **Dynamic Labels**:
Custom labels are added to display product information, store locations, and categories in a user-friendly format. 
The labels automatically update based on the selected filters to show key details such as:
- Product Type and Category
- Store Location Performance
- Sales Volume in Thousands ($0.00k format)
  
### 4. **Footnote with Tooltip**:
A footnote with a hover-over feature is included, allowing users to access more detailed information with ease.

### 5. **Comparative Analysis**:
Month-over-Month comparison measures for orders, quantity, and sales provide insights into how sales metrics fluctuate over time. 
An up/down arrow (🔼🔽) indicator is used to signify positive or negative trends.

## Value Proposition:
The Coffee Shop Sales Power BI dashboard enables managers and stakeholders to:
- Monitor monthly sales trends and identify top-performing products or store locations.
- Compare sales performance across different time periods (e.g., current vs. previous month).
- Make data-driven decisions regarding product offerings, pricing strategies, and resource allocation.
- Easily track the impact of weekends versus weekdays on sales performance.

## Key DAX Measures:
- **Total Sales** = SUM(Transactions[Sales])
- **Total Orders** = DISTINCTCOUNT(Transactions[transaction_id])
- **Total Quantity** = SUM(Transactions[transaction_qty])
- **Current Month Orders** = TOTALMTD([Total Orders], 'Date Table'[Date])
- **Current Month Sales** = TOTALMTD([Total Sales], 'Date Table'[Date])
- **Previous Month Sales** = CALCULATE([Total Sales], DATEADD('Date Table'[Date], -1, MONTH))
  
…and many more custom measures to enhance the analysis.

## Conclusion:
This Power BI dashboard offers a complete solution for analyzing coffee shop sales data, providing users with critical insights to optimize their operations. 
By incorporating powerful visualizations, dynamic labels, and interactive filters, it helps users make well-informed, data-driven decisions. 
The project stands as a valuable tool for sales performance monitoring and improvement.
