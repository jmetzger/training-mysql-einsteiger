# Example joins 

## Example Join über 2 Tabellen (1:1) 

```
SELECT a.*,c.* FROM customer c JOIN address a ON c.address_id = a.address_id; 
SELECT c.first_name,c.last_name,a.postal_code FROM customer c JOIN address a ON c.address_id = a.address_id; 

```
## Exercise 

```
Zeige alle Adressen der Stores an ? (Alle Felder von store und von address


```
