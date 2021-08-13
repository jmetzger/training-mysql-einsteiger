# Cursor with params 

## Example 1:

```
USE sakila;
DROP TABLE IF EXISTS actorlog;
CREATE TABLE actorlog(id INT auto_increment, full_name VARCHAR (90), primary key(id));
DELIMITER //

CREATE OR REPLACE PROCEDURE getActorName(p_id INT)
BEGIN
  DECLARE d_full_name VARCHAR(90);
  DECLARE done INT DEFAULT FALSE;
  DECLARE cur1 CURSOR(p_actor_id INT) FOR SELECT CONCAT(last_name,',',first_name) FROM actor where actor_id = p_actor_id;
  DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;

  OPEN cur1(p_id);
  read_loop: LOOP
    FETCH cur1 INTO d_full_name; 

    IF done THEN
      LEAVE read_loop;
    ELSE 
        INSERT INTO actorlog (full_name) values (d_full_name);
      END IF;
  END LOOP;

  CLOSE cur1;
END; //

DELIMITER ;

CALL getActorName(1);
SELECT * FROM actorlog;
```
