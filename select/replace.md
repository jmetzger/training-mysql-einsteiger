# REPLACE 

## Beispiel 

```
select first_name,'=>' as ' wird zu : ', replace(first_name,'CHRISTIAN','PETER') from actor where first_name like 'C%';

```

## Übung 

```
-- Db: sakila
-- table: film 

-- Lese alle replacement_cost aus (Feld 1), (Feld 2:) multipliziere diese mit 2 ( * 2 ) und Ersetze das Decimaltrennzeichen "." -> durch. "," 
-- Beispiel 

-- 2.99  5,98 



```


## Reference: 

  * https://www.w3schools.com/sql/func_mysql_replace.asp
