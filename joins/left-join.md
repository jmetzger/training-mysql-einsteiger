# LEFT JOIN 

## General 

  * Show all entries from the left table and only from the right if available 
  * Examples are based on sakila database. 

## Example 

```
use sakila 
SELECT 
    c.customer_id, 
    c.first_name, 
    c.last_name,
    a.actor_id,
    a.first_name,
    a.last_name
FROM customer c
LEFT JOIN actor a 
ON c.last_name = a.last_name
ORDER BY c.last_name;
```
