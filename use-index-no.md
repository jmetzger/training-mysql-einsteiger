# Keinen Index verwenden 

```
SELECT * FROM actor USE INDEX() WHERE last_name LIKE 'D%';
-- Identify if really no index is used 
EXPLAIN SELECT * FROM actor USE INDEX() WHERE last_name LIKE 'D%';
```
