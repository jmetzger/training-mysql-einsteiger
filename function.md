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

## Example 3 (Mit Variable anzahl vorher setzen) 

```
DELIMITER /

CREATE DEFINER=`ext`@`%` FUNCTION `Anzahl`(
	`starting_value` INT
)
RETURNS INT

BEGIN

   DECLARE total_value INT;
   DECLARE anzahl INT;
   -- SET total_value = 0;
   SELECT COUNT(*) INTO anzahl FROM actor; 

   -- WHILE total_value <= 3000 DO
   --  SET total_value = total_value + starting_value;
   -- END WHILE;

   -- RETURN total_value;
   RETURN anzahl;

END/


```

## Example 3 (Direkt in @anzahl schreiben) 

```
DELIMITER /

CREATE DEFINER=`ext`@`%` FUNCTION `schaupieler`(
	`starting_value` INT
)
RETURNS INT

BEGIN

   DECLARE total_value INT;
   SELECT COUNT(*) INTO @anzahl FROM actor; 
   RETURN @anzahl;

END/


```




## Ref:

  * https://mariadb.com/kb/en/create-function/



