## SQL

### DDL -Data Definition Language ( CREATE, ALTER, DROP, TRUNCATE )
*  DDL - Create products - ( https://codespace.app/s/create_products.sql-VolejxybjN )

### DML - Data Manipulation Language ( Insert/Update/Delete )
*  DML - Create products - ( https://codespace.app/s/create_products.sql-VolejxybjN )

### Constraints ( NOT NULL, UNIQUE, PRIMARY KEY, FOREIGN KEY, CHECK, DEFAULT )
* NOT NULL - Ensures that a column cannot have a NULL value
* UNIQUE - Values should not be duplicated. Unique can allow one NULL value. 
* PRIMARY KEY - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
* FOREIGN KEY - A foreign key matches the primary key field of another table. It means a foreign key field in one table refers to the primary key field of the other table.
* CHECK - it will allow only certain values for this column. e.g: gender in ('M','F')
* DEFAULT - Sets a default value for a column if no value is specified


### Aggregate Functions
*  Aggregate functions ( https://codespace.app/s/products.sql-WpmbkyJezJ )
*  Aggregate functions - Employees Salary Data ( https://codespace.app/s/aggregate_functions.sql-Oy5eV1zdEP)

### Sorting
*  Sorting -ascending,desending ( https://codespace.app/s/menus.sql-OpnelzjbKB )


## Joins
* To fetch data from 2 or more tables

##### Types of Join
* Inner Join
* Outer Join - Left / Right / Outer
* Self Join


#####  INNER JOIN

```sql
SELECT * FROM naresh_eventapp_users;

SELECT * FROM naresh_eventapp_events;

SELECT * FROM naresh_eventapp_registrations;

SELECT * FROM naresh_eventapp_users AS u
INNER JOIN naresh_eventapp_registrations AS r
ON u.id = r.user_id;
```

##### OUTER JOIN

```sql
SELECT * FROM naresh_eventapp_users AS u
LEFT OUTER JOIN naresh_eventapp_registrations AS r
ON u.id = r.user_id;

SELECT * FROM naresh_eventapp_events AS e
LEFT OUTER JOIN naresh_eventapp_registrations AS r
ON e.id = r.event_id;
```


