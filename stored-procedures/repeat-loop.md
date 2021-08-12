# Repeat-Loop

## Example 

```
DELIMITER //

CREATE PROCEDURE dorepeat(p1 INT)
  BEGIN
    SET @x = 0;
    REPEAT 
       SET @x = @x + 1; 
    UNTIL @x > p1 
    END REPEAT;
  END
//

CALL dorepeat(1000)//

SELECT @x//


```

## Reference 


  * https://mariadb.com/kb/en/repeat-loop/#:~:text=The%20statement%20list%20within%20a,REPEAT%20statement%20can%20be%20labeled.

