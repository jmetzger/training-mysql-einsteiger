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

## Adjusting to our example 

```
Nachname, Vorname, Geburtsdatum
# IGNORE 1 ROWS - simple does not use this first line 
Mustermann,Max,12.03.1976

LOAD DATA INFILE 'c:/Desktop/import/data - mysql.csv'
INTO TABLE mitarbeiter 
FIELDS TERMINATED BY ',' ENCLOSED BY '"' 
LINES TERMINATED BY '\n'
IGNORE 1 ROWS 
(name, vorname, @dob)
SET dob = STR_TO_DATE(@dob, '%d.%m.%Y');
```
