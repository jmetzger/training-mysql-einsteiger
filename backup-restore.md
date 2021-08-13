# Backup und Restore 

```
mysqldump sakila > /usr/src/sakila.sql
mysql sakila < /usr/src/sakila.sql
echo "show tables;" | mysql sakila;


echo "create schema verleih;" | mysql
mysql verleih < /usr/src/sakila.sql

```
