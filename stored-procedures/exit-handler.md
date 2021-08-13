# Exit Handler 

## Example 1 (Handler without begin end) 

```
-- In heidisql 

DELIMITER /
CREATE OR REPLACE PROCEDURE handlertest()
BEGIN
  DECLARE EXIT HANDLER FOR 1146 
    SELECT 'Sorry mate, wrong table';
  
  SELECT actor_id FROM wrong_table_name; 
  SELECT 'continue';
  SELECT * FROM actor WHERE actor_id = 1;

END /

```


```
-- Execute the CALL in an mysql - client to really see, what is going on 
-- In heidisql and other guis you will probably only see the output of the first select
MariaDB [sakila]> CALL handlertest;
+-------------------------+
| Sorry mate, wrong table |
+-------------------------+
| Sorry mate, wrong table |
+-------------------------+
1 row in set (0.001 sec)

+----------+
| continue |
+----------+
| continue |
+----------+
1 row in set (0.001 sec)

+----------+------------+-----------+
| actor_id | first_name | last_name |
+----------+------------+-----------+
|        1 | PENELOPE   | GUINESS   |
+----------+------------+-----------+
1 row in set (0.003 sec)

Query OK, 0 rows affected (0.003 sec)

MariaDB [sakila]> 

```

## Example 2: with begin and end (handler) 

```
-- Important: At the end of th BEGIN END; block for DECLARE CONTINUE .. 
-- There has to be an ";" at then end of END -> END; 

DELIMITER /
CREATE OR REPLACE PROCEDURE handlertest()
BEGIN
  DECLARE EXIT HANDLER FOR 1146 
  BEGIN 
     SELECT 'Sorry mate, wrong table';
  END;
  
  SELECT actor_id FROM wrong_table_name; 
  SELECT 'continue';
  SELECT * FROM actor WHERE actor_id = 1;

END /

```



```
-- Execute the CALL in an mysql - client to really see, what is going on 
-- In heidisql and other guis you will probably only see the output of the first select
MariaDB [sakila]> CALL handlertest;
+-------------------------+
| Sorry mate, wrong table |
+-------------------------+
| Sorry mate, wrong table |
+-------------------------+
1 row in set (0.001 sec)

+----------+
| continue |
+----------+
| continue |
+----------+
1 row in set (0.001 sec)

+----------+------------+-----------+
| actor_id | first_name | last_name |
+----------+------------+-----------+
|        1 | PENELOPE   | GUINESS   |
+----------+------------+-----------+
1 row in set (0.003 sec)

Query OK, 0 rows affected (0.003 sec)

MariaDB [sakila]> 

```

