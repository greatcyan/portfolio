### SQL Aggregation Functions
In this document, we explore SQL aggregation functions, which are essential for summarizing and analyzing data in relational databases. Aggregation functions perform calculations on a set of values and return a single result. They are widely used in SQL queries to group data, calculate statistics, and generate insights from large datasets.


```python
----------------------------------------------------
-- AVG()
----------------------------------------------------
> SELECT AVG(unit_price)
> FROM products;
+--------------------+
| AVG(unit_price)   |
+--------------------+
|         19.75     |
+--------------------+

> SELECT AVG(emp_curr_salary)
> FROM employees;
+---------------------------+
| AVG(emp_curr_salary)     |
+---------------------------+
|        54000.00          |
+---------------------------+


----------------------------------------------------
-- COUNT()
----------------------------------------------------
> SELECT COUNT(*)
> FROM orders;
+----------+
| COUNT(*) |
+----------+
|   1050   |
+----------+

> SELECT COUNT(prod_id)
> FROM order_details;
+--------------------+
| COUNT(prod_id)    |
+--------------------+
|        2000       |
+--------------------+

----------------------------------------------------
-- MAX() and MIN()
----------------------------------------------------
> SELECT MAX(unit_price), MIN(unit_price)
> FROM products;
+----------------+----------------+
| MAX(unit_price)| MIN(unit_price)|
+----------------+----------------+
|      299.99    |       5.00     |
+----------------+----------------+

----------------------------------------------------
-- SUM()
----------------------------------------------------
> SELECT SUM(quantity)
> FROM order_details;
+---------------+
| SUM(quantity) |
+---------------+
|     15000     |
+---------------+

----------------------------------------------------
-- COUNT(DISTINCT) and COUNT()
----------------------------------------------------
> SELECT COUNT(DISTINCT prod_id)
> FROM order_details;
+------------------------------+
| COUNT(DISTINCT prod_id)     |
+------------------------------+
|            500              |
+------------------------------+

> SELECT COUNT(prod_id)
> FROM order_details;
+--------------------+
| COUNT(prod_id)    |
+--------------------+
|        2000       |
+--------------------+

----------------------------------------------------
-- Aggregation with GROUP BY
----------------------------------------------------
> SELECT cat.category_name, COUNT(prod_name)
> FROM products prod
> INNER JOIN categories cat ON prod.category_id = cat.category_id
> GROUP BY category_name
> ORDER BY category_name ASC;
+------------------+------------------+
| category_name    | COUNT(prod_name) |
+------------------+------------------+
| Electronics      |        120       |
| Furniture        |        80        |
| Office Supplies  |        150       |
+------------------+------------------+

> SELECT cat.category_name, SUM(units_in_stock)
> FROM products prod
> INNER JOIN categories cat ON prod.category_id = cat.category_id
> GROUP BY category_name
> ORDER BY category_name ASC;
+------------------+-------------------+
| category_name    | SUM(units_in_stock)|
+------------------+-------------------+
| Electronics      |        5000       |
| Furniture        |        3000       |
| Office Supplies  |        4500       |
+------------------+-------------------+

```
