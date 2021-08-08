# Migrating put_line to MariaDB 

## You can migrate that one as follows (as package)  

```

DELIMITER /

CREATE OR REPLACE PACKAGE DBMS_OUTPUT AS
  PROCEDURE PUT_LINE(pString IN VARCHAR2);
END DBMS_OUTPUT;
/

CREATE OR REPLACE PACKAGE BODY DBMS_OUTPUT AS

  PROCEDURE PUT_LINE(pString IN VARCHAR2) AS
  BEGIN
    SELECT pString;
  END;
END DBMS_OUTPUT;
/

BEGIN
  DBMS_OUTPUT.PUT_LINE('Hello world from MariaDB DBMS_OUTPUT.PUT_LINE!');
END;
/

DELIMITER ;

```

## Reference:

  * https://docs.oracle.com/database/121/ARPLS/d_output.htm#ARPLS67327
