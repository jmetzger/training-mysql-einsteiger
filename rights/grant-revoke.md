# Grant / Revoke 

## Creating user first 

  * The user needs to be created, otherwice it is not working 
  
```
# 
CREATE USER training@localhost identfied by '123xy6aT';

```

## Login as user training on commandline 

```
mysql -utraining -p 

```

## Wie sind unsere Berechtigungen 

```
# Welcher Benutzer bin ich ?
select user();

# Welche Rechte habe ich 
show grants;

```

## Rights on the different levels 

```
GLOBAL: for all databases -> mysql.user 
DATBASES: mysql.db
TABLES: mysql.tables_priv 
FIELDS: mysql.columns_priv 
```

# Grant Privileges (all) 

```
mysql> grant all on *.* to training@localhost;
Query OK, 0 rows affected (0.00 sec)

mysql> show grants for training@localhost;
+-------------------------------------------------------+
| Grants for training@localhost                         |
+-------------------------------------------------------+
| GRANT ALL PRIVILEGES ON *.* TO 'training'@'localhost' |
+-------------------------------------------------------+
1 row in set (0.00 sec)

mysql>
```

# Grant privileges on a specific database 

```
revoke all on *.* to training@localhost 
grant all on training.* to training@localhost; 
```
