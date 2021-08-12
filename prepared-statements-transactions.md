# Prepared Statements with transactions (Examples) 


```
use sakila;
create table test if not exists (id int auto_increment, data varchar(30), primary key(id));

START TRANSACTION;
PREPARE stmt2 FROM 'INSERT INTO test (`data`) VALUES (?)';
SET @d1 = 'Line1';
EXECUTE stmt2 USING @d1;
SET @d1 = 'Line2';
EXECUTE stmt2 USING @d1;
COMMIT;

SELECT * from test;


BEGIN;
SET @d1 = 'Line3 -uncommited';
EXECUTE stmt2 USING @d1;
ROLLBACK;

DEALLOCATE PREPARE stmt2;
SELECT * FROM test;
```
