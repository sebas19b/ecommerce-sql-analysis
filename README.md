# ecommerce-sql-analysis
Advanced SQL project analyzing e-commerce data. Includes schema design, sample data, and 8 real-world queries using window functions, CTEs, and aggregations. Built with PostgreSQL.

## Database Schema

5 related tables:

    1.customers(customer_id, full_name, email, country, created_at)
    2.categories(category_id, name)
    3.products(product_id, name, categorory_id, price, stock)
    4.orders(order_id, customer_id, order_date, status)
    5.order_items(item_id, order_id, product_id, quantity, unit_price)

## Advanced Queries

### 1. Monthly Revenue (delivered orders only)
Groups revenue by month filtering only completed orders.
Techniques: `DATE_TRUNC`, `SUM`, `GROUP BY`

### 2. Top 5 Customers by Total Spending
Ranks customers by total amount spent across all orders.
Techniques: `RANK()`, `CTE (WITH)`, `JOIN`, `SUM`

### 3. Best-Selling Product per Category
Finds the top product in each category by units sold.
Techniques: `ROW_NUMBER()`, `PARTITION BY`, `CTE`

### 4. Cancellation Rate by Month
Calculates the percentage of cancelled orders per month.
Techniques: `FILTER`, `CASE`, `ROUND`, percentage formula

### 5. Multi-Category Buyers
Identifies customers who purchased from more than one category.
Techniques: `COUNT DISTINCT`, `HAVING`, multiple `JOIN`

### 6. Customer Retention Segments
Segments customers into one-time, returning, and loyal buyers.
Techniques: `CASE WHEN`, `CTE`, conditional grouping

### 7. Low Stock + High Demand Alert
Flags products with low stock but high sales volume.
Techniques: `HAVING`, multi-condition `WHERE`, `JOIN`

### 8. Running Total Revenue
Calculates cumulative revenue over time.
Techniques: `SUM() OVER (ORDER BY)` — advanced window function

## How to Run

1. Install PostgreSQL
2. Run the script:
