# SQL-PL
## Problem
A mid-sized Rwandan clothing company struggles with inventory and demand forecasting.  
The goal is to use **PL/SQL window functions** to analyze sales transactions,  
identify top customers, track trends, compare performance across time,  
and segment customers into meaningful groups.

## Database Schema
We work with one main table: `transactions`

```sql
CREATE TABLE transactions (
    transaction_id INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT NOT NULL,
    product_id INT NOT NULL,
    sale_date DATE NOT NULL,
    amount DECIMAL(10,2) NOT NULL
);
