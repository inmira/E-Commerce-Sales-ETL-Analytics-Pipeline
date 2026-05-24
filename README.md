# E-Commerce Sales ETL & Analytics Pipeline

## Project Overview

The goal of this project was to build an end-to-end ETL and analytics pipeline for e-commerce sales data using Python, SQL, and SQLite.

The project focused on:
- data extraction and integration from multiple datasets,
- data cleaning and validation,
- feature engineering and analytical dataset creation,
- loading transformed data into a relational database,
- performing SQL-based business analysis,
- creating visualizations to support reporting and decision-making.

The final analytical dataset was used to analyze revenue trends, customer geography, product categories, and transactional behavior.

---

## Dataset

The project is based on the Brazilian E-Commerce Public Dataset by Olist.

Main datasets used:
- orders
- customers
- order items
- payments
- products

---

## Technologies Used

- Python
- pandas
- NumPy
- SQL
- SQLite
- SQLAlchemy
- matplotlib
- Jupyter Notebook / Google Colab

---

## ETL Process

### 1. Extract

Raw CSV files were loaded into Python using pandas.

### 2. Transform

The transformation stage included:
- checking missing values,
- checking duplicate records,
- validating data types,
- converting date columns,
- handling missing product information,
- validating monetary fields,
- creating new analytical features.

Created features included:
- delivery time in days,
- approval time in hours,
- purchase month,
- total item value.

### 3. Load

The final analytical dataset was loaded into a SQLite database as the `sales_data` table.

The SQL load was validated by comparing row counts between the final DataFrame and the database table.

---

## Data Quality Checks

The project included several data validation steps:
- missing values analysis,
- duplicate checks,
- data type validation,
- review of delivery time outliers,
- review of delayed approvals,
- validation of payment values,
- validation of product attributes.

Missing delivery-related values were preserved where they reflected valid business states such as canceled, shipped, or undelivered orders.

---

## SQL Analysis

SQL queries were used to analyze:
- total revenue,
- monthly revenue trends,
- top product categories,
- revenue by customer state.

Example result:

- Total revenue: **19,776,160.44**
- Highest revenue region: **São Paulo (SP)**
- Top product category: **cama_mesa_banho**

---

## Key Insights

- Revenue increased strongly throughout 2017 and remained high in 2018.
- Revenue was concentrated in major Brazilian states, especially São Paulo.
- Home, health, electronics, and lifestyle-related categories generated the highest revenue.
- The final dataset showed realistic right-skewed transaction values typical for e-commerce data.

---

 
