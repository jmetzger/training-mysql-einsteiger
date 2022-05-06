# Views mit Beispielen 

## Einfaches Beispiel 

```
use sakila;
CREATE VIEW actor_vorname AS SELECT first_name AS vorname FROM actor;
select * from actor_vorname;
select * from actor_vorname where vorname like 'A%';
```

## Über View updaten wenn Updatable 

```
use sakila;
UPDATE actor_vorname SET vorname='BRANGELINA' WHERE vorname = 'ANGELINA';
```

## Neue Felder, sind NICHT automatisch im View: 

```
alter table actor add column city varchar(45) default 'Hildesheim';
# city is not nicht im view
select * from actor_b; 

# erst wenn ich das create oder alter statement ausführen 
alter view actor_b as select * from actor where last_name like 'B%';
select * from actor_b; 

```

## Übung 

```
A. 
Erstelle ein view, das nur den title und die 2 ersten Buchstaben des Titels anzeigt,
mit dem Name film_short. 

Nenne die felder: title_lang und title_short 

B. 
Gibt mit hilfe des title_lang - feldes Titel aus die mit "A%" beginnen 

```
