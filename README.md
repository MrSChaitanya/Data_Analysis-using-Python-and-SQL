# Retail Orders Data Analysis Project

An end-to-end data engineering and analytics pipeline demonstrating the complete lifecycle of retail data—from programmatic extraction and transformation to relational database loading and business intelligence querying.

## 🚀 Project Overview
This project automates the workflow of handling retail transaction data. By integrating Python for ETL (Extract, Transform, Load) and SQL for analytical depth, it provides a scalable approach to uncovering product performance and regional sales trends.

### 🛠 Tech Stack
*   **Language:** Python 3.x
*   **Libraries:** Pandas, SQLAlchemy, MySQL-Connector, Kaggle API
*   **Database:** MySQL Server
*   **Tools:** Jupyter Notebook, VS Code, MySQL Workbench

---

## 🏗 Workflow

### 1. Data Extraction
*   **Source:** Programmatically fetched the "Retail Orders" dataset via the **Kaggle API**.
*   **Processing:** Extracted ZIP archives and loaded data into a Pandas DataFrame.

### 2. Cleaning & Transformation (Python/Pandas)
*   **Data Integrity:** Identified and handled null values (e.g., 'Not Available', 'Unknown').
*   **Standardization:** Converted column headers to `snake_case` for SQL compatibility.
*   **Feature Engineering:** 
    *   Calculated `discount`, `sale_price`, and `profit`.
    *   Converted `order_date` to a proper `datetime` format.
*   **Optimization:** Dropped redundant columns to streamline the final database schema.

### 3. Data Loading
*   Utilized **SQLAlchemy** for a high-performance database connection.
*   Automated the loading process into **MySQL** using the `to_sql` method.

### 4. Data Analysis (SQL)
Solved critical business questions using advanced SQL (CTEs and Window Functions):
*   **Top 10** highest revenue-generating products.
*   **Top 5** selling products in each region.
*   **MoM Growth:** Comparison of 2022 vs. 2023 sales.
*   **Seasonality:** Peak sales months for every product category.
*   **Profitability:** Sub-categories with the highest profit growth YoY.

---

## ⚡ How to Run

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com
    ```
2.  **Configure Kaggle API:**
    Place your `kaggle.json` in your local `.kaggle` directory.
3.  **Update Credentials:**
    Modify the `create_engine` string in the Python script with your MySQL username and password.
4.  **Execute the Pipeline:**
    Run all cells in the Jupyter Notebook to process and load the data.
5.  **Run Analysis:**
    Open `analysis.sql` in MySQL Workbench to execute the business queries.

---

## 💡 Key Insights
*   **Schema Consistency:** Standardizing column names in Python significantly reduces errors during the SQL analysis phase.
*   **Performance:** Using SQLAlchemy's batch loading is considerably faster than standard row-by-row insertion.
*   **Logic:** Leveraging **CTEs** and **Window Functions** makes complex "Top N" and growth analysis readable and efficient.
