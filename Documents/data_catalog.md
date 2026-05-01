# 📘 Data Catalog for Gold Layer

---

# 📌 Overview

The **Gold Layer** represents the business-level data model designed to support analytical reporting and business intelligence use cases.

It consists of:
- 📊 Dimension Tables
- 📈 Fact Tables

These tables are optimized for analytics, reporting, and decision-making.

---

# 👥 1. gold.dim_customers

## 🎯 Purpose
Stores customer details enriched with demographic and geographic information.

---

## 📋 Columns

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| customer_key | INT | Surrogate key uniquely identifying each customer record in the dimension table |
| customer_id | INT | Unique numerical identifier assigned to each customer |
| customer_number | NVARCHAR(50) | Alphanumeric identifier used for tracking and referencing customers |
| first_name | NVARCHAR(50) | Customer's first name |
| last_name | NVARCHAR(50) | Customer's last name or family name |
| country | NVARCHAR(50) | Country of residence for the customer |
| marital_status | NVARCHAR(50) | Marital status of the customer (e.g., Married, Single) |
| gender | NVARCHAR(50) | Gender of the customer (e.g., Male, Female, n/a) |
| birthdate | DATE | Customer date of birth in YYYY-MM-DD format |
| create_date | DATE | Date when the customer record was created in the system |

---

# 📦 2. gold.dim_products

## 🎯 Purpose
Provides information about products and their business attributes.

---

## 📋 Columns

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| product_key | INT | Surrogate key uniquely identifying each product record |
| product_id | INT | Unique identifier assigned to the product |
| product_number | NVARCHAR(50) | Alphanumeric code representing the product |
| product_name | NVARCHAR(50) | Descriptive product name including type, color, and size |
| category_id | NVARCHAR(50) | Unique identifier for the product category |
| category | NVARCHAR(50) | High-level product classification (e.g., Bikes, Components) |
| subcategory | NVARCHAR(50) | Detailed product classification |
| maintenance_required | NVARCHAR(50) | Indicates whether maintenance is required |
| cost | INT | Product cost or base price |
| product_line | NVARCHAR(50) | Product line or series (e.g., Road, Mountain) |
| start_date | DATE | Date when the product became available |

---

# 💰 3. gold.fact_sales

## 🎯 Purpose
Stores transactional sales data for analytical and reporting purposes.

---

## 📋 Columns

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| order_number | NVARCHAR(50) | Unique identifier for each sales order |
| product_key | INT | Surrogate key linking to the product dimension |
| customer_key | INT | Surrogate key linking to the customer dimension |
| order_date | DATE | Date when the order was placed |
| shipping_date | DATE | Date when the order was shipped |
| due_date | DATE | Payment due date for the order |
| sales_amount | INT | Total sales value for the line item |
| quantity | INT | Quantity of products ordered |
| price | INT | Price per unit of the product |

---

# 🏁 Summary

The Gold Layer provides a clean and business-friendly data model for:

- 📊 Reporting
- 📈 Dashboarding
- 📉 Trend Analysis
- 👥 Customer Analytics
- 📦 Product Performance Analysis
- 💰 Sales Analysis
