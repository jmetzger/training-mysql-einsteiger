# Examples string-functions 

## Example 

```
SELECT concat(title,' ',release_year,' ',description) as listeneintrag FROM film;
SELECT concat ('hans und lotta',' ','haben glueck');
SELECT concat('Ausgabe: ',substr(description,1,20)) as listeneintrag FROM film;
SELECT upper(substr(description,1,20)) from film;
SELECT upper(substr(description,1,20)) from film;
SELECT lower(substr(description,1,20)) from film; 

```

## Exercise 

```
-- Db: sakila
-- Tabelle: actor 
Gebt folgende Felder aus (in einer Abfrage) 

o last_name gross geschrieben 
o first_name klein geschrieben
o ausgabe mit zusammengeklebt last_name + ' ' + first_name (ohne +) 
o erste beiden Buchstaben vom Nachnamen. 

UPPER, LOWER, CONCAT, SUBSTR  



```

## Documentation 

  * https://dev.mysql.com/doc/refman/8.0/en/string-functions.html
