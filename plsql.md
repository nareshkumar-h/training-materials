## PLSQL

* PL/SQL is a combination of SQL along with the procedural features of programming languages ( IF,ELSE,FOR etc)

##### Concepts
* Functions
* Procedures
* Triggers


##### Functions

```sql
DELIMITER $$

CREATE  FUNCTION `calculate`(num1 INT, num2 INT )
    RETURNS INT
    BEGIN
        DECLARE v_result INT;
        SET v_result := num1 + num2;
	RETURN v_result;
    END$$

DELIMITER ;
```

* Test
```
SELECT calculate(2,3);

SELECT calculate(3,3);
```

##### Procedure 
* IN/OUT/INOUT Parameters

```sql
DELIMITER $$

CREATE    
    PROCEDURE `pr_activate_account`(IN i_email VARCHAR(100), OUT i_result  VARCHAR(100) )    
    BEGIN
        
        IF ( i_email IS NULL ) THEN
		SET i_result = 'Email Id is Empty';  	
	ELSE	        
	   UPDATE naresh_eventapp_users SET ACTIVE=1 WHERE email = i_email;	  
		SET i_result = 'SUCCESS';
        END IF;
	
    END$$

DELIMITER ;
```

* Test Case 01: Valid Email Id
```sql
CALL pr_activate_account('nareshkumarh@live.com',@result);
SELECT @result;
```
* Output: SUCCESS

* Test Case 02: Input Email as Null
```sql
CALL pr_activate_account(NULL,@result);
SELECT @result;
```
* Output: Email Id is Empty
