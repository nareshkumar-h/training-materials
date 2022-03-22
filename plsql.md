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

##### Procedure - Example 1

```sql
DELIMITER $$

CREATE
    PROCEDURE `revature_training_db`.`pr_create_account`(IN i_name VARCHAR(100), IN i_email VARCHAR(100), IN i_password VARCHAR(100), IN i_college_name VARCHAR(100), OUT i_message VARCHAR(100))
    BEGIN

	INSERT INTO naresh_eventapp_users
	(NAME,email,PASSWORD,college_name) 
	VALUES ( i_name,i_email, i_password,i_college_name);
	SET i_message := 'SUCCESS';
    END$$

DELIMITER ;
```

* Test the procedure
```sql
CALL pr_create_account('siva','siva@gmail.com','pass1234','LVEC',@message);
SELECT @message;
```

* Output: SUCCESS

##### Procedure - Example 2
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



##### CallableStatement => to call procedure

* Callable Statement to call procedure  ( https://codespace.app/s/testprocedure.java-k8mepOQdMy )
