# Example joins 

## Example Join über 2 Tabellen (1:1) 

```
SELECT a.*,c.* FROM customer c JOIN address a ON c.address_id = a.address_id; 
SELECT c.first_name,c.last_name,a.postal_code FROM customer c JOIN address a ON c.address_id = a.address_id; 
-- komplexe alterantive, ich würde davon abraten, weil zuviel Schreibarbeit 
SELECT customer.first_name,customer.last_name,address.postal_code FROM customer JOIN address ON customer.address_id = address.address_id; 

```
## Exercise über 2 Tabellen (1:1) 

```
DB: sakila
Tables: store,address  
Feld: address_id 
Zeige alle Adressen der Stores an ? (Alle Felder von store und von address


```
