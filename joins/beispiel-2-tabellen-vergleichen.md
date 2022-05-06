# Beispiel - Vergleich von 2 Tabellen 

## Zeige alle Zeilen an, bei dem einen Wert in einem Feld in beiden Tabellen vorkommt. 

```
-- Wert soll jeweils im Feld last_name und first_name vorkommen 
-- Vorbereitung (Simulation) 
create table testtabelle as select * from actor where last_name like 'A%';
SELECT a.*,t.* FROM actor a JOIN testtabelle t ON a.last_name = t.last_name AND a.first_name = t.last_name; 

```
## Übung:

```
Lasse alle Kunden ausgeben, die auch gleichzeitig Schauspieler sind (anhand Vorname, Nachname)
Hint: actor, customer, first_name, last_name 




```

