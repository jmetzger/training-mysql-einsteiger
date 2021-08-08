# Example From Migration 

## Prerequisites 

  * Examples: https://cloud.google.com/architecture/moving-procedures-from-oracle-to-cloud-sql-for-mysql?hl=de

## Example 1: 

```
# From Google Doc 

CREATE OR REPLACE PROCEDURE SP_HELLO_WORLD
IS
v_str_val VARCHAR2(20);
BEGIN
v_str_val := 'Hello World';
END;

# To let it work proper we incoporate an output, but that's all 
DELIMITER /
CREATE OR REPLACE PROCEDURE SP_HELLO_WORLD
IS
v_str_val VARCHAR2(20);
BEGIN
v_str_val := 'Hello World';
select v_str_val 
END/

# Exec does not work 
EXEC SP_HELLO_WORLD 
# CALL works 
CALL SP_HELLO_WORLD 
# Also inside an anonymous procedure works 
BEGIN 
  SP_HELLO_WORLD;
END/ 
```

## Example 2:


