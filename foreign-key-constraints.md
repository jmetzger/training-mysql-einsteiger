# Foreign Key constraints - Example 

```
# Walkthrough 
use sakila;
create table filmcopy as select * from film;
set foreign_key_checks = 0;
truncate film;
set foreign_key_checks = 1
# WRONG
#alter table filmcopy add constraint fk_language_id references language (language_id) 
alter table filmcopy add foreign key (language_id) references language (language_id);

# Test it 
# language.language_id needs to have an index 
delete from language where language_id = 1
```

