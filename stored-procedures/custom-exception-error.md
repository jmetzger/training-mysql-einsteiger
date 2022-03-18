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
         -- set local vars within diagnostics 
	 GET DIAGNOSTICS CONDITION 1 @sqlstate = RETURNED_SQLSTATE, 
	 @errno = MYSQL_ERRNO, @mytext = MESSAGE_TEXT;  
	 
	 SET @full_error = CONCAT("ERROR ", @errno, " (", @sqlstate, "):", @mytext);
	 SELECT @full_error;
    END;
   
    SELECT actor_id INTO @n_actor_id FROM NOT_actor WHERE actor_id = 1; 
    
	 
	 
END; /

DELIMITER ;

```

## Variante 2: Mit Schreiben in log-tabelle 

```
USE `sakila`;
CREATE TABLE IF NOT EXISTS applogs (id INT AUTO_INCREMENT, message MEDIUMTEXT, PRIMARY KEY(id));

DROP PROCEDURE IF EXISTS actortest;
DELIMITER /
CREATE OR REPLACE PROCEDURE actortest(OUT n_actor_id INT)
BEGIN
    
	 
    DECLARE EXIT HANDLER FOR SQLEXCEPTION
    BEGIN
    GET DIAGNOSTICS CONDITION 1 @SQLSTATE = RETURNED_SQLSTATE, 
	 @errno = MYSQL_ERRNO, @TEXT = MESSAGE_TEXT;  
	 SET @full_error = CONCAT("ERROR ", @errno, " (", @SQLSTATE, "):", @TEXT);
	 INSERT INTO applogs (message) VALUES (@full_error); 
	 SELECT @full_error;
	 END;
   
    SELECT actor_id INTO n_actor_id FROM NOT_actor_ctor WHERE actor_id = 1; 
	 -- SET n_actor_id = 55;
    
	 
	 
END; /

DELIMITER ;
```
