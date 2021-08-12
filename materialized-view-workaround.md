# Materialized View Workaround 

```
CREATE EVENT `tr_sakila_aggregate`
	ON SCHEDULE
		EVERY 1 MONTH STARTS '2021-08-12 11:20:00'
	ON COMPLETION PRESERVE
	ENABLE
	COMMENT 'Simulation Materialized View (Light)'
	DO BEGIN
   DROP TABLE IF EXISTS sakila_aggregate;
   CREATE TABLE sakila_aggregate AS SELECT actor_id,last_name,first_name FROM actor WHERE actor_id > 200;
END
```
