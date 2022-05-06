# Triggers - Example  

## Create the structure 

```
create table countries (
    country_id int auto_increment,
    name varchar(50) not null,
    primary key(country_id) 
);

INSERT INTO countries (name) values ('Germany'), ('Austria'); 

create table country_stats(
    country_id int,
    year int,
    population int,
    primary key (country_id, year),
    foreign key(country_id)
	references countries(country_id)
);

INSERT INTO country_stats (country_id, year, population) values (1,2020,100000);


create table population_logs(
    log_id int auto_increment,
    country_id int not null,
    year int not null,
    old_population int not null,
    new_population int not null,
    updated_at timestamp default current_timestamp,
    primary key(log_id)
);

```

## Create the trigger 

```
create trigger before_country_stats_update 
    before update on country_stats
    for each row
    insert into population_logs(
        country_id, 
        year, 
        old_population, 
        new_population
    )
    values(
        old.country_id,
        old.year,
        old.population,
        new.population
    );

```

## Create trigger (the same) but with BEGIN/END - Block 

```
delimiter //
create trigger before_country_stats_update 
    before update on country_stats
    for each row

    BEGIN
    SET @anfang = 1;
    insert into population_logs(
        country_id, 
        year, 
        old_population, 
        new_population
    )
    values(
        old.country_id,
        old.year,
        old.population,
        new.population
    );
    END//

```

## Run a test 

```
update 
    country_stats
set 
    population = 1352617399
where 
    country_id = 1 and 
    year = 2020;

-- what's the new result 

select * from population_logs;

```


## Exercise 

```
-- Database: training
CREATE DATABASE IF NOT EXISTS training; 
use training;

CREATE TABLE animals (id mediumint(9) 
NOT NULL AUTO_INCREMENT, 
name char(30) NOT NULL, 
PRIMARY KEY (`id`));

CREATE TABLE animal_count (animals int);

INSERT INTO animal_count (animals) VALUES(0);

CREATE TRIGGER increment_animal 
AFTER INSERT ON animals 
FOR EACH ROW 
UPDATE animal_count SET animal_count.animals = animal_count.animals+1;


-- Jetzt testen 
SELECT * FROM animal_count;
INSERT INTO animals (name) VALUES('aardvark');
INSERT INTO animals (name) VALUES('baboon');
SELECT * FROM animal_count;


-- Reference: 
-- https://mariadb.com/kb/en/trigger-overview/
```
