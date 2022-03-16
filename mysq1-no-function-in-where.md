# No function in where !! 

```
# Bad for performance 

# Bad
# Because, system has to read each row from db, to use function first
# and then compare -> no index used 
select * from actor WHERE UPPER(last_name) like ('B%');

MariaDB [sakila]> explain select * from actor where upper(last_name) like 'A%';
+------+-------------+-------+------+---------------+------+---------+------+------+-------------+
| id   | select_type | table | type | possible_keys | key  | key_len | ref  | rows | Extra       |
+------+-------------+-------+------+---------------+------+---------+------+------+-------------+
|    1 | SIMPLE      | actor | ALL  | NULL          | NULL | NULL    | NULL | 202  | Using where |
+------+-------------+-------+------+---------------+------+---------+------+------+-------------+
1 row in set (0.000 sec)


# Good 
select * from actor WHERE last_name like UPPER('b%')


```

## How to solve it, if you want to use upper 

```
-- Step 1: Create a virtual column 
ALTER TABLE actor ADD COLUMN last_name_upper VARCHAR(45) AS (UPPER(last_name)) PERSISTENT;
ALTER TABLE actor ADD COLUMN last_name_lower VARCHAR(45) AS (LOWER(last_name)) PERSISTENT;

-- Step 2: Create Index on last_name_lower 
CREATE INDEX idx_actor_last_name_lower ON actor (last_name_lower);

```


## Referenz:

  * https://mariadb.com/kb/en/generated-columns/
