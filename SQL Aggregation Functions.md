### SQL Aggregation Functions
This is a curated details on SQL aggregation functions along with sample queries demonstrating their usage. Aggregation functions are crucial for summarizing and analyzing data in relational databases, and this guide provides practical examples to help you effectively apply these functions in your SQL queries.


```sql
----------------------------------------------------
--AVG()
----------------------------------------------------
SELECT AVG(unit_price)
  FROM products;
  
SELECT AVG(emp_curr_salary)
  FROM employees;

----------------------------------------------------
--COUNT()
----------------------------------------------------

SELECT COUNT(*)
  FROM orders;
  
SELECT COUNT(prod_id)
  FROM order_details;

----------------------------------------------------
--MAX() and MIN()
----------------------------------------------------
SELECT MAX(unit_price), MIN(unit_price)
  FROM products;

----------------------------------------------------
--SUM()
----------------------------------------------------
SELECT SUM(quantity)
  FROM order_details;
  
  

----------------------------------------------------
--SUM()
----------------------------------------------------
SELECT COUNT(DISTINCT prod_id)
  FROM order_details
  
SELECT COUNT(prod_id)
  FROM order_details
  
----------------------------------------------------
--Aggregation with GROUP BY
----------------------------------------------------
SELECT cat.category_name, COUNT(prod_name)
  FROM products prod
INNER JOIN categories cat ON prod.category_id = cat.category_id
GROUP BY category_name
ORDER BY category_name ASC;

SELECT cat.category_name, SUM(units_in_stock)
  FROM products prod
INNER JOIN categories cat 
		ON prod.category_id = cat.category_id
GROUP BY category_name
ORDER BY category_name ASC;

```
