# Cheatsheet - Select 

## SELECT .. FROM .. WHERE .. ORDER BY .. LIMIT 

```
select * from actor;
select feld1,feld2,feld3 from actor;

-- Mit Feldalias für die Ausgabe
select feld1 as ueberschrift_ausgabe,feld as feldueberschrift from actor;
```

### WHERE 

```
-- WHERE feldname =/like  
select * from actor where last_name = 'AKROYD';
select * from actor where last_name like 'A%';
select * from actor where last_name like 'A%' and first_name like 'C%';
select * from actor where (last_name = 'Akroyd' and first_name = 'Christian') or (last_name = 'Gable' and first_name = 'Christian');

-- WHERE feldname IN / NOT IN 
SELECT * FROM actor WHERE first_name IN ('JOE','ED','JENNIFER');
SELECT * FROM actor WHERE last_name NOT IN ('AKROYD','JONES');

-- WHERE feldname < > <= >= BETWEEN 

SELECT * FROM actor where actor_id > 100 and actor_id < 150;
select * from actor where actor_id >= 10 and actor_id <= 50;
SELECT * FROM actor where actor_id between 100 and 150;

-- WHERE feldname IS NULL / IS NOT NULL 
SELECT * FROM rental WHERE return_date IS NOT NULL;
SELECT * FROM rental WHERE return_date IS NULL;

-- WHERE feldname <= '2022-01-02 10:00:01' (DATUM) 
SELECT * FROM sakila.payment WHERE payment_date > '2005-05-24 22:00:01' and payment_date < '2005-05-25 22:00:01'

```

### STRING-FUNKTIONEN 

```
SELECT concat(title,' ',release_year,' ',description) as listeneintrag FROM film;
SELECT upper(title) from film;
SELECT lower(title) from film;
SELECT lower(substr(description,1,20)) from film; 
```





```
-- Mit Bedingung und Sortierreihenfolge 
select FELD from TABELLE WHERE BEDINGUNG ORDER BY FELD1,FELD2
select first_name,last_name from actor where last_name like 'A%' order by first_name,last_name 

-- Nur Limit 
select FELD from tabelle limit 0,30; -- Ab Datensatz 1 der Ergebnismenge   
select * from actor limit 30 -- Ab Datensatz 

-- WHERE/ORDER BY/LIMIT 
SELECT feld FROM tabelle WHERE bedingung ORDER BY FELD1,FELD2 LIMIT 0,10 
SELECT feld FROM tabelle WHERE bedingung ORDER BY FELD1,FELD2 LIMIT 5,10 -- Ab dem 5. Datensatz der Ergebnismenge 
```


## Rechnen 

```
SELECT amount,1 as 'Preiserhoehung um',amount + 1 as preiserhoehung FROM payment;
```
