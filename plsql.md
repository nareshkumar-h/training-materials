## PLSQL

* PL/SQL is a combination of SQL along with the procedural features of programming languages ( IF,ELSE,FOR etc)

##### Concepts
* Functions
* Procedures
* Triggers


##### Functions

```sql
DELIMITER $$

CREATE  FUNCTION `revature_training_db`.`calculate`(num1 INT, num2 INT )
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

