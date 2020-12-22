# Create and export dummy data (4.500.000 Million datasets)

## Creation 

```
CREATE TABLE `data` 
(
  `id`         bigint(20) NOT NULL      AUTO_INCREMENT,
  `datetime`   timestamp  NULL          DEFAULT CURRENT_TIMESTAMP,
  `channel`    int(11)                  DEFAULT NULL,
  `value`      float                    DEFAULT NULL,

  PRIMARY KEY (`id`)
);

-- 10.000.000 Datasets 
DELIMITER $$
CREATE PROCEDURE generate_data()
BEGIN
  DECLARE i INT DEFAULT 0;
  WHILE i < 10000000 DO
    INSERT INTO `data` (`datetime`,`value`,`channel`) VALUES (
      FROM_UNIXTIME(UNIX_TIMESTAMP('2020-01-01 01:00:00')+FLOOR(RAND()*31536000)),
      ROUND(RAND()*100,2),
      1
    );
    SET i = i + 1;
    SELECT i as iteration,now(); 
  END WHILE;
END$$
DELIMITER ;

CALL generate_data();
DROP PROCEDURE generate_data;

```

## Export as csv 

```
# there is a secure path, where it is allowed to export 
mysql -e 'SHOW VARIABLES LIKE "secure_file_priv";'
# assuming we created the procedure inside database sakila 
mysqldump --tab=/var/lib/mysql-files sakila data 
```

  * You will find the structure of the table here [Play data structure](/helpers/data/data.sql) 
  * You will find this data here: [Play data](/helpers/data/data.txt.bz2)

## Import from csv

```
mysql> select now();
+---------------------+
| now()               |
+---------------------+
| 2020-12-22 06:45:12 |
+---------------------+
1 row in set (0.00 sec)

mysql> LOAD DATA INFILE '/var/lib/mysql-files/data.txt' INTO TABLE sakila.data;
Query OK, 5585240 rows affected (22.11 sec)
Records: 5585240  Deleted: 0  Skipped: 0  Warnings: 0

mysql> select now();
+---------------------+
| now()               |
+---------------------+
| 2020-12-22 06:45:56 |
+---------------------+
1 row in set (0.00 sec)

mysql> 
```
