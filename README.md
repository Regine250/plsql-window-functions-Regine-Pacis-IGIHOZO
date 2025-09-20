# SQL-PL
# PL/SQL Window Functions — [Lastname] [Firstname]
Repository: plsql-window-functions-[lastname]-[firstname]

## 1. Problem Definition (Business Scenario)
**Business context:** A mid-sized clothing company in Rwanda specializing in locally made apparel seeks to enhance its inventory management and sales forecasting processes.  
**Data challenge:** The company struggles with excess inventory and stock shortages due to inaccurate demand prediction. Historical sales data is fragmented and not effectively utilized, leading to lower stock levels that impact revenue.
**Expected outcome**: The analysis is expected to provide insights into sales trends and customer preferences, enabling the company to optimize inventory levels and enhance demand forecasting accuracy. This will lead to reduced carrying costs and increased revenue through better product availability.

## 2. Success Criteria (5 measurable goals)
1. Top 5 products per region/quarter → `RANK()` and `ROW_NUMBER()`.  
2. Running monthly sales totals → `SUM() OVER (ORDER BY ...)`.  
3. Month-over-month growth → `LAG()` / `LEAD()`.  
4. Customer quartiles → `NTILE(4)`.  
5. 3-month moving averages → `AVG() OVER (ORDER BY ... RANGE/ROWS ...)`.

---

## 3. Schema & ER Diagram
**Tables**
1. Customers Table
Purpose	Customer info
Key Columns	customer_id (PK), name, region
Example Row	1001, John Doe, Kigali
2. Products Table
Purpose	Product catalog
Key Columns	product_id (PK), name, category
Example Row	2001, Coffee Beans, Beverages
3. Transactions Table
Purpose	Sales records
Key Columns	transaction_id (PK), customer_id (FK), product_id (FK), sale_date, amount
Example Row	3001, 1001, 2001, 2024-01-15, 25000

ER Diagram

An ER diagram can visually represent these relationships, showing how customers, products, and transactions are interconnected:
Customers:customer_id is the primary key.
Products:product_id is the primary key.
Transactions:customer_id and product_id are foreign keys referencing the customers and products tables, respectively.
Customers
Customer_id (PK)	name	region

Products
Product_id (PK)	name	category

Transactions
Transaction_id (PK)	Customer_id (FK)	Product_id (FK)	sale_date	amount

