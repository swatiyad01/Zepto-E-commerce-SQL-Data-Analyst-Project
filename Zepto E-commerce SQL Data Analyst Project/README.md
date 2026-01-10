# 🛒 Zepto Inventory Analysis — SQL Project

## 📌 Project Overview

This project is a hands-on **SQL data analysis project** built to practice and demonstrate core data analyst skills using a real-world e-commerce inventory dataset inspired by Zepto.

The focus of this project is to simulate how a data analyst works with raw inventory data — starting from table creation and data exploration, moving through data cleaning, and finally answering business-oriented questions using SQL.

---

## 🎯 Objectives

The main objectives of this project are to:

- Understand the structure of an e-commerce inventory dataset  
- Perform **Exploratory Data Analysis (EDA)** using SQL  
- Clean and standardize pricing and inventory data  
- Use SQL to derive **business insights** related to pricing, discounts, stock availability, revenue, and inventory weight  

---

## 📁 Dataset Information

- **Source:** Kaggle  
  https://www.kaggle.com/datasets/palvinder2006/zepto-inventory-dataset

- The dataset represents a realistic e-commerce inventory system based on product listings.

### Key Notes About the Data

- Each row represents a **SKU (Stock Keeping Unit)**  
- Duplicate product names exist due to:
  - Different pack sizes  
  - Different weights  
  - Different discounts or pricing  
- This mirrors how real-world catalog data is structured  

---

## 🧾 Table Schema

The dataset was stored in a PostgreSQL table named `zepto`.

```sql
CREATE TABLE zepto (
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);
🔍 Data Exploration
The following exploratory steps were performed:

Counted total number of records

Viewed sample rows to understand data structure

Checked for NULL values in critical columns

Identified unique product categories

Compared in-stock vs out-of-stock products

Identified products with multiple SKUs

🧹 Data Cleaning
To improve data quality and consistency:

Identified records with zero MRP or zero selling price

Removed invalid pricing records

Converted prices from paise to rupees

Ensured numeric consistency for revenue and value calculations

📊 Business Analysis & Insights
The following analytical questions were answered using SQL:

Top 10 products offering the highest discount percentage

High-MRP products that are currently out of stock

Estimated category-wise revenue

Expensive products with minimal discounts

Categories with the highest average discount percentage

Price-per-gram analysis to identify best-value products

Weight-based product segmentation (Low / Medium / Bulk)

Total inventory weight per product category

These queries simulate real business decision-making scenarios such as pricing strategy, inventory planning, and product value comparison.

🛠️ Tools & Skills Used
SQL (PostgreSQL)

Data Cleaning & Validation

Aggregate Functions (SUM, AVG, COUNT)

GROUP BY, HAVING, ORDER BY

CASE statements

Business-driven query logic

📂 How to Run the Project
Clone the repository

bash
Copy code
git clone <your-repository-link>
Create a PostgreSQL database

Run the SQL file to create the table

Import the dataset CSV (UTF-8 encoded)

Execute the queries step-by-step for analysis

📌 Key Learning Outcomes
Translating business questions into SQL logic

Cleaning messy, real-world data

Writing readable and structured SQL queries

Understanding inventory and pricing analysis in e-commerce
