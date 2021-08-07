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
