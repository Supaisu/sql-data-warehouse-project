# Data Warehouse and Analytics Project

Welcome to the Data Warehouse and Analytics Project repository!
This project demonstrates a comprehensive data warehousing and analytics solutiom, from building a data warehouse to generating actionable insights. Designed as a portfolio project, it highlights industry best practices in data engineering and analytics.

---

## Data Architecture
<img width="1091" height="631" alt="image" src="https://github.com/user-attachments/assets/8da5c1f1-9050-46ee-8fbf-ffbf0ef35c34" />

1. Bronze Layer: Stores raw data as-is from the source systems. Data is ingested from CSV Files into SQL Server Database.
2. Silver Layer: This layer includes data cleansing, standardization, and normalization processes to prepare data for analysis.
3. Gold Layer: Houses business-ready data modeled into a star schema required for reporting and analytics.

---
   
## Project Overview
This project involves:

1. Data Architecture: Designing a Modern Data Warehouse Using Medallion Architecture Bronze, Silver, and Gold layers.
2. ETL Pipelines: Extracting, transforming, and loading data from source systems into the warehouse.
3. Data Modeling: Developing fact and dimension tables optimized for analytical queries.
4. Analytics & Reporting: Creating SQL-based reports and dashboards for actionable insights.

---

## Project Requirements

Building the Data Warehouse

Objective

Develop a modern data warehouse using SQL server to consolidate sales data, enabling analytical reporting and informed decision-making. 

Specifications
- Data Sources: Import data from two source systems (ERP and CRM) provided as CSV files.
- Data Quality: Cleanse and resolve data quality issues prior to analysis
- Integration: Combine both sources into a single, user-friendly data model designed for analytical queries
- Scope: Focus on the latest dataset only; historisation of data is not required.
- Documentation: Provide clear documentation of the data model to support both business stakeholders and analytics teams.

---

Repository Structure
## Repository Structure
```
sql-data-warehouse-project/
│
├── datasets/                              # Raw datasets used for the project (ERP and CRM data)
│
├── documents/                             # Project documentation and architecture details
│   ├── Data Flow Diagram.drawio.png       # Data flow diagram
│   ├── Data Mart (Star Schema).drawio.png # Star schema model
│   ├── Data Warehouse Architecture.drawio.png  # Project architecture
│   ├── Integration Model.drawio.png       # Integration model
│   └── data_catalog.md                    # Catalog of datasets, including field descriptions and metadata
│
├── scripts/                               # SQL scripts for ETL and transformations
│   ├── bronze/                            # Scripts for extracting and loading raw data
│   ├── silver/                            # Scripts for cleaning and transforming data
│   └── gold/                              # Scripts for creating analytical models
│
├── tests/                                 # Test scripts and quality files
│
├── README.md                              # Project overview and instructions
└── LICENSE                                # License information for the repository
```

## BI: Analytics and Reporting (Data Analytics)

Objective
Develop SQL-based analytics to deliver detailed insights into:
- Customer Behaviour
- Product Performance
- Sales Trends

These insights empower stakeholders with key business metrics, enabling strategic decision-making.

---

## License

This project is licensed under the MIT License. You are free to use, modify, and share this project with proper attribution.

## About Me

I am an aspiring data professional on a mission to become a valuable asset to a firm by bringing the skills and fresh perspective to deliver actionable results!

(This is also my first ever project, as part of the SQL mastery course that I am completing)
