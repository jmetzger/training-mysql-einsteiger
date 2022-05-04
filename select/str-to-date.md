# String in Date(Mysql) umwandeln 

## Beispiel: 

```
# Das Ziel ist immer das bekannte Format 
# YYYY-MM-DD, aber das macht selbständig unter Haube,
# Wenn ich ihm sage, wie mein Ursprungsformat aussieht 

SELECT STR_TO_DATE("August 10 2017", "%M %d %Y");

```

## Übung 

```
Wandle das Datum in ein MYSQL-Datumsformat um mit STR_TO_DATE 
12.04.2022 

```


## Referenz:

 * https://www.w3schools.com/sql/func_mysql_str_to_date.asp
