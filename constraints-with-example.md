# Foreign Key Constraints with example 

## Walkthrough 

### Step 1: Sample Table and data 

```
create table gadget_types(
    type_id int auto_increment,
    name varchar(100) not null,
    primary key(type_id)
);

insert into gadget_types(name)
values
    ('Entertainment'),
    ('Computing'),
    ('Communication'),
    ('Lifestyle'),
    ('Cameras');

create table gadgets(
    gadget_id int auto_increment,
    gadget_name varchar(100) not null,
    type_id int,
    primary key(gadget_id),
    constraint fk_type
    foreign key(type_id) 
        references gadget_types(type_id)
);
```

## Step 2: Insert data to gadgets 

```
insert into 
    gadgets(gadget_name,type_id)
values
    ('Amazon Kindle',1),
    ('Apple iPod',1),
    ('Audio Highway Listen Up',1),
    ('Apple iPad',2),
    ('MicroSD',2),
    ('Apple iPhone',3),
    ('BlackBerry 6210',3),
    ('Pager',3),
    ('Air Taser Model 34000',4),
    ('Credit Card',4),
    ('Zippo',4),
    ('Casio G-Shock DW-5000C',4),
    ('Nikon F',5),
    ('Canon EOS 5D Mark II',5);
```

## Step 3 - Try to delete 

```
delete from gadget_types 
where type_id = 1;


SQL Error (1451): Cannot delete or update a parent row: a foreign key constraint fails (`nation`.`gadgets`, CONSTRAINT `fk_type` FOREIGN KEY (`type_id`) REFERENCES `gadget_types` (`type_id`)) 
--> To delete a row from the gadget_types table, you need to remove all the referencing rows from the gadgets table first.
```

## Step 4 - Drop Contrains and set NULL Reference 

```
alter table gadgets
drop constraint fk_type;

alter table gadgets 
add constraint fk_type 
foreign key(type_id) 
    references gadget_types(type_id)
    on delete set null
    on update set null;

delete from gadget_types
where type_id = 1;

select * from gadgets;
--> As shown clearly from the output, the values in the type_id column of rows with type_id 1 from the gadgets table were set to null because of the on delete set null option.
```

## Step 5 - change id in gadget_types 

```
update gadget_types
set type_id = 20
where type_id = 2;

select * from gadgets;

--> The values in the type_id column of rows with type_id 2 from the gadgets table were set to null because of the on update set null option.
```

## Step 6 - remove orphans 

```
delete from gadgets
where type_id is null;
```

## Step 7 - cascade reference option 

```
-- Drop constraint 
alter table gadgets
drop constraint fk_type;

alter table gadgets 
add constraint fk_type 
foreign key(type_id) 
    references gadget_types(type_id)
    on delete cascade
    on update cascade;

delete from gadget_types
where type_id = 3;
--> MariaDB automatically deleted rows from the gadgets table whose type_id is 3 because of the on delete cascade action.

select * from gadgets;
```

## Step 8 - Update gadget_type id 4 to 40:

```
update gadget_types
set type_id = 40
where type_id = 4

--> MariaDB automatically updated rows from the gadgets table whose type_id is 4 to 40 because of the on update cascade action:
```

```
select * from gadgets;
--> Updated all references 
```

## Ref:

  * https://www.mariadbtutorial.com/mariadb-basics/mariadb-foreign-key/
