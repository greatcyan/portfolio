### SQL Aggregation Functions
In this document, we explore SQL aggregation functions, which are essential for summarizing and analyzing data in relational databases. Aggregation functions perform calculations on a set of values and return a single result. They are widely used in SQL queries to group data, calculate statistics, and generate insights from large datasets.


```SQL
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
