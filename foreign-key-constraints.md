# Foreign Key constraints - Example 

```
# Walkthrough 
create filmcopy as select * from film:
set foreign_key_checks = 0;
trunate film 
set foreign_key_checks = 1
alter table actorcopy add constraint (fk_language_id) references language (language_id) 

# Test it 
# language.language_id needs to have an index 
delete from language where language_id = 1
```

