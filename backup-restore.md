# Backup und Restore 

## Unter Linux 
```
mysqldump sakila > /usr/src/sakila.sql
mysql sakila < /usr/src/sakila.sql
echo "show tables;" | mysql sakila;


#echo "create schema verleih;" | mysql
# oder
mysql -e 'create schema verleih'
mysql verleih < /usr/src/sakila.sql

```
# Unter Windows 

```
# mysqldump muss entweder in der %PATH% variablen stehen oder wir müssen 
# bin verzeichnis von mysql, sein, 
# vorher cmd.exe ausführen über Windows ausführen (oder Suchfeld cmd)  
mysqldump -uext -p -h 127.0.0.1 sakila  > C:\Users\Jochen Metzger\Documents\sakila.sql
```

## Alle Daten und Struktur sichern 

```
# Wichtig --events --routines -> sonst werden diese nicht gesichert. !!!! 
mysqldump --all-databases --events --routines > all-structure.sql
```




## Nur Struktur sichern 

```
mysqldump --no-data --all-databases --events --routines > all-structure.sql


```


## Nur daten pro Tabelle 

```
mysqldump --no-create-info sakila actor > sakila-actor-data.sql
```
