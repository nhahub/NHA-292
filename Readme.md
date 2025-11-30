Alex Agency Analytics Dashboard
 Project Overview

This project presents a comprehensive B2B Analytics Dashboard designed to analyze and monitor the sales and distribution performance of a wholesale agency.

The dashboard provides decision-makers with actionable insights into:

Sales performance and trends

Customer distribution

Employee productivity

Product performance

Shipping efficiency across territories

 Data Model

The dataset is structured using a Snowflake Schema Model.

The core structure includes:

Fact Table

Orders (FactOrder)

Dimension Tables

Customers

Products

Employees

Territories

Shippers

Dates

This design supports:

Optimized performance

Reduced data redundancy

Enhanced scalability for analytical queries

 Dashboard Highlights
  Sales Performance

Total Sales

Average Sales per Employee

Sales Trend Analysis

 Employee Analytics

Top Performer Identification

Contribution Percentage

Employee Productivity Metrics

 Customers & Markets

Number of Customers by Region

Country Market Size Distribution

 Products

Top-Selling Products

Category-level performance

Product contribution analysis

 Shipping & Operations

Average Delivery Time

Delayed Orders

Shipping Performance by Company

 Key Measures (DAX Examples)
Total Sales
Total Sales = SUM(FactOrder[TotalOrderValue])

Sales Per Employee
Sales Per Employee =
SUMX(
    VALUES(DimEmployees[EmployeeID]),
    CALCULATE(SUM(FactOrder[TotalOrderValue]))
)

Average Sales Per Employee
Avg Sales Per Employee =
AVERAGEX(
    VALUES(DimEmployees[EmployeeID]),
    [Sales Per Employee]
)

Top Performer Name
Top Performer =
MAXX(
    TOPN(1, VALUES(DimEmployees[EmployeeName]), [Sales Per Employee]),
    DimEmployees[EmployeeName]
)

Delivery Delay (Days)
Avg Delivery Delay =
AVERAGEX(
    FILTER(
        FactOrder,
        FactOrder[shippedDate] > FactOrder[requiredDate]
    ),
    DATEDIFF(FactOrder[requiredDate], FactOrder[shippedDate], DAY)
)

 Business Value

This dashboard enables stakeholders to:

Track performance against targets

Identify operational issues in logistics

Evaluate employee efficiency

Optimize product distribution

Improve customer coverage strategy

 Tools & Technologies

Power BI

DAX

Power Query

Data Modeling Star Schema)

Git & GitHub

 

📁 Files Included

✅ Dataset (.xlsx)

✅ Power BI File (Dashboard)

✅ Documentation (PDF)

✅ PowerPoint Presentation

✅ README.md



 Future Improvements

Forecasting with DAX / Python

Customer segmentation

Real-time data refresh

Advanced KPI Cards

 Team Members

This project was developed as a team project by:

Ahmed Mamdouh

Omar Mohammed

Saeed Mohammed

Jasser Ashraf

Mohammed Salah

Youssef Marzouk

⭐ If you find this project helpful...

Give it a star on GitHub ⭐