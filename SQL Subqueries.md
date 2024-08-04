### Subqueries
Subqueries, or nested queries, are an essential feature in SQL that allow you to perform complex data retrieval operations by embedding one query within another. They are useful for scenarios where you need to filter, aggregate, or transform data based on the results of another query. This section provides examples of various types of subqueries, each illustrating different use cases and functionalities.

```sql
------------------------------------------------
-- Subquery 1 IN
------------------------------------------------
SELECT prod_id, prod_name, category_id
  FROM products
 WHERE category_id IN (
     SELECT category_id
       FROM categories
      WHERE category_name IN ('Dairy Products', 'Grains/Cereals', 'Beverages')
 )
ORDER BY category_id DESC;

------------------------------------------------
-- Subquery 2 NOT IN
------------------------------------------------
SELECT order_id, cust_id, order_date, ship_country
  FROM orders
 WHERE ship_via NOT IN (
     SELECT shipper_id
       FROM shippers
      WHERE company_name IN ('UPS', 'DHL')
 );

------------------------------------------------
-- Subquery 3 Inequality
------------------------------------------------
SELECT order_id, cust_id, order_date, ship_via, freight, ship_country
  FROM orders
 WHERE freight >= (
     SELECT AVG(freight)
       FROM orders
 );

------------------------------------------------
-- Subquery 4 FROM Clause
------------------------------------------------
-- Simple Query
SELECT ord.order_id, cust_id, emp.emp_id, emp.last_name, emp.first_name, prod_id, 
       unit_price, quantity, unit_price * quantity AS order_amount
  FROM orders ord
 INNER JOIN order_details od ON ord.order_id = od.order_id
 INNER JOIN employees emp ON ord.emp_id = emp.emp_id;

-- Subquery as a Derived Table
SELECT * 
  FROM (
     SELECT ord.order_id, cust_id, emp.emp_id, emp.last_name, emp.first_name, prod_id, 
            unit_price, quantity, unit_price * quantity AS order_amount
       FROM orders ord
      INNER JOIN order_details od ON ord.order_id = od.order_id
      INNER JOIN employees emp ON ord.emp_id = emp.emp_id
 ) AS emp_orders;

-- Aggregation on Subquery Result
SELECT cust_id, SUM(order_amount) AS total_order_amount
  FROM (
     SELECT ord.order_id, cust_id, emp.emp_id, emp.last_name, emp.first_name, prod_id, 
            unit_price, quantity, unit_price * quantity AS order_amount
       FROM orders ord
      INNER JOIN order_details od ON ord.order_id = od.order_id
      INNER JOIN employees emp ON ord.emp_id = emp.emp_id
 ) AS emp_orders
GROUP BY cust_id;

------------------------------------------------
-- Subquery 5 FROM with JOIN
------------------------------------------------
SELECT territory_description, AVG(order_amount) AS total_order_amount
  FROM (
     SELECT ord.order_id, cust_id, emp.emp_id, emp.last_name, emp.first_name, 
            prod_id, unit_price, quantity, unit_price * quantity AS order_amount
       FROM orders ord
      INNER JOIN order_details od ON ord.order_id = od.order_id
      INNER JOIN employees emp ON ord.emp_id = emp.emp_id
 ) AS emp_orders
 INNER JOIN employee_territories et ON emp_orders.emp_id = et.emp_id
 INNER JOIN territories terri ON terri.territory_id = et.territory_id
GROUP BY territory_description;

------------------------------------------------
-- Subquery 6 SELECT Working as a JOIN Statement
------------------------------------------------
SELECT cust.cust_id, (
    SELECT SUM(freight)
      FROM orders ord
     WHERE cust.cust_id = ord.cust_id
 ) AS total_shipping_freight
  FROM customers cust;

------------------------------------------------
-- Subquery 7 SELECT Comparison Between Single Values
------------------------------------------------
SELECT order_id, AVG(discount) AS order_discount, (
    (SELECT AVG(discount)
       FROM order_details) - AVG(discount)
 ) AS discount_diff
  FROM order_details
GROUP BY order_id;

------------------------------------------------
-- Subquery 8 SELECT Generate a Calculated Value
------------------------------------------------
SELECT order_id, AVG(discount) AS order_discount, (
    (SELECT AVG(discount)
       FROM order_details) - AVG(discount)
 ) AS discount_difference
  FROM order_details
GROUP BY order_id;

------------------------------------------------
-- Subquery 9 Correlated Subquery
------------------------------------------------
SELECT od.order_id, od.prod_id, unit_price, (
    SELECT AVG(unit_price)
      FROM order_details odin
     WHERE odin.order_id = od.order_id
 ) AS average_order_price
  FROM order_details od
GROUP BY od.order_id, od.prod_id;

------------------------------------------------
-- Subquery 10 Multiple Columns
------------------------------------------------
SELECT order_id, od.prod_id, prod.prod_name, od.unit_price
  FROM order_details od
 INNER JOIN products prod ON prod.prod_id = od.prod_id
 WHERE (od.order_id, od.unit_price) IN (
     SELECT order_id, MIN(unit_price)
       FROM order_details
      GROUP BY order_id
 );

-- Subquery to Get Minimum Unit Price
SELECT order_id, MIN(unit_price)
  FROM order_details
GROUP BY order_id
ORDER BY 1;
```
