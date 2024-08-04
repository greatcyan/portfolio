### SQL Aggregation Functions


```python
import sqlparse
```

###### AVG()


```python
query = """

SELECT AVG(unit_price)
  FROM products;
  
SELECT AVG(emp_curr_salary)
  FROM employees;

"""

formatted_query = sqlparse.format(query, reindent=True, keyword_case='upper')
print(formatted_query)
```

    
    SELECT AVG(unit_price)
    FROM products;
    
    
    SELECT AVG(emp_curr_salary)
    FROM employees;
    

###### COUNT()


```python
query = """

SELECT COUNT(*)
  FROM orders;
  
SELECT COUNT(prod_id)
  FROM order_details;

"""

formatted_query = sqlparse.format(query, reindent=True, keyword_case='upper')
print(formatted_query)
```

    
    SELECT COUNT(*)
    FROM orders;
    
    
    SELECT COUNT(prod_id)
    FROM order_details;
    

###### MIN() & MAX()


```python
query = """

SELECT MAX(unit_price), MIN(unit_price)
  FROM products;

"""

formatted_query = sqlparse.format(query, reindent=True, keyword_case='upper')
print(formatted_query)
```

    
    SELECT MAX(unit_price),
           MIN(unit_price)
    FROM products;
    

###### SUM()


```python
query = """

SELECT SUM(quantity)
  FROM order_details;

"""

formatted_query = sqlparse.format(query, reindent=True, keyword_case='upper')
print(formatted_query)
```

    
    SELECT SUM(quantity)
    FROM order_details;
    

###### COUNT() DISTINCT()


```python
query = """

SELECT COUNT(DISTINCT prod_id)
  FROM order_details
  
SELECT COUNT(prod_id)
  FROM order_details

"""

formatted_query = sqlparse.format(query, reindent=True, keyword_case='upper')
print(formatted_query)
```

    
    SELECT COUNT(DISTINCT prod_id)
    FROM order_details
    SELECT COUNT(prod_id)
    FROM order_details
    

###### Aggregation with GROUP BY


```python
query = """

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

"""

formatted_query = sqlparse.format(query, reindent=True, keyword_case='upper')
print(formatted_query)
```

    
    SELECT cat.category_name,
           COUNT(prod_name)
    FROM products prod
    INNER JOIN categories cat ON prod.category_id = cat.category_id
    GROUP BY category_name
    ORDER BY category_name ASC;
    
    
    SELECT cat.category_name,
           SUM(units_in_stock)
    FROM products prod
    INNER JOIN categories cat ON prod.category_id = cat.category_id
    GROUP BY category_name
    ORDER BY category_name ASC;
    


```python

```
