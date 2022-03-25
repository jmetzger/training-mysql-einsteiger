# Group By and Having Examples 

## What does it do ?

```
Group By aggregates data (data sets) 
Example: So if something appears multiple times, e.g a first name, 
it will only appears once. 

```

## Example GROUP BY 

```
SELECT last_name,COUNT(last_name) as cnt FROM actor GROUP BY last_name 
```

## Example 1 GROUP BY 

```
-- Ich möchte alle Schauspieler die mit dem nachnamen A anfangen 
```

## Exercise 

```
DB: sakila
Table: film  

Gruppiere alle filme nach rental_rate und gibt die jeweilige anzahl aus 
d.h. 
z.B. (wert nicht korrekt - weil nicht überprüft 

preis. anzahl 
0.99.  4 
2.99.  50 

```


## What does HAVING do 

```
Step 1: 
First MySQL reads all the data based on WHERE 

Step 2: 
Then it aggregates the data (GROUP BY) and filters it by HAVING 
```

## Example Having 


  * Simple: WHERE for GroupBy (because where does not work here)
  * Example 

```
SELECT last_name, COUNT(last_name) 
FROM sakila.actor
GROUP BY last_name
HAVING count(last_name) > 2
```
 
## Exercise 

```
Gruppiere alle actor 
o mit nachname, und anzahl nachname (felder die wir ausgeben) 
o Gebe nur die actor aus, deren nachname mit J anfängt


```
