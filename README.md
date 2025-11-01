# **SQL Data Warehouse Project**

This project demonstrates the **end-to-end design and implementation** of a modern **Data Warehouse** using **Microsoft SQL Server**.  
It follows a clean multi-layer architecture — **Bronze, Silver, and Gold** — to manage data ingestion, transformation, and analytics efficiently.

---
## **Overview**

> The goal of this project is to **design and build a complete SQL Data Warehouse** that simulates how data engineers organize, clean, and analyze business data for insights.It uses **multiple source systems (CRM, ERP)** and applies **best practices in naming, schema design, data quality, and transformation**.

**Key Deliverables:**
- A well-defined **data pipeline** from raw ingestion to analytical reporting.  
- Layered schemas (**Bronze → Silver → Gold**) with structured stored procedures.  
- Business-ready analytical views and metrics for decision-making.

---

## **Architecture**

The project follows a **multi-schema Lakehouse-style architecture** inside SQL Server.
![Project Architecture](.assets/SQL (3000 x 1800 px).png)
Each layer is isolated for clarity, traceability, and reusability.

---

## **Data Layers**

### **1. Bronze Layer**
- Stores **raw data** ingested directly from CSV files.
- No transformations applied — maintains original structure for lineage.
- Loaded via stored procedure: `bronze.load_bronze`.

### **2. Silver Layer**
- Cleans, validates, and standardizes data from Bronze.
- Handles duplicates, nulls, and inconsistent formats.
- Includes metadata columns (`dwh_create_date`).
- Loaded via: `silver.load_silver`.

### **3. Gold Layer**
- Contains **analytical models**: fact and dimension tables.
- Implements **Star Schema**:
  - `dim_customers`
  - `dim_products`
  - `fact_sales`
- Includes business reports like `report_customers`.

---

## **ETL / ELT Process**

| Step | Layer | Action | Description |
|------|--------|---------|-------------|
| 1 | Bronze | Ingest | Bulk insert from CRM & ERP CSV files |
| 2 | Silver | Transform | Clean, validate, and normalize data |
| 3 | Gold | Load | Join and enrich data into business views |

---

## **Quality Checks** *

The project applies **data quality validation** at each stage

- Duplicate and NULL detection
- Trim and format checks
- Date consistency checks
- Referential integrity between fact and dimensions
- Validation of business rules (e.g., `sales = quantity * price`)

---

## **Exploratory & Analytical SQL**

Includes over **10 categories** of analytical SQL scripts
- **Measures Exploration** – Total Sales, Orders, Customers
- **Magnitude Analysis** – Revenue by Category, Country, Gender
- **Ranking Analysis** – Top/Bottom Products and Customers
- **Trend Analysis** – Monthly/Yearly Sales Growth
- **Segmentation** – Customer Groups (VIP, Regular, New)
- **Cumulative & Performance Analysis**
- **Comprehensive Customer Reports**

---

## **Project Highlights**

✅ Fully automated ETL using stored procedures  
✅ Clean naming conventions and schema isolation  
✅ Quality-first data validation  
✅ Reusable and readable SQL code  
✅ Analytical layer ready for Power BI / Tableau visualization  




