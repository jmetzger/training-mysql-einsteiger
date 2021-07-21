# Select mit Like 

```
# Alle Datensätze, die mit J anfangen 
select first_name,last_name from actor where last_name like 'j%'
# mit ausgabe zusätzlichem String 
select first_name,last_name,' ist der/die Beste' as bewertung from actor where last_name like 'j%'

```
