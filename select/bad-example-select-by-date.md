# Bad Example Select by date (Performance) 

## Example 

```
select YEAR(return_date),return_date from rental where YEAR(return_date) <= 2005;
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
