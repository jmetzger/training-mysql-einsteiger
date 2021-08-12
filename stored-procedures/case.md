# Case - Statement 

## Example with database insert 

```
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
	   SELEC'Bitte gebe einen First Name ein: ';
	   LEAVEain;
	END IF; 
	        
	IF last_me = ''
	THEN    
	   SELEC'Bitte gebe einen Last Name ein: ';
	   LEAVEain;
	END IF; 
	        
	CASE fam
    WHEN 'superstar' THEN 
	   SET sr_type='ST';
    WHEN 'megastar' THEN 
	   SET sr_type='MS';
	 WHEN 'sr' THEN
	   SET sr_type='S';  
	 ELSE   
	   SELEC'Als Star ist nur superstart,megastart oder star erlaubt'; 
	   LEAVEain;
   END CASE;
	        
	INSERT IO actor 
	  (startte,
	   endda,
		firste,
		last_,
		star_)
	VALUES (artdate,enddate,first_name,last_name,star_type);
	        
	SELECT CCAT ('Schauspieler ',first_name,' ',last_name,' 
           
END/       
DELIMITER ;


CALL addActor('2021-12-22','2021-12-31','Peter','Lausitz','megastar');


```


## Reference 

  * https://mariadb.com/kb/en/case-statement/
