# Index Stats 

## General 

```
Index stats where introduced in MariaDB 10.4 
(These can be used by the query optimizer) 

Before that only indexes were used, 
now it is also possible these stats into account

The stats are saved in the mysql-database 

These are histogramm stats,
they are used automatically from 10.4.1 on,
but they are not created automatically. 

You have to perform an operation which is 
cost intensive to create them, because a full
table scan is done. 


These stats are 
Engine-independent Statistics

```

## Refs:

  * https://mariadb.com/kb/en/histogram-based-statistics/
