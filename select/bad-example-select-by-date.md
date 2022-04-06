# Bad Example Select by date (Performance) 

## Example 

```
# Es kann kein Index (Eintrag im Schlagwortverzeichnis verwendet werden) 
select YEAR(return_date),return_date from rental where YEAR(return_date) <= 2005;

# Besser: Index kann verwendet werden.
SELECT YEAR(return_date),return_date 
FROM rental 
WHERE return_date >= '2005-01-01 00:00:01' 
AND return_date <= '2005-12-31 23:59:59';
```

## Example 2:

```
select YEAR(return_date),MONTH(return_date),DAY(return_date) from rental; 
```

## Exercise 

```
Lasst euch alle Rückgaben aus Rental anzeigen, die zwischen (inkl) dem 27. und 30. zurückgegeben wurden 
(egal welchen Monats) 
```
