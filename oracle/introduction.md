# Introduction to Oracle mode 

## Walkthrough 

```
set sql_mode = oracle -- writing it small works, but capital letters too 
select @@sql_mode;
delimiter /
CREATE DATABASE onboarding /
use onboarding / 

-- now create some table already with oracle data types 
CREATE TABLE employees (
   id INT(11) unsigned NOT NULL AUTO_INCREMENT,
   first_name VARCHAR2(200) NOT NULL,
   last_name VARCHAR2(200) NOT NULL,
   department CHAR(3) NOT NULL,
   position_level INT(1) NOT NULL,
   PRIMARY KEY(id)
);   

CREATE TABLE tasks (
   id INT(11) unsigned NOT NULL AUTO_INCREMENT,
   emp_id INT(11) unsigned NOT NULL,
   `description` VARCHAR2(200) NOT NULL,
   completed BOOLEAN NOT NULL DEFAULT 0,
   PRIMARY KEY(id),
   CONSTRAINT `fk_emp` FOREIGN KEY (emp_id) REFERENCES employees(id) ON 
   DELETE CASCADE ON UPDATE CASCADE
);/

show columns from tasks /  -- automatically converted 
+-------------+------------------+------+-----+---------+----------------+
| Field       | Type             | Null | Key | Default | Extra          |
+-------------+------------------+------+-----+---------+----------------+
| id          | int(11) unsigned | NO   | PRI | NULL    | auto_increment |
| emp_id      | int(11) unsigned | NO   | MUL | NULL    |                |
| description | varchar(200)     | NO   |     | NULL    |                |
| completed   | tinyint(1)       | NO   |     | 0       |                |
+-------------+------------------+------+-----+---------+----------------+

```

## Walkthrough create procedure (ORACLE sql_mode) 

```
CREATE OR REPLACE PROCEDURE `add_employee` (fname IN VARCHAR2, lname IN VARCHAR2, dept IN VARCHAR2, pos_level IN INTEGER ) AS 
BEGIN 
  IF ((fname <> '') && (lname <> '') && (dept <> '') && (pos_level > 0)) THEN 
       INSERT INTO employees (first_name,last_name,department,position_level)
       VALUES (fname, lname, dept, pos_level);
  ELSE 
     SELECT 'Insufficient data entered' AS WARNING;
  END IF;
EXCEPTION WHEN OTHERS THEN 
  SELECT 'exception ' || SQLCODE || ' ' || SQLERRM as EXCEPTION;
END;
/
```
