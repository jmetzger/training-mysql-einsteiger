# Inhalte aus Tabellen anzeigen 

## Einfaches Beispiel (bestimmte Felder) 

```
# Zeige alle diese felder aus dieser Tabelle 
SELECT <welche_feld_mit_komma_getrennt> FROM <welche tabelle>

-- bitte datenbank sakila verwenden 
use sakila 
-- zeige actor_id, last_name 
SELECT actor_id, last_name FROM actor 

```

## Einfaches Beispiel (alle Felder) 
```

-- bitte datenbank sakila verwenden 
use sakila 
-- zeige actor_id, last_name 
SELECT * FROM actor 

```

## Einfaches Beispiel mit Bedingung 

```
-- SYNTAX
use sakila;
-- SELECT <welche_felder> FROM <welche_tabelle> WHERE <wo_welches_feld_welchen_wert_hat>
-- Beispiel 1 
SELECT actor_id, last_name FROM actor where actor_id = 5;
-- Beispiel 2
SELECT * FROM actor where actor_id = 5;
```

## Einfache Bedingung mit Bereich(en)

```
-- SYNTAX
use sakila;
-- SELECT <welche_felder> FROM <welche_tabelle> WHERE <wo_welches_feld_welchen_wert_hat>
-- Beispiel 1 
SELECT actor_id, last_name FROM actor where actor_id > 8;
-- Beispiel 2
SELECT * FROM actor where actor_id > 8;
-- Beispiel 3
SELECT * FROM actor where actor_id > 8 and actor_id < 50;

```

## Zwei Bereiche abfragen 

```
# Brackets are not necessary, works the same 
select * from actor where (actor_id >= 8  and actor_id <=50) or (actor_id >= 100 and actor_id <= 150)
```
