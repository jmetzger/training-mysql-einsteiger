# Tables 

## Show tables 

```
# within mysql>
# so on the command-line enter:
# mysql (as root) 
USE sakila 
SHOW TABLES 

-- or --

select * from information_schema.TABLES 
```

### Create table 

```
-- only if you want to create table in a completely new database 
create schema training; 
USE training
CREATE TABLE people (id INT NOT NULL AUTO_INCREMENT, name VARCHAR(20), PRIMARY KEY(id)); 
```

### Find out the structure of the table 

```
# you have to connect to db first with 
# mysql 
# within mysql>
describe people 
show create table people 
```

### Change table (Add field)  

```
--- We want to add a field before name 
ALTER TABLE people ADD first_name VARCHAR(10) BEFORE name;
```

### Modify a field in table (Change propery) 

```
ALTER TABLE people
	MODIFY COLUMN first_name VARCHAR(20);
```
