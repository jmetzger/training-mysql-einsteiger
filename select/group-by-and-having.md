# Group By and Having Examples 

## What does it do ?

```
Group By aggregates data (data sets) 
Example: So if something appears multiple times, e.g a first name, 
it will only appears once. 

```

## Syntax 

```
SELECT .. FROM .. WHERE .. GROUP BY .. HAVING .. ORDER BY .. LIMIT
```

## Example GROUP BY 

```
SELECT last_name,COUNT(last_name) as cnt FROM actor GROUP BY last_name;
```

## Exercise 

```
-- DB: sakila
-- Table: film  

-- Gruppiere alle filme nach rental_rate und gibt die jeweilige anzahl aus 
-- d.h. 
-- z.B. 
-- Preis Anzahl
-- 4.99	336
-- 2.99	323
-- 0.99	341

```


## What does HAVING do 

```
Step 1: 
First MySQL reads all the data based on WHERE 

Step 2: 
Then it aggregates the data (GROUP BY) and filters it by HAVING 
```

## Example Having (Simple) 


  * Simple: WHERE for GroupBy (because where does not work here)
  * Example 

```
SELECT last_name, COUNT(last_name) 
FROM sakila.actor
GROUP BY last_name
HAVING count(last_name) > 2
```

## Example Having (a bit more complicated) 

```
# Step 1: Get all data wuth last_name like 'W%'
# Step 2: Group by last_name 
# Step 3: Only return dataset where count(last_name) --> aggregated data (HAVING) = 2 

select last_name,count(last_name) from actor where last_name like 'W%' group by last_name having count(last_name) = 2;
```


## Exercise 

```
Gruppiere alle actor 
o mit nachname, und anzahl nachname (felder die wir ausgeben) 
o Gebe nur die actor aus, deren nachname mit J anfängt


```
