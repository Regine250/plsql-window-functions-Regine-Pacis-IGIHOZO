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

## 7. References (minimum 10)
1. MySQL 8.0 Reference Manual — Window Functions.  
2. MySQL Blog — Introducing Window Functions.  
3. Oracle Docs — Analytic (Window) Functions (conceptual background).  
4. Percona Blog — Window Functions in MySQL 8.0.  
5. LearnSQL — RANGE Clause in Window Functions.  
6. devart — MySQL Window Functions tutorial.  
7. Modern-SQL (caniuse) — RANGE BETWEEN with datetime.  
8. GeeksforGeeks — MySQL Window Functions overview.  
9. W3Schools — SQL Window Functions (examples).  
10. Course lecture slides / class notes.

> (Add links and full citations in the README when you finalize.)

---

## 8. Integrity Statement
All sources were properly cited. Implementations and analysis represent original work. No AI-generated content was copied without attribution or adaptation.

---

## 9. Submission template (email)
To: eric.maniraguha@auca.ac.rw  
Subject: Repository Submission — plsql-window-functions-[lastname]-[firstname]

Body:
