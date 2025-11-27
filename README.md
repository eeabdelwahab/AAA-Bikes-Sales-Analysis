AAA Bikes – Sales Analysis (2016–2018)

This project presents a complete end-to-end analytics workflow for AAA Bikes, covering data extraction, cleaning, transformation, modeling, DAX calculations, and dashboard creation.
The analysis explores over 3 million rows of sales data across three years (2016–2018) to uncover performance trends and support strategic decision-making.

Project Objective

The goal of this project was to analyze three years of sales performance for AAA Bikes, focusing on:

Cleaning and standardizing raw MS Access data

Building a structured star-schema data model

Creating interactive Power BI dashboards

Applying statistical techniques to detect trends and relationships

Generating insights and recommendations to guide business decisions

Dataset

Source: MS Access database

Rows: More than 3 million

Time Period: 2016, 2017, 2018

Main Tables: Sales, Products, Categories, Cities, Dates

The dataset contained transactional sales records combined with product, category, city, and calendar lookup tables.

Data Preparation (Power Query)

Key cleaning and transformation steps included:

Removing duplicate records

Standardizing column names across tables

Fixing incorrect data types (dates and numeric fields)

Merging dimension lookup tables (Products, Categories, Cities, Dates)

Creating calculated columns such as AvgPrice and SalesTotal

Handling missing or inconsistent values

Exporting the cleaned dataset for modeling in Power Pivot

This stage ensured data consistency and improved overall model performance.

Data Modeling (Power Pivot)

A star-schema model was designed to optimize reporting and DAX performance.

Fact Table

FactSales

Quantity

Price

Discount

SalesTotal

Dimension Tables

DimProduct

DimCategory

DimCity

DimDate (full date hierarchy enabled)

Relationships

Many-to-One relationships from the FactSales table to each dimension table

Ensured proper filter flow and high-performance aggregations

DAX Measures
Core Metrics
TotalQuantity = SUM(FactSales[Quantity])
SalesTotal    = SUM(FactSales[SalesTotal])
AvgPrice      = DIVIDE([SalesTotal], [TotalQuantity])

Yearly Sales
Sales 2016 = CALCULATE([SalesTotal], YEAR(DimDate[Date]) = 2016)
Sales 2017 = CALCULATE([SalesTotal], YEAR(DimDate[Date]) = 2017)
Sales 2018 = CALCULATE([SalesTotal], YEAR(DimDate[Date]) = 2018)

Statistical Measures
Sales Mean      = AVERAGE(FactSales[SalesTotal])
Sales Median    = MEDIAN(FactSales[SalesTotal])
Sales Variance  = VAR(FactSales[SalesTotal])
Sales StdDev    = STDEV.P(FactSales[SalesTotal])

Correlation (Sales vs Quantity)

Using a manual statistical DAX implementation:

Sales_Quantity_Correlation = 
"Correlation calculated using manual statistical DAX implementation"

Key Insights

Annual sales remained stable at approximately £63M per year.

Total quantity sold stayed consistent at around 2 million units annually.

The Bikes category contributed over 77% of total revenue.

Cargo Bike was the highest-selling product across all years.

Cairo, Alexandria, and Giza led all cities in total sales volume.

Sales and quantity showed a moderate positive correlation, suggesting volume-based promotional opportunities.

These insights reveal strong product performance patterns and clear regional sales dominance.

Recommendations

Increase inventory and marketing for top-performing products such as Cargo Bikes and Mountain Bikes.

Expand stock availability in high-demand cities including Cairo and Alexandria.

Reassess pricing for lower-performing Components category items.

Utilize seasonal promotions and bundles to increase average order value.

Apply targeted volume-based discounts to boost sales without reducing overall profitability.

Tools Used

MS Access

Microsoft Excel

Power Query

Power Pivot

Power BI

DAX

Repository Structure

AAA-Bikes-Sales-Analysis
│
├── RawData/
├── CleanedData/
├── PowerQuery/
├── PowerPivot/
├── PowerBI/
└── README.md

Project Status

This project is fully completed as an end-to-end data analytics workflow, from raw data extraction to modeling, dashboard creation, and insights generation.
