# Group By and Having Examples 

## What does it do ?

```
Group By aggregates dates. 
Example: So if something appears multiple times, e.g a first name, 
it will only appears once. 

```

## Example GROUP BY 

```

SELECT last_name,COUNT(last_name) as cnt FROM actor GROUP BY last_name 

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
SELECT last_name, COUNT(*) 
FROM sakila.actor
GROUP BY last_name
HAVING count(last_name) > 2
```
 