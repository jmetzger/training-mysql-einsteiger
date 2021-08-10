# Aktivierung: Query not using indexes 

```

-- long_query_time can auf 10 sec bleiben 
SET GLOBAL log_queries_not_using_indexes = 1; 
SET GLOBAL log_output = 'TABLE';
-- last setting  
SET slow_query_log = 1; 
```
