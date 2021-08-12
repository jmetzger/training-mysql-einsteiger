# IF in Stored Procedures 

## Example 1

```
-- Gibt 1 aus 
-- SELECT werden auf dem Bildschirm angezeigt ;o) 

DELIMITER $$
USE sakila $$
DROP PROCEDURE IF EXISTS my_sproc $$
CREATE PROCEDURE
my_sproc ()
BEGIN
   IF 1=1
   THEN
     SELECT 1;
   END IF;
END $$

CALL my_sproc
```

## Example 2 

```
DELIMITER $
CREATE PROCEDURE my_pr()
BEGIN
IF 2 = 2 THEN
SELECT 'TRUE';
ELSE
SELECT 'FALSE';
END IF;
END $
DELIMITER ;
CALL my_pr;

```

## Example 3 

```
DELIMITER /
CREATE OR REPLACE PROCEDURE addActor (IN startdate DATE, IN enddate DATE) 
main: BEGIN 
   IF startdate > enddate 
   THEN 
      SELECT 'Das Startdaum liegt nach dem Enddatum';
      LEAVE main; 
	END IF;  
	
	SELECT 'das passt';

END/ 
DELIMITER ;
```


## Reference 

https://mariadb.com/kb/en/if/
