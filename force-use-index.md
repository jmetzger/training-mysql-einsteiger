# Force use of index 

```
EXPLAIN SELECT Name,CountryCode FROM City FORCE INDEX (Name)
WHERE name>="A" and CountryCode >="A";

```

```
EXPLAIN SELECT Name,CountryCode FROM City USE INDEX (Name)
WHERE name>="A" and CountryCode >="A";

```
