# Unterschiede Hochkommas (einfache, doppelte) bei MySQK/Mariadb

## MySQL 

``` 
Hochkommas werden nur bei der Abfrage des Wertes verwendet, z.B 

select * from actor where last_name like 'A%'
# das ist das gleiche wie:
select * from actor where last_name like "A%"

```

## MySQL - Wann nehme ich einfache, wann doppelte ? 

```
# z.B. wenn ich ein Hochkomma in der Abfrage brauche, z.B
# damit besser lesbar für Admin/Entwickler 
select * from actor where last_name like "O'Connor"  
# Alternativ geht auch:
# Verfahren: Escapen 
select * from actor where last_name like 'O\'Connor'
```

# Oracle:

```
# Für Feldname und Ausgabe Feldname (Alias) Doppelte hochkommas.
# z.B 
# Hier immer das doppelte Hochkomma, weil es um den Identifier/Bezeichner geht 
SELECT  'Hello, world!'    AS "My Greeting"

## Für String und Date - Werte einfache Hochkommas
select * from actor where last_name like 'A%'


```
