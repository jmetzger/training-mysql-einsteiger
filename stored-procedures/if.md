# IF in Stored Procedures 

## Example 

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

## Reference 

https://mariadb.com/kb/en/if/
