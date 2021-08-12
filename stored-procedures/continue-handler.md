# Continue Handler 

```
USE `test`;
DROP PROCEDURE IF EXISTS `sp1`;
DELIMITER ||
CREATE PROCEDURE `sp1`()
BEGIN
    DECLARE `cur` CURSOR FOR
        SELECT 1 LIMIT 0;
    
    DECLARE CONTINUE HANDLER
        FOR 1326
    BEGIN
        SELECT 'cursor not open';
        -- no loop here
        CALL `sp1`();
    END;
    
    DECLARE CONTINUE HANDLER
        FOR 1146
    BEGIN
        SELECT 'table doesnt exist';
        CLOSE `cur`;
    END;
    
    DECLARE CONTINUE HANDLER
        FOR 1456
    BEGIN
        SELECT 'recursion not allowed';
        SELECT 1 FROM `not-exists`;
    END;
    
    CALL `sp1`();
END;
||
DELIMITER ;
CALL `sp1`();

```
