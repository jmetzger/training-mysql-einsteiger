# Numerische Funktionen - ROUND/CEIL/FLOOR 

## Example 

```
-- Kaufmännisch runden 
SELECT ROUND(1.56,1);
-- Abschneiden
SELECT truncate(1.56,1);
-- FLOOR() -> abrunden zum nächsten Integer  
SELECT FLOOR(12.56);
-- CEIL() - Aufrunden zum nächsten Integer 
SELECT CEIL(12.3);

```

## Exercise 

```
1. Übung 

-- Db: sakila
-- Table: film 
-- Field: length 

Lass Dir die durchscnittliche Länge aller Filme, kaufmännisch gerundet auf volle Minuten anzeigen

2. Übung 

-- Db.: sakila 
-- Table: film 

Berechne die Summe aller replacement_cost(s) in film und runde dieser auf die nächste voller Zahl auf. 
HINT: SUM 

```
