# Data Warehouse and Analytics Project

A modern data warehouse built with SQL Server, demonstrating end-to-end data engineering, from raw data ingestion through to business-ready analytics. Built using medallion architecture (bronze, silver, gold layers) with ETL pipelines, star schema modelling, and analytical reporting.

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
- **Analytical reporting** - SQL-based insights into customer behaviour, product performance, and sales trends

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

## How to Run

1. Install [SQL Server Express](https://www.microsoft.com/en-gb/sql-server/sql-server-downloads) and [SSMS](https://learn.microsoft.com/en-us/ssms/download-sql-server-management-studio-ssms).
2. Clone this repo and run `scripts/init_database.sql` to create the `DataWarehouse` database and the `bronze`, `silver` and `gold` schemas. **Warning:** this drops any existing `DataWarehouse` database.
3. Run `scripts/bronze/ddl_bronze.SQL`, then update the CSV file paths in `scripts/bronze/proc_load_bronze.sql` to point at your local `datasets/` folder and run it. Load the data with `EXEC bronze.load_bronze;`
4. Run `scripts/silver/ddl_silver.sql` and `scripts/silver/proc_load_silver.sql`, then `EXEC silver.load_silver;`
5. Run `scripts/gold/ddl_gold.sql` to create the star schema views.
6. Validate the results with the scripts in `tests/`.

---

## Acknowledgements

This project was built by following the [Data With Baraa](https://github.com/DataWithBaraa/sql-data-warehouse-project) SQL Data Warehouse course, which provided the dataset and project structure.

---

## About Me

Data analyst with a BSc in Accounting and Finance (Royal Holloway) and an MSc in Computer Science with Data Analytics (University of York). I build end-to-end data solutions that bridge business understanding with technical execution.

- [LinkedIn](https://www.linkedin.com/in/umaircadir/)
- [GitHub](https://github.com/Supaisu)

---

## License

This project is licensed under the [MIT License](LICENSE).
