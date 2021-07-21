# Select mit Like 

## Hintergrund Platzhalter '%' und '_' 

  * https://elearn.inf.tu-dresden.de/sqlkurs/lektion01/01_07_03_einschr_like.html

## Name fängt mit J an 

```
# Alle Datensätze, die mit J anfangen 
select first_name,last_name from actor where last_name like 'j%'
# mit ausgabe zusätzlichem String 
select first_name,last_name,' ist der/die Beste' as bewertung from actor where last_name like 'j%'

```

## Name hört mit n auf 

```
select first_name,last_name from actor where last_name like '%n'
```

## Name beinhaltet 'q'  

```
select first_name,last_name from actor where last_name like '%q%'
```
