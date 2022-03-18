# Lock tables 

```
# Session 1
use sakila;
-- nobody else can read or write 
LOCK TABLES actor WRITE; 
```

```
# Session 2
show open tables where in_use like 1;
+----------+------------+--------+-------------+
| Database | Table      | In_use | Name_locked |
+----------+------------+--------+-------------+
| sakila   | actor      |      1 |           0 |
| sakila   | film_actor |      1 |           0 |
+----------+------------+--------+-------------+
2 rows in set (0.002 sec)

-- will hang till locks are unlocked 
INSERT INTO actor (first_name,last_name) values ('Josy','McCosy');
```
```
# Session 1
mysql> UNLOCK TABLES 

```

```
# Session 2
-- INSERT is written now

-- no output for show open tables if only these are locked 
show open tables where in_use like 1;

```

