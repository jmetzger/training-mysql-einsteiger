# Prepared Statements with examples 

## Setup 

```
CREATE TABLE test (id int auto_increment, data varchar(40) NOT NULL DEFAULT '', PRIMARY KEY(id))
```

## Single Line (Insert) 

```
USE sakila;
PREPARE st1 FROM 'INSERT INTO actor (first_name,last_name) VALUES (?,?)';
SET @first_name = 'Johan'; 
SET @last_name = 'Muster';
EXECUTE st1 USING @first_name,@last_name; 
DEALLOCATE PREPARE st1;

SELECT * FROM actor ORDER BY order_id DESC;
```

## Multiline Prepared Statement (Insert)  

```
-- Statement vorbereiten 
PREPARE stmt1 FROM 'INSERT INTO test (data) VALUES (?), (?), (?)';
SET @d1 = 'Line1';
SET @d2 = 'Line2';
SET @d3 = 'Line3';
EXECUTE stmt1 USING @d1, @d2, @d3;

-- If you do not want to use it anymore DEALLOCATE IT 
DEALLOCATE PREPARE stmt1;

SELECT * from test;

```

## Using it with select 

```
create table t1 (a int,b char(10));
insert into t1 values (1,"one"),(2, "two"),(3,"three");
prepare test from "select * from t1 where a=?";
set @param=2;
execute test using @param;
+------+------+
| a    | b    |
+------+------+
|    2 | two  |
+------+------+
set @param=3;
execute test using @param;
+------+-------+
| a    | b     |
+------+-------+
|    3 | three |
+------+-------+
deallocate prepare test;
```

## Finding out number of rows 

```
If this function is executed immediately after execute. 



```
