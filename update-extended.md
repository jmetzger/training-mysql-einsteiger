# Erweitertes Update 

## Aufgabe 

```
Erhöhe bei allen Datensätzen in film die rental_rate um 1 Euro,
für die Schauspieler "actor", deren Nachname mit D anfängt 
```

## Lösung 

```
SELECT DISTINCT fc.film_id FROM filmcopy fc JOIN film_actor fa ON fc.film_id = fa.film_id JOIN actor a ON fa.actor_id = a.actor_id where a.last_name like 'D%';

-- Version 1 
UPDATE filmcopy fc JOIN film_actor fa ON fc.film_id = fa.film_id JOIN actor a ON fa.actor_id = a.actor_id SET rental_rate = rental_rate + 1 WHERE a.last_name LIKE 'D%'

-- Version 2
UPDATE actor a  JOIN film_actor fa ON a.actor_id = fa.actor_id JOIN filmcopy f on fa.film_id = f.film_id  SET f.rental_rate = f.rental_rate + 1 WHERE a.last_name LIKE 'D%'


Query OK, 432 rows affected (0.02 sec)
Rows matched: 432  Changed: 432  Warnings: 0
```

