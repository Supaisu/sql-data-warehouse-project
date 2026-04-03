# Data Warehouse and Analytics Project

A modern data warehouse built with SQL Server, demonstrating end-to-end data engineering — from raw data ingestion through to business-ready analytics. Built using medallion architecture (bronze, silver, gold layers) with ETL pipelines, star schema modelling, and analytical reporting.

---

## Data Architecture

![Data Architecture](documents/Data%20Warehouse%20Architecture.drawio.png)

**Bronze Layer** — Stores raw data as-is from source systems. Data is ingested from CSV files (ERP and CRM) into SQL Server.

**Silver Layer** — Data cleansing, standardisation, and normalisation. Handles quality issues, resolves inconsistencies, and prepares data for downstream modelling.

**Gold Layer** — Business-ready data modelled into a star schema. Optimised for analytical queries and reporting, with fact and dimension tables designed for performance.

---

## Key Concepts Demonstrated

- **Medallion architecture** - Structured data flow across bronze, silver, and gold layers
- **Star schema design** - Fact and dimension tables optimised for analytical workloads
- **ETL pipeline development** - Extract, transform, and load processes from source to warehouse
- **Data quality engineering** - Cleansing, deduplication, and standardisation of raw data
- **Multi-source integration** - Combining ERP and CRM systems into a unified data model
- **Analytical reporting** — SQL-based insights into customer behaviour, product performance, and sales trends

---

## Project Overview

| Area | Detail |
|------|--------|
| **Data Sources** | ERP and CRM systems (provided as CSV files) |
| **Database** | SQL Server |
| **Architecture** | Medallion (Bronze → Silver → Gold) |
| **Data Model** | Star schema with fact and dimension tables |
| **Focus** | Latest dataset only (no historisation) |

---

## Repository Structure

```
sql-data-warehouse-project/
│
├── datasets/              # Raw datasets (ERP and CRM data)
│
├── documents/             # Architecture diagrams and documentation
│   ├── Data Flow Diagram.drawio.png
│   ├── Data Mart (Star Schema).drawio.png
│   ├── Data Warehouse Architecture.drawio.png
│   ├── Integration Model.drawio.png
│   └── data_catalog.md
│
├── scripts/               # SQL scripts for ETL and transformations
│   ├── bronze/            # Raw data extraction and loading
│   ├── silver/            # Cleaning and transformation
│   └── gold/              # Analytical models and star schema
│
├── tests/                 # Data quality tests and validation
│
├── README.md
└── LICENSE
```

---

## Analytics and Reporting

The gold layer supports SQL-based analytics delivering insights into:

- **Customer behaviour** - Segmentation, purchasing patterns, and retention analysis
- **Product performance** - Revenue by product, category trends, and margin analysis
- **Sales trends** - Period-over-period comparisons, seasonal patterns, and growth metrics

These insights are designed to empower stakeholders with actionable business metrics for strategic decision-making.

---

## Architecture Diagrams

| Diagram | Description |
|---------|-------------|
| [Data Warehouse Architecture](documents/Data%20Warehouse%20Architecture.drawio.png) | End-to-end system architecture |
| [Data Flow Diagram](documents/Data%20Flow%20Diagram.drawio.png) | Data movement across layers |
| [Star Schema](documents/Data%20Mart%20(Star%20Schema).drawio.png) | Gold layer dimensional model |
| [Integration Model](documents/Integration%20Model.drawio.png) | Source system integration design |
| [Data Catalog](documents/data_catalog.md) | Field descriptions and metadata |

---

## About Me

Data engineering postgraduate with a background in Accounting and Finance. Currently completing an MSc in Computer Science with Data Analytics, building end-to-end data solutions that bridge business understanding with technical execution.

- [LinkedIn]([https://www.linkedin.com/in/umaircadir/])
- [GitHub](https://github.com/Supaisu)

---

## License

This project is licensed under the MIT License. Free to use, modify, and share with proper attribution.
