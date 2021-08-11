# Index Stats (Storage Independent Stats) 

## General 

```
Index stats where introduced in MariaDB 10.4 
(These can be used by the query optimizer) 

Before that only indexes were used, 
now it is also possible these stats into account

The stats are saved in the mysql-database 
mysql.column_stats
mysql.table_stats
mysql.index_stats 

These are histogramm stats,
they are used automatically from 10.4.1 on,
but they are not created automatically. 

You have to perform an operation which is 
cost intensive to create them, because a full
table scan is done. 


These stats are 
Engine-independent Statistics

```

## Notes

  * Stats are currently used (MariaDB 10.6) by default because of setting
    * show variables like 'use_stat_tables'
    * -> preferably_for_queries 
  * But: They are not created automatically (see Howto how to do that) 
  * Also: They are not deleted automatically 



## Howto 

```
use mysql;
select * from column_stats;
select * from index_stats;
select * from table_stats;
use contributions;
ANALYZE TABLE contributions PERSISTENT FOR ALL;

use mysqL;
select * from column_stats;
select * from index_stats;
select * from table_stats;

```

## When will it be used ? 

```
2021-08-11: Looks like it is currently used for range-scan for the optimizer,
which table to start with 

An excessive example can be found here: 


```


## Refs:

  * https://mariadb.com/kb/en/histogram-based-statistics/
