# Electroniccs Store Sales Performance Dashboard - Power BI (Basic)
Welcome to the **Electronics Store Power BI Sales Dashboard Project**💡

This basic Power BI dashboard creation project is done on the fictional data generated based on real world electronic store sales details for a fiscal year.

## 📌 Project Overview
Create a single page Power BI dashboard for an Electronics Store reportinng all the essential metrics regarding their sales for the year 2025.  

### Data Source
Two tables, two fact tables about sales from the past two years and one dimension table about the products
- Fact Tables [`fact_sales`](docs.fact_sales.csv) and [`fact_sales_2024`](docs/fact_sales_2024.csv)
- Dimension Table [`dim_products`](docs/dim_products.csv)

### Data Model
The data model follows a Star Schema pattern with one to many relation from the products to sales tables

### Data Visuals
- KPI Cards for important metrics
- Charts for indicating Rvenue over time
- Breakdowns of Orders and Revenue by Products

---

## 📊 Dashboard

---

## 📋 Project Outline
The source data for this project is stored as two csv files, two fact tables for the sales details of the year 2025 and 2024 and one dimension table for the product datails. The `product_id` column links all the tables in a **Star Schema** pattern where the fact tables are at the centre and dimension tables are places surround them. The project follows the standard four step process  
- **Power Query** for data cleaning and data standardization
- **DAX Calculations** for calcualted columns and additional tables, mainly a decidated `measures` and `date` table
- **Data Modelling** creates the relations between all the above tables, here the model follows a Star Schema pattern
- **Data Visualization** brings all the imformation from various tables into different charts and KPI cards for insights

### Power Query ⚙️

### DAX Calculations 📐

### Data Modelling 🔗

### Data Visualization 📊










