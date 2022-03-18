# Queries ohne Indexes loggen (slow query log) 

```
# Windows my.ini 
[mysqld]

slow_query_log
# standard ist o.k. 
long_query_time=10
log_queries_not_using_indexes=ON


```
