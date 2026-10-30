 # E-Commerce Sales: ETL and Data Analytics

## Project Overview

This project focuses on building an ETL pipeline and preparing e-commerce data for analytical reporting using the Brazilian Olist e-commerce dataset.

The main objective is to extract, clean, transform, and organize order, product, customer, and payment data into structured analytical tables.

The project also demonstrates data quality validation, data modeling, and SQL-based analysis to support business insights into e-commerce sales and operations.

## Business Context

E-commerce datasets contain information at different levels of detail:

- An order can contain multiple products.
- An order can have multiple payment records.
- Customer and product information is stored in separate datasets.

Combining these tables without considering their granularity can multiply rows and lead to incorrect financial aggregations.

This project addresses this issue by maintaining separate tables and applying appropriate aggregation methods.

## Dataset

The project uses the Brazilian Olist public e-commerce dataset.

The following source files are used:

- `orders.csv`
- `order_items.csv`
- `order_payments.csv`
- `customers.csv`
- `products.csv`

The analytical scope is limited to orders with the `delivered` status.

## Tools and Technologies

- **Python** 
- **Pandas** 
- **NumPy** 
- **SQLite**
- **SQL** 
- **Google Colab** 

## ETL Process

### 1. Data Extraction

Load the source CSV files into Pandas DataFrames.

### 2. Data Cleaning and Transformation

- Filter delivered orders.
- Convert date columns to datetime format.
- Handle missing values.
- Clean product category information.
- Convert numerical columns to appropriate data types.
- Calculate delivery duration and order approval time.
- Prepare separate analytical tables.

### 3. Data Modeling

The project maintains separate tables with clearly defined levels of detail:

| Table | Level of Detail |
|---|---|
| Orders | One row per delivered order |
| OrderItems | One row per order item |
| Payments | One row per payment record |
| Customers | One row per customer ID |
| Products | One row per product ID |

Additional analytical datasets are prepared:

- `Orders_Analysis` — order-level information with aggregated payment and item metrics.
- `Items_Analysis` — item-level information enriched with product and order attributes.

### 4. Data Quality Validation

Validation checks include:

- Uniqueness of primary keys.
- Uniqueness of the composite key (`order_id`, `order_item_id`) in OrderItems.
- Referential consistency between analytical tables.
- Reconciliation of payment totals.
- Validation of aggregation results.

Payment reconciliation confirms that the total payment value in the Payments table matches the total after aggregation to the order level.

**Delivered payment total: 15,422,461.77**

The validation also identified one delivered order without a corresponding payment record. This order is retained in the Orders and OrderItems tables without an artificial payment value.

## SQL Analysis

The transformed data is stored in an SQLite database.

The project includes SQL queries for:

- Total payment value for delivered orders.
- Monthly payment trends.
- Item price and freight value by product category.
- Payment value by customer state.
- Distribution of payment methods.

## Output Files

The ETL pipeline exports the following datasets:

- `Orders.csv`
- `OrderItems.csv`
- `Payments.csv`
- `Customers.csv`
- `Products.csv`
- `Orders_Analysis.csv`
- `Items_Analysis.csv`
- `olist_analytics.db`

## Key Learning Outcomes

- Designing an ETL workflow with Python and Pandas.
- Understanding table granularity and relationships.
- Identifying and preventing row multiplication in joins.
- Validating financial aggregations through reconciliation.
- Preparing structured datasets for business intelligence reporting.
- Using SQL to analyze e-commerce sales and payment data.

## Next Step

The prepared tables can be loaded into Power BI to build a relational data model and develop an interactive e-commerce analytics dashboard.
