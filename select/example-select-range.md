# Select mit Range 

## Beispiel 1

```
SELECT * FROM actor where actor_id > 100 and actor_id < 150;

# 10 und 50 inkludiert
select * from actor where actor_id >= 10 and actor_id <= 50;

```

```
SELECT * FROM actor where actor_id between 100 and 150;


```

## Übung 1

```
- Gebe alle Adressen (address) aus, wo der postal_code > 10000 und postal_code < 20000 ist 
oder < 90000 und > 50000 
- sortiert nach district 
- gebe 20 Einträge aus (offset 0) 
```
