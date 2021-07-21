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
