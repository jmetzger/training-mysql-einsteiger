# Loop 

## Example 

```
DELIMITER //

CREATE or REPLACE PROCEDURE CalcValue ( starting_value INT )


BEGIN

   DECLARE total_value INT;

   SET total_value = 0;

   label1: LOOP
     SET total_value = total_value + starting_value;
     IF total_value < 850 THEN
       ITERATE label1;
     END IF;
     LEAVE label1;
   END LOOP label1;

   SELECT total_value;

END; //

DELIMITER ;

CALL CalcValue(200);

```

## Reference 


