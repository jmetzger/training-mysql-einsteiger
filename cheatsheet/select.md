# Cheatsheet - Select 

```
select * from actor;
select feld1,feld2,feld3 from actor;

-- Mit Bedingung 
select * from actor where last_name = 'AKROYD';
select * from actor where last_name like 'A%';
select * from actor where last_name like 'A%' and first_name like 'C%';

-- Mit Bedingung und Sortierreihenfolge 
select FELD from TABELLE WHERE BEDINGUNG ORDER BY FELD1,FELD2
select first_name,last_name from actor where last_name like 'A%' order by first_name,last_name 

-- Nur Limit 
select FELD from tabelle limit 0,30; -- Ab Datensatz 1 der Ergebnismenge   
select * from actor limit 30 -- Ab Datensatz 



```
