# Select mit Range 

## Beispiel 1

```
SELECT * FROM actor where actor_id > 100 and actor_id < 150;

# 10 und 50 inkludiert
select * from actor where actor_id >= 10 and actor_id <= 50;
```

## Beispiel 2

```
SELECT * FROM actor where actor_id between 100 and 150;
```

## Übung 1

```
- Gebe alle Adressen (address) aus, wo der postal_code > 10000 und postal_code < 20000 ist 
oder < 90000 und > 50000 

```

## Übung 2

```
- Lasst euch Filme (film) anzeigen deren Wiederbeschaffungspreis (replacement_cost) zwischen 18.99 und 20.99 ist. (inkl) 

```

## Übung 3

```
Lass Euch alle Einträge aus dem inventory mit between im Bereich 10 bis 100 anzeigen (inkl 10 und 100) - inventory_id


```
