# Group by - simple example 

```
# Variante 1 
SELECT last_name,COUNT(last_name) as cnt FROM actor GROUP BY last_name 

# Variante 2: ohne Group - akroyd zählen -> geht nur bei einem Namen 
SELECT last_name,COUNT(last_name) as cnt FROM actor WHERE last_name = 'AKROYD' 

# Das ist falsch - weil mehrere Namen, Ausgabe nur eine Zeile  
SELECT last_name,COUNT(last_name) as cnt FROM actor WHERE last_name = 'AKROYD' or last_name = 'ALLEN' 

# Variante 2a (Erst Daten holen - 6 Datensätze, dann aggregieren (group by) 
# Für grosse Datenmengen besser ! 
SELECT last_name,COUNT(last_name) as cnt FROM actor WHERE last_name = 'AKROYD' or last_name = 'ALLEN' GROUP BY last_name
# Variante 2b (Alle Daten holen - 200 Datensätze, dann alles aggregieren) 
SELECT last_name,COUNT(last_name) as cnt FROM actor GROUP BY last_name HAVING last_name = 'AKROYD' or last_name = 'ALLEN'

```
