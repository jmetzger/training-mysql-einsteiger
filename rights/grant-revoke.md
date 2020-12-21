# Grant / Revoke 

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
