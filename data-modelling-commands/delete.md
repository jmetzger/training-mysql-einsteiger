# Delete 

## Simple Delete 

```
USE sakila;
DELETE FROM actor where actor_id > 200  
```

## Effective Deleting 

### All data needs to be deleted 

```
# use truncate, as it is way quicker 
CREATE TABLE actor2 AS SELECT * FROM actor;
TRUNCATE actor2
```

### Need to delete huge amount of data (e.g. 1.000.000 rows ? 

```
# Do it in iterations with DELETE 
# This is better for performance 
# It does not block that much 

```

```
# doing it in the application
# pseudo code 
rows_affected = 0
do {
   rows_affected = do_query(
      "DELETE FROM messages WHERE created < DATE_SUB(NOW(),INTERVAL 3 MONTH)
      LIMIT 10000")
} while rows_affected > 0
```
