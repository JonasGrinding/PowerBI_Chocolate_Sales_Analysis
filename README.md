# Sales and Profit Analysis Dashboard

📊 This project presents a comprehensive dashboard for analyzing sales performance, shipments, costs, and profitability metrics across various dimensions. It offers insights into key metrics such as Total Sales, Profit Margins, and Box Shipments while tracking month-over-month (MoM) changes and comparing them to target benchmarks.

🔍 Key DAX calculations, visualizations, and measures used in the dashboard can be explored here.

## Background

This project was initiated to streamline the process of monitoring and analyzing sales and profit metrics across different categories. The dashboard is designed to provide both high-level overviews and detailed breakdowns of sales performance, offering insights that are critical for strategic decision-making.

### Key Questions Addressed:

1. What are the current total sales, and how do they compare to previous months?
2. How many boxes and shipments were processed?
3. What are the total costs, and how do they impact profit margins?
4. Which salespersons are driving the most profit, and what is their profit percentage?
5. How are the metrics performing on a month-over-month (MoM) and year-over-year (YoY) basis?

## Tools & Technologies

For this project, the following tools and technologies were utilized:

**Power BI:** For building interactive and dynamic dashboards, visualizing sales, shipments, and profitability data.
**DAX (Data Analysis Expressions):** The primary language used to create calculated columns, measures, and custom tables within Power BI.
**Git & GitHub:** Used for version control, collaboration, and sharing the project with others.

## Measures Created

The following are some key DAX measures that were created to drive the dashboard's functionality:

**MoM Boxes Change %**:
```dax
MoM Boxes Change % =
    var this_month = [Total Boxes]
    var prev_month = CALCULATE([Total Boxes], PREVIOUSMONTH('calendar'[Date]))
RETURN
    DIVIDE(this_month-prev_month, prev_month)
```

**Latest MoM Sales Change %**:
```dax
Latest MoM Sales Change % =
    var ld = [Latest Date]
    var this_month_sales = [Total Sales Latest Month]
    var prev_month_sales = CALCULATE([Total Sales], 'calendar'[Start of Month] = EDATE(ld, -1))
RETURN
    DIVIDE(this_month_sales-prev_month_sales, prev_month_sales)
```

*Profit Target Indicator**:
```dax
Profit Target Indicator =
    IF([Profit %]>[Profit Target], 2, IF([Profit %]>0.9[Profit Target], 1, 0))
```

**Total Sales (prev month)**:
```dax
Total Sales (prev month) =
    CALCULATE([Total Sales], PREVIOUSMONTH('calendar'[Date]))
```

## The Dashboard

### Overview

The dashboard provides a snapshot of key performance indicators (KPIs) including total sales, total boxes shipped, total shipments, total costs, and total profit. It also tracks profit percentage, LBS (pounds) count, and LBS percentage, enabling a comprehensive understanding of performance.

![image](https://github.com/user-attachments/assets/2840acea-f3bc-4e1a-abac-662335be58de)


### Detailed Analysis

Boxes by Start of Month: This line chart shows the trend of boxes shipped from March 2023 to January 2024, helping to identify peaks and troughs in shipment activity.
Shipment Analysis: A bar chart visualizing the distribution of shipments over time, offering insights into shipment volumes and trends.
!

### Salesperson Performance

The dashboard includes a detailed breakdown of sales by salesperson, showing sales figures, profit, profit percentage, and LBS percentage. This allows for the identification of top performers and areas where improvements may be needed.

## Key Insights

### 1. Sales Performance

The dashboard indicates that total sales for the period reached $34M. However, there was a 10.8% decline in sales on a month-over-month basis, signaling potential issues or seasonal trends that may need addressing.

### 2. Profitability

Total profit stood at $21M, with a profit margin of 60.3%. This high-profit margin is indicative of efficient cost management and strong sales performance.

### 3. Shipment and Boxes Trends

The total number of boxes shipped was 2M, and the total number of shipments was 6K. These metrics, along with the shipment analysis, provide a clear picture of operational performance.

# Conclusion
## What I Learned
Through this project, I gained deeper expertise in creating dynamic and interactive dashboards using Power BI and DAX. I honed my ability to:

- **Design Comprehensive Dashboards:** I developed a dashboard that integrates multiple key metrics into a cohesive view, enhancing my ability to present data in a way that is both visually engaging and analytically useful.
-  **Master DAX Functions:** Crafting complex measures such as month-over-month (MoM) changes and custom profit indicators sharpened my skills in DAX, allowing me to perform advanced calculations and create more meaningful insights.
- **Interpret Business Performance:** By analyzing the sales, shipments, and profit data, I learned how to effectively track business performance, identify trends, and spot potential issues that need to be addressed.
- **Strategic Decision-Making:** This project reinforced the importance of data-driven decision-making. The insights gleaned from the dashboard are critical for making informed strategic choices, such as adjusting sales strategies, optimizing costs, and setting realistic profit targets.

#### Key Insights
Several key insights emerged from the analysis:

1. **Sales Trends:** The total sales for the period amounted to $34M, but with a 10.8% decline in MoM sales, it became apparent that there are fluctuations that need to be further investigated, possibly due to seasonality or external market conditions.

2. **Profit Margins:** With a total profit of $21M and a profit margin of 60.3%, the business is maintaining healthy profitability. However, the varying profit percentages among salespersons suggest opportunities for training or strategy adjustments to enhance performance across the board.

3. **Operational Efficiency:** The analysis of boxes shipped and total shipments provided insights into the operational efficiency of the business. Consistent shipment volumes with fluctuating sales indicate potential bottlenecks or inefficiencies in the supply chain that could be optimized.

4. **Salesperson Performance:** The breakdown of sales by salesperson highlighted significant differences in performance, offering an opportunity to recognize top performers and implement targeted improvements for those lagging.

### Insights for Future Improvement
- **Focus on MoM Analysis:** The importance of tracking month-over-month changes was reinforced, as it helps in understanding the immediate impact of business decisions and market conditions. This can be expanded in future projects to include more detailed trend analysis.

- **Profit Optimization:** While the overall profit margin is strong, there is room to optimize costs and further improve profitability. Future analyses could dive deeper into cost structures and their impact on the bottom line.

- **Employee Training and Incentives:** The varying profit percentages among salespersons suggest that focused training and perhaps revised incentive structures could align performance more closely with business goals.

### Closing Thoughts
This project was a significant learning experience that not only enhanced my technical skills in Power BI and DAX but also deepened my understanding of how to interpret and act on complex business data. The insights gained are invaluable for driving business success, ensuring that every decision is backed by data-driven analysis. Moving forward, these skills and insights will serve as a strong foundation for tackling more advanced data analytics projects and making strategic decisions that propel business growth.
