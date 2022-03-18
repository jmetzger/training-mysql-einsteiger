# Working with partitions 

## Pre-Requisites 

```
# partition als engine muss aktiviert sein
# ist eigentlich immer der fall 
SHOW PLUGINS;
...
| Aria                          | ACTIVE   | STORAGE ENGINE     | NULL    | GPL     |
| FEEDBACK                      | DISABLED | INFORMATION SCHEMA | NULL    | GPL     |
| partition                     | ACTIVE   | STORAGE ENGINE     | NULL    | GPL     |
+-------------------------------+----------+--------------------+---------+---------+

```


## Refs:

  * https://mariadb.com/kb/en/partitioning-overview/
