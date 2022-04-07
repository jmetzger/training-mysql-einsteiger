# Beispiel - Query mit Variablen 

```
# IN VARIABLE SCHREIBEN
# Geht aber nur, wenn wir genau ein Ergebnis haben 
select count(*) into @howmany from actor where last_name like 'W%' 
order by last_name desc, first_name;
-- select @howmany

select first_name,last_name,@howmany from actor where last_name like 'W%' 
order by last_name desc, first_name;

```
