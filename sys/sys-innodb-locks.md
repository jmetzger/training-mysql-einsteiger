# Sys - Database - Show innodb-locks 

```
SELECT waiting_trx_id, waiting_pid, waiting_query, blocking_trx_id, blocking_pid, blocking_query 
FROM sys.innodb_lock_waits;
```
