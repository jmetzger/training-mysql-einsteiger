# Recipe DBAL 

## Ausgangsituation 

```
DBAL erstellt query 
Query ist langsam 
Was tun ? 
```

## Steps 1+2  

```
## An das SQL-Statement rankommen. 


## 1. Analyse, warum ist Query langsam (kann ich von aussen etwas tun, um die Query zu beeinflussen ohne sie zu ändern 
explain <sql-statement>

## Sichtprüfung, fehlen Keys ?? 
# 
#explain select vendor_city,vendor_state from contributions where vendor_first_name like 'D%';
#+----+-------------+---------------+------------+------+---------------+------+---------+------+---------+----------+-------------+
#| id | select_type | table         | partitions | type | possible_keys | key  | key_len | ref  | rows    | filtered | Extra       |
#+----+-------------+---------------+------------+------+---------------+------+---------+------+---------+----------+-------------+
#|  1 | SIMPLE      | contributions | NULL       | ALL  | NULL          | NULL | NULL    | NULL | 2028402 |    11.11 | Using where |
#+----+-------------+---------------+------------+------+---------------+------+---------+------+---------+----------+-------------+
# Gibt es bei dem type einen Eintrag ALL. 

## Oder da ist ein key drin, aber der wird garnicht verändert.

## Index setzen 


```

## Step 3. 


```
Query analysieren -> Schritt debuggen. 
1) Links -> Rechts: Entweder von Links (sprich: was sind die ersten Daten, die ich brauche, welche dann, welche dann usw.) 

2) Rechts -> Links -> immer mehr wegnehmen und gucken, ob es schneller wird. 

```

## Step 4: 

```
index hint. 
```

## Step 5: Customized Query
