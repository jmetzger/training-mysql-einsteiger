# Examples string-functions 

## Example 1

```
# Zusammenkleben 
SELECT concat(title,' ',release_year,' ',description) as listeneintrag FROM film;
SELECT concat ('hans und lotta',' ','haben glueck');

# Teilstring 
SELECT substr('Zusammengesetztes Wort',1,2);

# Kleinschreibung 
select lower('SONNENSCHEIN');
select lower(last_name) from actor;

# Grossschreibung
select upper('klein');

# Kombiniert 
SELECT concat('Ausgabe: ',substr(description,1,20)) as listeneintrag FROM film;
SELECT upper(substr(description,1,20)) from film;
SELECT lower(substr(description,1,20)) from film; 

```

## Example 2 

```
select 'test' ' ist gut ' 'verlaufen';

```

## Exercise 

```
-- Db: sakila
-- Tabelle: actor 
Gebt folgende Felder aus (in einer Abfrage) 

o Ausgabe Spalte 1: last_name gross geschrieben 
o Ausgabe Spalte 2: first_name klein geschrieben
o Ausgabe Spalte 3: ausgabe mit zusammengeklebt last_name + ' ' + first_name (ohne +) 
o Ausgabe Spalte 4: erste beiden Buchstaben vom Nachnamen. 

HINT: -> UPPER, LOWER, CONCAT, SUBSTR  



```

## Documentation 

  * https://dev.mysql.com/doc/refman/8.0/en/string-functions.html
  * https://www.w3schools.com/sql/func_mysql_concat.asp
  * https://www.mysqltutorial.org/sql-concat-in-mysql.aspx
