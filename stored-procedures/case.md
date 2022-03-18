# Case - Statement 

## Example with database insert 

```
use sakil;
ALTER TABLE actor 

DELIMITER /
CREATE OR REPLACE PROCEDURE addActor (IN startdate DATE, 
                                      IN enddate DATE, 
                                      IN first_name VARCHAR(45), 
				      IN last_name VARCHAR(45),
				      IN fame VARCHAR(9))
main: BEGIN
           
   DECLARE star_type CHAR(2);
           
   IF startdate > enddate 
   THEN    
      SELECT 'Das Startdaum liegt nach dem Enddatum';
      LEAVE main;
   END IF; 
	        
   IF firstame = ''
   THEN    
      SELECT 'Bitte gebe einen First Name ein: ';
      LEAVE main;
   END IF; 
	        
   IF last_name = ''
   THEN    
      SELECT 'Bitte gebe einen Last Name ein: ';
      LEAVE main;
   END IF; 
	        
   CASE fame
    
     WHEN 'superstar' THEN 
       SET star_type='ST';
     WHEN 'megastar' THEN 
       SET star_type='MS';
     WHEN 'star' THEN
       SET star_type='S';  
     ELSE   
       SELECT 'Als Star ist nur superstar,megastart oder star erlaubt'; 
       LEAVE main;
   END CASE;
	        
   INSERT INTO actor (startdate,enddate,first_name,last_name,star_type)
   VALUES (startdate,enddate,first_name,last_name,star_type);
	        
   SELECT CONCAT ('Schauspieler ',first_name,' ',last_name,' ',fame);
           
END/       
DELIMITER ;


CALL addActor('2021-12-22','2021-12-31','Peter','Lausitz','megastar');


```


## Reference 

  * https://mariadb.com/kb/en/case-statement/
