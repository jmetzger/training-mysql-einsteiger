# Different result double pipes 

```
MariaDB [(none)]> select @@sql_mode;
+-------------------------------------------------------------------------------------------+
| @@sql_mode                                                                                |
+-------------------------------------------------------------------------------------------+
| STRICT_TRANS_TABLES,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION |
+-------------------------------------------------------------------------------------------+
1 row in set (0.000 sec)

MariaDB [(none)]> SELECT 'hallo' || 'hans';
+-------------------+
| 'hallo' || 'hans' |
+-------------------+
|                 0 |
+-------------------+
1 row in set, 4 warnings (0.001 sec)

MariaDB [(none)]> set sql_mode = oracle
    -> ;
Query OK, 0 rows affected (0.000 sec)

MariaDB [(none)]> SELECT 'hallo' || 'hans';
+-------------------+
| 'hallo' || 'hans' |
+-------------------+
| hallohans         |
+-------------------+
1 row in set (0.000 sec)

MariaDB [(none)]> 

```
