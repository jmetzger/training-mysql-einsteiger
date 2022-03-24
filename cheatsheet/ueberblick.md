# Cheatsheat 

## Zugrechtfinden 

```
-- Welche Datenbanken gibt es:
show databases;

-- Welche Tabelle gibt es in einer Datenbank 
-- use <datenbankname>
use sakila;
show tables;

# Wie ist die Struktur eine Tabelle / welche Felder 
-- describe <tabellenname> z.B. actor 
describe actor
# Welche Indizies gibt es in einer Tabelle ? 
show indexes from actor

# Alle procedures/functions einer Datenbank auslesen
select * from information_schema.routines where routine_schema = 'sakila';
```
