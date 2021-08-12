# Continue Handler 

```
USE `sakila`;
DROP PROCEDURE IF EXISTS actortest;
DELIMITER /
CREATE OR REPLACE PROCEDURE actortest()
BEGIN
     
    DECLARE CONTINUE HANDLER
        FOR 1146
    BEGIN
        SELECT 'You check the wrong table Mate';
    END;
   
    SELECT actor_id into @foo FROM no_actor_table;
	 
END; / 

DELIMITER ;


CALL actortest();
-- or
-- CALL actortest

```
