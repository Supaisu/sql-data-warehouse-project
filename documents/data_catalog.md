# Data Catalog for Gold Layer

## Overview
The Gold Layer contains business-ready data modelled into a **star schema** for reporting and analytics. It is derived from the cleaned and standardised Silver Layer tables.

---

## 1. gold.dim_customers

**Description:** Dimension table containing customer details, combining data from CRM and ERP sources.

| Column Name       | Data Type     | Description                                      | Source                          |
|--------------------|---------------|--------------------------------------------------|---------------------------------|
| customer_key       | INT           | Surrogate key for the customer dimension         | Generated                      |
| customer_id        | INT           | Business key from the CRM system                 | silver.crm_cust_info.cst_id     |
| customer_number    | NVARCHAR(50)  | Alternate customer identifier                    | silver.crm_cust_info.cst_key    |
| first_name         | NVARCHAR(50)  | Customer's first name                            | silver.crm_cust_info.cst_firstname |
| last_name          | NVARCHAR(50)  | Customer's last name                             | silver.crm_cust_info.cst_lastname  |
| marital_status     | NVARCHAR(50)  | Marital status (Single, Married, n/a)            | silver.crm_cust_info.cst_marital_status |
| gender             | NVARCHAR(50)  | Gender (Male, Female, n/a)                       | silver.crm_cust_info.cst_gndr / silver.erp_cust_az12.gen |
| birthdate          | DATE          | Customer's date of birth                         | silver.erp_cust_az12.bdate      |
| country            | NVARCHAR(50)  | Customer's country of residence                  | silver.erp_loc_a101.cntry       |
| create_date        | DATE          | Date the customer record was created             | silver.crm_cust_info.cst_create_date |

---

## 2. gold.dim_products

**Description:** Dimension table containing product details and category information.

| Column Name        | Data Type     | Description                                      | Source                          |
|---------------------|---------------|--------------------------------------------------|---------------------------------|
| product_key         | INT           | Surrogate key for the product dimension          | Generated                      |
| product_id          | INT           | Business key from the CRM system                 | silver.crm_prd_info.prd_id      |
| product_number      | NVARCHAR(50)  | Product identifier code                          | silver.crm_prd_info.prd_key     |
| product_name        | NVARCHAR(50)  | Name of the product                              | silver.crm_prd_info.prd_nm      |
| category_id         | NVARCHAR(50)  | Identifier for the product category              | silver.crm_prd_info.cat_id      |
| category            | NVARCHAR(50)  | Product category name                            | silver.erp_px_cat_g1v2.cat      |
| subcategory         | NVARCHAR(50)  | Product subcategory name                         | silver.erp_px_cat_g1v2.subcat   |
| maintenance         | NVARCHAR(50)  | Product maintenance classification               | silver.erp_px_cat_g1v2.maintenance |
| product_cost        | DECIMAL       | Cost of the product                              | silver.crm_prd_info.prd_cost    |
| product_line        | NVARCHAR(50)  | Product line (Mountain, Road, Touring, etc.)     | silver.crm_prd_info.prd_line    |
| start_date          | DATE          | Product availability start date                  | silver.crm_prd_info.prd_start_dt |
| end_date            | DATE          | Product availability end date (NULL if current)  | silver.crm_prd_info.prd_end_dt  |

---

## 3. gold.fact_sales

**Description:** Fact table containing sales transactions at the line-item level.

| Column Name        | Data Type     | Description                                      | Source                          |
|---------------------|---------------|--------------------------------------------------|---------------------------------|
| order_number        | NVARCHAR(50)  | Unique order identifier                          | silver.crm_sales_details.sls_ord_num |
| product_key         | INT           | Foreign key to gold.dim_products                 | silver.crm_sales_details.sls_prd_key |
| customer_key        | INT           | Foreign key to gold.dim_customers                | silver.crm_sales_details.sls_cust_id |
| order_date          | DATE          | Date the order was placed                        | silver.crm_sales_details.sls_order_dt |
| shipping_date       | DATE          | Date the order was shipped                       | silver.crm_sales_details.sls_ship_dt |
| due_date            | DATE          | Date the order is due                            | silver.crm_sales_details.sls_due_dt |
| sales_amount        | DECIMAL       | Total sales amount                               | silver.crm_sales_details.sls_sales |
| quantity            | INT           | Number of units sold                             | silver.crm_sales_details.sls_quality |
| price               | DECIMAL       | Unit price of the product                        | silver.crm_sales_details.sls_price |
