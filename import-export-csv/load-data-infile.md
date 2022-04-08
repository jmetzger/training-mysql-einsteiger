# Import Data with LOAD DATA INFILE 

## Example 

```
LOAD DATA INFILE 'c:/tmp/discounts_2.csv'
INTO TABLE discounts
FIELDS TERMINATED BY ',' ENCLOSED BY '"'
LINES TERMINATED BY '\n'
IGNORE 1 ROWS
(title,@expired_date,amount)
SET expired_date = STR_TO_DATE(@expired_date, '%m/%d/%Y');
```

## Adjusting to our example (MySQL 8, SQL executed in Workbench

```
Nachname, Vorname, Geburtsdatum
-- IGNORE 1 ROWS - simple does not use this first line 
Mustermann,Max,12.03.1976

SHOW VARIABLES LIKE 'secure_file_priv';

-- path must be like so: c:/.... (so no backslashes)
-- geburtsdatum is a field that must exist in structure / table 
LOAD DATA INFILE 'c:/ProgramData/MySQL/MySQL Server 8.0/Uploads/mysql - daten.csv'
INTO TABLE mitarbeiter 
FIELDS TERMINATED BY ',' ENCLOSED BY '"' 
LINES TERMINATED BY '\n'
IGNORE 1 ROWS 
(name, vorname, @geburtsdatum)
SET geburtsdatum = STR_TO_DATE(@geburtsdatum, '%d.%m.%Y');
```

## Reference: 

  * https://www.mysqltutorial.org/import-csv-file-mysql-table/
  * https://www.w3schools.com/sql/func_mysql_str_to_date.asp
