# find out queries

```
set global general_log = 1;
-- run queries
set global general_log = 0
--
-- analyze log file, find path 
select @@general_log_file 
```
