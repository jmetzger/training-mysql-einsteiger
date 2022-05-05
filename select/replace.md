# REPLACE 

## Beispiel 

```

SELECT REPLACE('Hallo Weltenbummler Weltenentdecker','Welt','Erd');
SELECT REPLACE('Jones','o','e');

select first_name,'=>' as ' wird zu : ', replace(first_name,'CHRISTIAN','PETER') from actor where first_name like 'C%';

```

## Beispiel (Erweitert) 

```
select first_name,'wird zu:',replace(first_name,'CHRISTIAN','PETER') as modified from actor where replace(first_name,'CHRISTIAN','PETER') != first_name;

# performanter:
select first_name,'wird zu:',replace(first_name,'CHRISTIAN','PETER') as modified from actor where first_name = 'CHRISTIAN';

```


## Übung: 

```
Gebe all Adressen aus, bei denen die Adresse das Wort Drive enthält 
(vorne, hinten, Mitte)

Zeige folgende Felder an:

Feld1: address_id, 
Feld2: address, 
Feld3: (modifizierte Adresse: ersetze Drive -> Weg) als neue_adresse ausgeben

Hint: replace() 

```


## Übung (hat nix mit dem Thema zu tun) 

```
-- Db: sakila
-- table: film 

-- Lese alle replacement_cost aus (Feld 1), (Feld 2:) multipliziere diese mit 2 ( * 2 ) und Ersetze das Decimaltrennzeichen "." -> durch. "," 
-- Beispiel 

-- 2.99  5,98 



```


## Reference: 

  * https://www.w3schools.com/sql/func_mysql_replace.asp
