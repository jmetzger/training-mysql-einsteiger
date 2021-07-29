# MySQL - alter table instant/inplace/copy 

## Example 

```

mysql> CREATE TABLE personen (id mediumint unsigned auto_increment,name varchar(40),vorname varchar(40),primary key(id));
Query OK, 0 rows affected (0.03 sec)

mysql> CREATE TABLE personen2 (id mediumint unsigned xauto_increment,name varchar(40),vorname varchar(40),primary key(id)); 
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'xauto_increment,name varchar(40),vorname varchar(40),primary key(id))' at line 1
mysql> show create table personen;
+----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Table    | Create Table                                                                                                                                                                                                                                  |
+----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| personen | CREATE TABLE `personen` (
  `id` mediumint unsigned NOT NULL AUTO_INCREMENT,
  `name` varchar(40) DEFAULT NULL,
  `vorname` varchar(40) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci |
+----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
1 row in set (0.00 sec)

mysql> alter table personen modify id int unsigned NOT NULL AUTO_INCREMENT;
Query OK, 0 rows affected (0.02 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> alter table personen modify id mediumint unsigned not null auto_increment algorithm=INSTANT;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'algorithm=INSTANT' at line 1
mysql> alter table personen modify id mediumint unsigned not null auto_increment, algorithm=INSTANT;
ERROR 1846 (0A000): ALGORITHM=INSTANT is not supported. Reason: Cannot change column type INPLACE. Try ALGORITHM=COPY/INPLACE.
mysql> alter table personen modify id int unsigned not null auto_increment, algorithm=INSTANT;
Query OK, 0 rows affected (0.01 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> alter table personen modify id mediumint unsigned not null auto_increment, algorithm=INSTANT;
ERROR 1846 (0A000): ALGORITHM=INSTANT is not supported. Reason: Cannot change column type INPLACE. Try ALGORITHM=COPY/INPLACE.
mysql> alter table personen modify id mediumint unsigned not null auto_increment, algorithm=INPLACE;
ERROR 1846 (0A000): ALGORITHM=INPLACE is not supported. Reason: Cannot change column type INPLACE. Try ALGORITHM=COPY.
mysql> alter table personen modify id mediumint unsigned not null auto_increment, algorithm=COPY;
Query OK, 0 rows affected (0.02 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> 
```


## Reference 

  * https://mydbops.wordpress.com/2020/03/04/an-overview-of-ddl-algorithms-in-mysql-covers-mysql-8/

## Alternative 

  * pt-online-schema-change 
