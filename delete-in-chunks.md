# Delete in chunks 

## Why 

  * Delete in chunks does not block so much 

## Example 

```
DROP PROCEDURE IF EXISTS archive_table;

DELIMITER $$

CREATE PROCEDURE archive_table()

BEGIN   
    REPEAT
        DO SLEEP(1); ## Optional, to minimise contention
        DELETE FROM data LIMIT 1000; 
        ## 10000 also works, this is more conservative  
    UNTIL ROW_COUNT() = 0 END REPEAT;
END$$

DELIMITER ;
CALL archive_table();
```
