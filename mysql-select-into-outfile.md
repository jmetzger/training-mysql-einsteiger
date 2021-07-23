# Export to file (csv) 

```
-- zeig mir das Datenverzeichnis
SELECT @@datadir;
-- der secure-path - nur dort darf hin exportiert werden 
show variables like '%secure%';

SELECT actor_id,last_name 
INTO OUTFILE 'C:\\ProgramData\\MySQL\\MySQL Server 8.0\\Uploads\\result.txt'
FROM actor;

```
