# Custom Exception Error 

## Variante 1

```
USE `sakila`;
DROP PROCEDURE IF EXISTS actortest;
DELIMITER /
CREATE OR REPLACE PROCEDURE actortest(OUT n_actor_id INT)
BEGIN
    
	 
    DECLARE EXIT HANDLER FOR SQLEXCEPTION
    BEGIN
    GET DIAGNOSTICS CONDITION 1 @SQLSTATE = RETURNED_SQLSTATE, 
	 @errno = MYSQL_ERRNO, @TEXT = MESSAGE_TEXT;  
	 SET @full_error = CONCAT("ERROR ", @errno, " (", @SQLSTATE, "):", @TEXT);
	 SELECT @full_error;
	 END;
   
    SELECT actor_id INTO n_actor_id FROM NOT_actor_ctor WHERE actor_id = 1; 
	 -- SET n_actor_id = 55;
    
	 
	 
END; /

DELIMITER ;

```

