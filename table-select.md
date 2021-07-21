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
# SYNTAX
use sakila;
SELECT <welche_felder> FROM <welche_tabelle> WHERE <wo_welches_feld_welchen_wert_hat>
# Beispiel 
SELECT actor_id, last_name FROM actor where actor_id = 5
```
