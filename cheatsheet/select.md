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

### WHERE -> DATUMSABFRAGE (NUR BEI WENIG DATEN < 1.000.0000 als Richtwert) 

```
-- möglichst im where keine Funktion für Feldname
select YEAR(return_date),return_date from rental where YEAR(return_date) <= 2005; 
```

## DATUMS-FUNKTIONEN

```
select YEAR(return_date),MONTH(return_date),DAY(return_date) from rental;
SELECT date_format(last_update,'%M %Y') as meindatum FROM actor;

-- Unix timestamp 
SELECT unix_timestamp('2022-01-04');
SELECT last_update,unix_timestamp(last_update) from actor;
SELECT unix_timestamp(); -- aktuelles Datum als unix timestamp 
```

### STRING-FUNKTIONEN 

```
SELECT concat(title,' ',release_year,' ',description) as listeneintrag FROM film;
SELECT upper(title) from film;
SELECT lower(title) from film;
SELECT lower(substr(description,1,20)) from film; 
```

### ZÄHLEN / STATISTIK 

```
SELECT count(*) as howmany FROM actor; 
select count(*) from actor where last_name like 'D%';

-- Höchste Kosten (MAX), Geringste Kosten (MIN) anzeigen
SELECT MAX(replacement_cost) as am_teuersten,MIN(replacement_cost) FROM sakila.film;
```

## SORTIERUNG / LIMIT 

```
-- WHERE/ORDER BY 
select FELD from TABELLE WHERE BEDINGUNG ORDER BY FELD1,FELD2
select first_name,last_name from actor where last_name like 'A%' order by first_name,last_name 

-- LIMIT
select FELD from tabelle limit 0,30; -- Ab Datensatz 1 der Ergebnismenge   
select * from actor limit 30 -- Ab Datensatz 

-- WHERE/ORDER BY/LIMIT 
SELECT feld FROM tabelle WHERE bedingung ORDER BY FELD1,FELD2 LIMIT 0,10 
SELECT feld FROM tabelle WHERE bedingung ORDER BY FELD1,FELD2 LIMIT 5,10 -- Ab dem 6. Datensatz der Ergebnismenge 
```


## RECHNEN / RUNDEN 

```
SELECT amount,1 as 'Preiserhoehung um',amount + 1 as preiserhoehung FROM payment;

-- Kaufmännisch runden 
SELECT ROUND(1.56,1);
-- Abschneiden
SELECT TRUNCATE(1.56,1);
-- FLOOR() -> abrunden zum nächsten Integer  
SELECT FLOOR(12.56);
-- CEIL() - Aufrunden zum nächsten Integer 
SELECT CEIL(12.3);
```

## GROUP (GRUPPIEREN) - SELECT .. FROM .. WHERE .. GROUP BY .. HAVING .. ORDER BY .. LIMIT 

```
SELECT last_name,COUNT(last_name) as cnt FROM actor GROUP BY last_name;

-- Nachnamen Gruppieren und alle Nachnamen anzeigen die mehr als 2 Mal vorkommen 
SELECT last_name, COUNT(last_name) 
FROM sakila.actor
GROUP BY last_name
HAVING count(last_name) > 2
```

## JOINS - SELECT .. FROM .. JOIN ... ON ... JOIN ... ON ... WHERE .. GROUP BY .. HAVING .. ORDER BY .. LIMIT 

```
-- JOIN über 2 Tabellen 
SELECT a.*,c.* FROM customer c JOIN address a ON c.address_id = a.address_id; 
SELECT c.first_name,c.last_name,a.postal_code FROM customer c JOIN address a ON c.address_id = a.address_id; 

-- JOIN über 3 Tabellen 

-- Schritt 1: 2 Tabellen 
SELECT a.last_name,fa.film_id FROM actor a JOIN film_actor fa ON a.actor_id = fa.actor_id;

-- Schritt 2: auf 3 Tabellen erweitern 
SELECT a.last_name,fa.film_id,f.title 
FROM actor a 
JOIN film_actor fa 
ON a.actor_id = fa.actor_id
JOIN film f 
ON fa.film_id = f.film_id;

```
