# Cursor 

## Example 1:

```
CREATE DATABASE IF NOT EXISTS training;
USE training;


CREATE TABLE c1(i INT);

CREATE TABLE c2(i INT);

CREATE TABLE c3(i INT);

DELIMITER //

CREATE PROCEDURE p1()
BEGIN
  DECLARE done INT DEFAULT FALSE;
  DECLARE x, y INT;
  DECLARE cur1 CURSOR FOR SELECT i FROM c1;
  DECLARE cur2 CURSOR FOR SELECT i FROM c2;
  DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;

  OPEN cur1;
  OPEN cur2;

  read_loop: LOOP
    FETCH cur1 INTO x;
    FETCH cur2 INTO y;
    IF done THEN
      LEAVE read_loop;
    END IF;
    IF x < y THEN
      INSERT INTO c3 VALUES (x);
    ELSE
      INSERT INTO c3 VALUES (y);
    END IF;
  END LOOP;

  CLOSE cur1;
  CLOSE cur2;
END; //

DELIMITER ;

INSERT INTO c1 VALUES(5),(50),(500);
INSERT INTO c2 VALUES(10),(20),(30);

CALL p1;
SELECT * FROM c3;

```

## Example 2 

```
CREATE OR REPLACE PROCEDURE getActorNames(p_ab CHAR(1))
BEGIN
  DECLARE d_full_name VARCHAR(90);
  DECLARE done INT DEFAULT FALSE;
  DECLARE cur1 CURSOR FOR SELECT CONCAT(last_name,',',first_name) FROM actor where last_name LIKE CONCAT(p_ab,'%');
  DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;


  OPEN cur1;
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

CALL getActorNames('B');
SELECT * FROM actorlog;
```

## Example 3 

```
USE sakila;
-- DROP TABLE IF EXISTS actor_stats;
CREATE TABLE IF NOT EXISTS actor_stats(id INT auto_increment, last_name VARCHAR (90), howmany TINYINT, UNIQUE (last_name), primary key(id));

CREATE OR REPLACE PROCEDURE writeActorStats()
BEGIN
  DECLARE d_last_name VARCHAR(45);
  DECLARE done INT DEFAULT FALSE;
  DECLARE c_actors CURSOR FOR SELECT last_name FROM actor;
  DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;
  DECLARE CONTINUE HANDLER FOR 1062  
  BEGIN 
    UPDATE actor_stats SET howmany = howmany + 1 WHERE last_name = d_last_name;
  END;

  TRUNCATE actor_stats;

  OPEN c_actors;
  read_loop: LOOP
    FETCH c_actors INTO d_last_name; 
    
    IF done THEN
      LEAVE read_loop;
    ELSE 
        INSERT INTO actor_stats (last_name,howmany) values (d_last_name,1);
    END IF;
  END LOOP;

  CLOSE c_actors;
END; //

DELIMITER ;

CALL writeActorStats();
SELECT * FROM actor_stats;
SELECT * FROM actorlog;
```



## Reference 

  * https://mariadb.com/kb/en/cursor-overview/

