# Explain 

```
explain format=json  SELECT a.first_name, a.last_name, fa.film_id FROM film_actor2 fa INNER JOIN actor2 a ON fa.actor_id = a.actor_id

```

# What does type say ? 

* https://dev.mysql.com/doc/refman/5.7/en/explain-output.html#explain-join-types
