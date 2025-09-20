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


---

## 4. Queries
All SQL scripts are in `/scripts/`:
- `create_schema.sql` — schema + sample data
- `ranking_functions.sql`
- `aggregate_functions.sql`
- `navigation_functions.sql`
- `distribution_functions.sql`

(Each script contains comments and is ready to run in MySQL / XAMPP)

---

## 5. Screenshots
Folder: `/screenshots/`  
Include clear screenshots for each query: ranking, aggregate, navigation, distribution:
- `ranking.png`
- `aggregate.png`
- `navigation.png`
- `distribution.png`

> Ensure the result columns and window-function outputs are visible in each screenshot.

---

## 6. Results Analysis (3 layers)

### Descriptive
Sales are moderately concentrated: a few customers and products generate a majority of revenue. Daily sales show occasional spikes with several low-volume days.

### Diagnostic
Top customers are concentrated in Kigali and often purchase higher-priced apparel (jackets, dresses). Spikes align with product launches or promotions (data shows clustered high-value transactions).

### Prescriptive
1. Prioritize inventory for top quartile SKUs and customers (reorder point & safety stock).  
2. Target top- and second-quartile customers with retention offers and cross-sell campaigns.  
3. Use 7-day / 3-month moving averages for ordering cadence; flag days with sudden negative growth for review.

---

**References (APA style)**

1. MySQL. (2025). MySQL 8.0 Reference Manual: Window Functions. Oracle Corporation. 
Retrieved from https://dev.mysql.com/doc/refman/8.0/en/window-functions.html

2. MySQL. (n.d.). Introducing window functions. MySQL Blog. 
Retrieved from https://mysqlserverteam.com/introducing-window-functions-in-mysql-8-0/

3. Oracle. (n.d.). Analytic (window) functions. Oracle Documentation.
Retrieved from https://docs.oracle.com/en/database/oracle/oracle-database/19/sqlrf/analytic-functions.html

4. Percona. (2020). Window functions in MySQL 8.0. Percona Blog.
Retrieved from https://www.percona.com/blog/2020/06/22/window-functions-in-mysql-8-0/

5. LearnSQL. (n.d.). MySQL RANGE clause in window functions. 
Retrieved from https://learnsql.com/blog/range-clause-window-functions/

6. Devart. (n.d.). MySQL window functions tutorial.
Retrieved from https://www.devart.com/dbforge/mysql/studio/windows-functions.html

7. Modern-SQL. (n.d.). RANGE BETWEEN with datetime in MySQL.
Retrieved from https://modern-sql.com/feature/window-functions-range-between

8. GeeksforGeeks. (2022). MySQL window functions overview. 
Retrieved from https://www.geeksforgeeks.org/window-functions-in-mysql/

9. W3Schools. (n.d.). SQL window functions.
Retrieved from https://www.w3schools.com/sql/sql_window.asp

10. AUCA Course. (2024_2025). Database Management Systems lecture slides / class notes. African University of Central Africa.
---

## 8. Integrity Statement
All sources were properly cited. Implementations and analysis represent original work. No AI-generated content was copied without attribution or adaptation.
