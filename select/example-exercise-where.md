# Example / Exercise for SELECT ... FROM ... WHERE 

## Example (Simple)

```
SELECT * FROM actor WHERE last_name = 'AKROYD' or last_name = 'GABLE';

```

## Example (mit Klammern) 

```
SELECT * FROM actor WHERE (last_name = 'Akroyd' and first_name = 'Christian') or (last_name = 'Gable' and first_name = 'Christian');
```

## Übung 

```
* Alle Datensätze aus actor anzeigen bei denen der Nachname Akroyd oder der Vorname Christian ist.


```
