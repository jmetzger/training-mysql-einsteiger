# Example left joins 

## Example Left Join über 2 Tabellen (1:1) 

```
SELECT a.*,c.last_name FROM address a LEFT JOIN customer c ON a.address_id = c.address_id;
SELECT a.*,c.last_name FROM address a LEFT JOIN customer c ON a.address_id = c.address_id WHERE c.last_name IS NULL;


```
## Exercise über 2 Tabellen (1:1) 

```
DB: sakila
Tables: address,store  
Feld: address_id 

Zeigt alle addressen an und bei allen addressen wo es keinen store gibt NULL 
(LEFT JOIN) 


```