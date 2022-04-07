# CHAR_LENGTH and LENGTH 

## Was ist der Unterschied ? 

  * CHAR_LENGTH - zeigt Anzahl der Zeichen an
  * LENGTH - Anzahl der Bytes 


# Beispiel actor 

```
select last_name, length(last_name),char_length(last_name) from actor;

```


## Exercise 

```
-- Db: sakila  
-- Table: actor 

Übung: 

Bitte vorname und nachname als zusammengesetzten String aus (durch Leerzeichen getrennt),
z.B. PETERSON,DAN und gib als 2. Feld die Länge des Strings aus. 
z.B. PETERSON,DAN 12  

HINT: Verwende zum Zusammenkleben möglich CONCAT_WS 
```




