# Function 

## Example 1 

```
CREATE FUNCTION hello (s CHAR(20))
    RETURNS CHAR(50) DETERMINISTIC
    RETURN CONCAT('Hello, ',s,'!');

```

## Example 2


```
DELIMITER //

CREATE FUNCTION CalcValue ( starting_value INT )
RETURNS INT DETERMINISTIC

BEGIN

   DECLARE total_value INT;

   SET total_value = 0;

   label1: WHILE total_value <= 3000 DO
     SET total_value = total_value + starting_value;
   END WHILE label1;

   RETURN total_value;

END; //

DELIMITER ;

-- Use it 
SELECT CalcValue (1000);

```


## Ref:

  * https://mariadb.com/kb/en/create-function/



