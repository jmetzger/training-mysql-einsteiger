# Grant / Revoke 

# Rights on the different levels 

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
