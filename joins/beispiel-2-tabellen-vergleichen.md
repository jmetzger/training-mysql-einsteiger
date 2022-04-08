# Beispiel - Vergleich von 2 Tabellen 

## Zeige alle Zeilen an, bei dem einen Wert in einem Feld in beiden Tabellen vorkommt. 

```
-- Wert soll jeweils im Feld last_name vorkommen 
-- Vorbereitung (Simulation) 
create table testtabelle as select * from actor where last_name like 'A%';
SELECT a.*,t.* FROM actor a JOIN testtabelle t ON a.last_name = t.last_name; 

```
