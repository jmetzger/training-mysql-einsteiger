# Views mit Beispielen 

## Einfaches Beispiel 

```
use sakila;
CREATE VIEW actor_vorname AS SELECT first_name AS vorname FROM actor;
select * from actor_vorname;
```

## Über View updaten wenn Updatable 

```
use sakila;
UPDATE actor_vorname SET vorname='BRANGELINA' WHERE vorname = 'ANGELINA';
```

## Kann algorithm MERGE verwendet werden ? 

```
CREATE ALGORITHM=MERGE VIEW actor_b AS SELECT * FROM actor WHERE last_name LIKE 'B%';
```
