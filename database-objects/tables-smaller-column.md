# Teststellung - Feld verkleinern 

```
ALTER TABLE actor ADD filme tinyint unsigned default 255;
-- Does not work 
-- UPDATE actor SET filme = 256  WHERE actor_id = 1;
-- ALTER TABLE actor MODIFY filme smallint unsigned default 256;
INSERT INTO actor (first_name,last_name) values ('Gaucho','Poncho');
INSERT INTO actor (first_name,last_name,filme) values ('Gauchina','Ponchina',32000);

-- Does not work 
ALTER TABLE actor MODIFY filme tinyint unsigned;
```
