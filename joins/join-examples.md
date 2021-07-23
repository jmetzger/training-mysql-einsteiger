# Join examples 

```
# Work - step by step. 
SELECT * FROM film f;
SELECT f.title FROM film f;
SELECT f.language_id FROM film f JOIN language l ON f.language_id = l.language_id; 
-- aus film-tabelle alle felder - f.* 
SELECT f.*,l.name FROM film f JOIN language l ON f.language_id = l.language_id; 
SELECT f.film_id,f.title,l.name,f.description FROM film f JOIN language l ON f.language_id = l.language_id;
```
