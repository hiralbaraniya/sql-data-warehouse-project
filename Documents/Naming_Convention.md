# 📘 Naming Conventions

This document outlines the naming conventions used for schemas, tables, views, columns, and other objects in the data warehouse.

---

## 📑 Table of Contents
- General Principles  
- Table Naming Conventions  
  - Bronze Rules  
  - Silver Rules  
  - Gold Rules  
- Column Naming Conventions  
  - Surrogate Keys  
  - Technical Columns  
- Stored Procedures  

---

# 📌 General Principles

- 🧾 Naming Style: Use `snake_case`, with lowercase letters and underscores (_) to separate words  
- 🌐 Language: Use English for all object names  
- 🚫 Avoid Reserved Words: Do not use SQL reserved keywords as object names  

---

# 🗂️ Table Naming Conventions

## 🥉 Bronze Rules

- Table names must start with the source system name  
- Must retain the original source table names (no renaming)

### Format:
<sourcesystem>_<entity>

- `<sourcesystem>`: Name of source system (e.g., crm, erp)  
- `<entity>`: Exact table name from source system  

### Example:
crm_customer_info → Customer information from CRM system  

---

## 🥈 Silver Rules

- Same naming convention as Bronze layer  
- Retain source system structure and naming  

### Format:
<sourcesystem>_<entity>

### Example:
erp_orders → Orders data from ERP system  

---

## 🥇 Gold Rules

- Use business-aligned, meaningful names  
- Must start with a category prefix  

### Format:
<category>_<entity>

### Category Patterns:

| Pattern   | Meaning              | Example               |
|----------|----------------------|-----------------------|
| dim_     | Dimension table      | dim_customers         |
| fact_    | Fact table           | fact_sales            |
| report_  | Reporting table      | report_sales_monthly  |

### Examples:
- dim_customers → Customer dimension table  
- fact_sales → Sales fact table  

---

# 🏷️ Column Naming Conventions

## 🔑 Surrogate Keys

- Primary keys in dimension tables must use `_key` suffix  

### Format:
<table_name>_key

### Example:
customer_key → Surrogate key in dim_customers  

---

## ⚙️ Technical Columns

- All system-generated columns must start with `dwh_` prefix  

### Format:
dwh_<column_name>

### Example:
dwh_load_date → Record load timestamp  

---

# ⚙️ Stored Procedure Naming Conventions

- Stored procedures must follow:

load_<layer>

### Layers:
- bronze → Raw ingestion layer  
- silver → Cleaned & transformed layer  
- gold → Business-ready layer  

### Examples:
- load_bronze → Load raw data  
- load_silver → Load cleaned data  
- load_gold → Load curated analytics data  
