Retail Orders Data Analysis Project (Python + MySQL)
Project Overview
This is an end-to-end data engineering and analytics project designed to demonstrate the pipeline from data extraction to insightful analysis. The project involves downloading a dataset from Kaggle via its API, cleaning and transforming the data using Python (Pandas), loading the processed data into a MySQL database, and performing complex SQL queries to solve business problems.

Tech Stack
Language: Python 3.x

Libraries: pandas, sqlalchemy, mysql-connector-python, kaggle

Database: MySQL Server

Tooling: Jupyter Notebook / VS Code, MySQL Workbench

Workflow
1. Data Extraction
Used the Kaggle API to programmatically download the "Retail Orders" dataset.

Extracted the data from zip files and loaded it into a Pandas DataFrame.

2. Data Cleaning & Transformation
Handling Nulls: Identified specific strings (e.g., 'Not Available', 'Unknown') and treated them as NaN.

Standardization: Converted column names to lower-case and replaced spaces with underscores for better SQL compatibility.

Feature Engineering: * Calculated discount using list_price and discount_percent.

Derived sale_price and profit.

Converted order_date from object/string to a proper datetime format.

Optimization: Dropped redundant columns (list_price, cost_price, discount_percent) to streamline the final schema.

3. Data Loading
Utilized mysql-connector-python to ensure the target database (df_orders_db) exists.

Used SQLAlchemy to establish a high-performance connection.

Loaded the transformed data into MySQL using the to_sql method with the append parameter.

4. Data Analysis (SQL)
Performed business analysis by writing complex SQL queries to answer the following:

Top 10 highest revenue-generating products.

Top 5 highest selling products in each region.

Month-over-month sales growth comparison between 2022 and 2023.

Peak sales month for every product category.

Sub-category with the highest profit growth in 2023 compared to 2022.

How to Run
Clone the Repository:

Bash
git clone https://github.com/your-username/retail-orders-analysis.git
Configure Kaggle API:

Place your kaggle.json in ~/.kaggle/ (Linux/Mac) or C:\Users\<User>\.kaggle\ (Windows).

Update Database Credentials:

Modify the create_engine string in the script with your local MySQL username and password.

Execute the Notebook:

Run all cells in the Jupyter Notebook to process and load the data.

Run Analysis:

Open MySQL Workbench and run the queries provided in the analysis.sql file.

Key Insights
Data Quality: Standardizing column names and types in Python significantly reduces errors during SQL analysis.

Performance: Using SQLAlchemy's to_sql is significantly faster than standard row-by-row insertion.

SQL Logic: Leveraging Common Table Expressions (CTEs) and Window Functions makes complex "Top N" and "Growth" analysis readable and efficient.