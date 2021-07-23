# Join and Group - Example 

```
# fake 100 itilian movies 
UPDATE film SET language_id = 2 WHERE film_id > 900;
# Group by to show number of itilian and english movies
# Interesting for reporting 
SELECT l.name,count(l.name) FROM film f JOIN language l ON f.language_id = l.language_id GROUP BY l.name;

```
