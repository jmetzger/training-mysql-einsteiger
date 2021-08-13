# Zeichensatz umstellen.

## Example (if it works it is great) 

```
-- Do this for every table 
ALTER TABLE Tabellenname CONVERT TO CHARACTER SET utf8 COLLATE utf8_general_ci
ALTER DATABASE Datenbankname DEFAULT CHARACTER SET  utf8 COLLATE utf8_general_ci
```

## Ref. with problems (specific project) 

  * https://fromdual.com/mariadb-and-mysql-character-set-conversion
