# Join über 3 Tabellen 

## Example 

```
-- Schritt 1 - Erstmal JOIN über 2 Tabellen 

select a.last_name,fa.film_id from actor a JOIN film_actor fa ON a.actor_id = fa.actor_id;

-- Schritt 2 (Schritt 1 erweitert)
-- Jetzt der JOIN über 3 Tabellen 
SELECT a.last_name,fa.film_id,f.title 
FROM actor a 
JOIN film_actor fa 
ON a.actor_id = fa.actor_id
JOIN film f 
ON fa.film_id = f.film_id;

```

## Exercise for Step 1 (Schritt 1) 

```
Db: sakila
Tables: film, film_category 

Zeigt alle category_id ' s aus der Tabelle film_category für den jeweiligen film an. 

```
