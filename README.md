# Electronics Store Sales Performance Dashboard - Power BI (Basic)
Welcome to the **Electronics Store Power BI Sales Dashboard Project**💡

This basic Power BI dashboard creation project is done on the fictional data generated based on real world electronic store sales details for a fiscal year.

## 📌 Project Overview
Create a single page Power BI dashboard for an Electronics Store reportinng all the essential metrics regarding their sales for the year 2025.  
The dashboard should be modern and minimalist following all the UI/UX principles for easy user experience

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
After connecting to the source data the first step is to clean the tables for any inconsistancies that may have occured during the data creation process  
This include
- Checking the all the columns that contains a dimensional values for unwanted spaces and remove them using Trim function
- Checking for null values in the all the columns and replacing neccessary columns with appropriate values
- Ensuring that the date column contains only date values and no null values and converting the date column into the 'Date' data type
- Ensuring that all the columns are marked with the correct data type, sales and price as 'Currency' for example

### DAX Calculations 📐
The DAX calculations for this dataset mainly consists of creating two dedicated columns, one for calculated metrics called 'measures and one for date
- **Measures Table**  
  The `measures` table containns all the neccessary calcultions derived from the existing data inside the tables. This include
  - `total_revenue` - Sum of all the sales
  - `total_orders` - Sum of all the distinct orders
  - `total_quantity` - Sum of all the order quantity
  - `total_products` - Count of all the products
  - `sales_last_year` - Sum of all the sales last year
  - `revenue_growth` - Increase in revenue compared to the previous year
  - `average_revenue_per_customer` - Total revenue divided by total customers
  - `average_order_value` - Total revenue divided by total orders
The formulas written as a single query in [`measures_dax_formulas`](scripts/measures_dax_formulas)

- **Date Table**  
 The `date_table` is generated with all the dates from the sales fiscal year. This table can be used as a expanaded version of the already existing `order_date` column in the fact tabl, it contains additional information regarding the **Quarter**, **Month** numerical and name and **Day** from the order date.
The [`date_dax_formula`](scripts/date_dax_formula) contains the formula for creating date table

### Data Modelling 🔗
The Data Model for this dataset follow a **Star Schema** pattern. After the DAX calculation there are a total of five tables in the model.
- Fact tables - `fact_sales` and `fact_sales_2024`
- Dimension tables - `dim_products` and `date_table`
- Measures table - `measures`

The `fact_sales` and `fact_sales_2024` can be linked with the `dim_prodcuts` and `date_table` using the `product_id` and `order_date` columns respectively in a one to many relation from the fact to dimension  
The `measures` table is a standalone table as it does not contain any common column with the any other table

![data_model](docs/data_model.png)

### Data Visualization 📊
The Data Visualization follws a modern minimalist approach for creating all the KPIs and Charts. A clean interfacre following UI/UX design principles is followed to makes the dashboard interaction easy and smooth

- The KPI Cards

The end result is a modern and minimilist dashboard contianing all the insights neccessary for the business to analyse the sales performance for the fiscal year










