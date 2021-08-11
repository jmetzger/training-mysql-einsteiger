# Explain verwenden 

## Einfacher Fall 

```
explain select * from actor 
```

## Erweiterter Fall
```
explain extended select * from user 
show warnings 
```

## Anzeigen der Partitions 

```
explain partitions select * from actor 
```


## Ausgabe im JSON-Format 

```
# Hier gibt es noch zusätzliche Informationen 
explain format=json select * from actor 
```

```
explain format=json  SELECT a.first_name, a.last_name, fa.film_id FROM film_actor2 fa INNER JOIN actor2 a ON fa.actor_id = a.actor_id

```

# What does type say ? 

* https://mariadb.com/kb/en/explain/
