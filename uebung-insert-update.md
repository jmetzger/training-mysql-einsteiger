# Übung Update/Insert 

```
1. In einer Anweisung alle Datensätze ändern in denen der erste Name JUDY und der Nachname DEAN ist -> dort Vorname in JAMES ändern.

UPDATE actor SET first_name = 'JAMES' where last_name='DEAN' and first_name='JUDY';


2. In einem SQL-Statement 2 neue Datensätze einfügnen. 1. Mann, Josef  2. Mannheim, Martha 

INSERT INTO actor (first_name, last_name) values ('Mann','Josef'), ('Mannheim','Martha');
```
