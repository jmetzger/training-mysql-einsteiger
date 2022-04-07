# Beispiel Limit (combined with order by)

## What does it do ? 

```
From your results of your query only shows a subset

```

## Beispiel 

```
# Eine Zahl: d.h. beginnend ab 0. Datensatz (Datensatz Numero 1) und 3 Ergebnisse 
SELECT * FROM actor ORDER BY last_name DESC LIMIT 3;

# Beginne mit Datensatz 3 und dann 10 Ergebnisse.
SELECT * FROM actor WHERE last_name like 'W%' ORDER BY last_name DESC, first_name LIMIT 2,10;

```


## Übung 

```
1. Zeige von den Filmen (sakila.film) die teuersten (rental_rate) zuerst, davon 

Variante 1:
- Zeige die ersten 20 

Variante 2: Zeige 10 ab dem 11. Film 

```

