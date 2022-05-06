# Beispiel komplexer Join 


## Beispiel 

```
select f.rental_rate,count(f.rental_rate)
from film f 
join film_category fc 
on f.film_id = fc.film_id
join category c 
on fc.category_id = c.category_id
WHERE c.name ='Comedy'
AND f.rental_rate > 0.99
GROUP BY f.rental_rate
ORDER BY f.rental_rate DESC;
```

## Übung 

```
Gib alle Filme aus, die der category Family angehören
und deren rental_rate = 2.99 ist. 
Gruppiere sie nach den replacement_cost.
Gibt folgende Felder aus:
   replacment_cost und die Anzahl replacement_cost
```   
