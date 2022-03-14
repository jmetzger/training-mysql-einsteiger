# Praktisches Beispiel - Insert 

# Beispiel 
```
INSERT INTO actor (first_name,last_name) values ('Joe','Manchos');
```

# Nicht-optimales Beispiel

```
# Problem die Spaltenzahl und die Spaltennamen können sich ändern
# dann geht das insert nicht mehr 

## 2022-01-01 
## Folgende Felder
## first_name
## last_name 

## 2022-03-01 
## Folgender Felder nach Strukturänderung 
## first_name 
## middle_name
## last_name 

INSERT INTO actor values ('Joe','Manchos');

```


# Erweitertes Insert
```
# Mehrere Wertepaare einfügen - geht schneller als einzelne Inserts 
INSERT INTO actor (first_name,last_name) values ('Joe','Metzgeros'),('Hans','Mustermann');
```

# Referenz

  * https://www.w3schools.com/sql/sql_insert.asp
