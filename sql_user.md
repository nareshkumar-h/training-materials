##### Data Controlling Language (DCL)


##### Create User
```sql
CREATE USER naresh IDENTIFIED WITH mysql_native_password BY 'naresh';
```

##### Drop User
```sql
DROP USER naresh;
```

##### Create Database

```sql
CREATE DATABASE naresh_db;
````


##### Provide Permissions to user using GRANT command

* All Privileges
```sql
GRANT ALL PRIVILEGES ON naresh_db.* TO 'naresh'@'%' ;
```

##### Provide specific permission to user

* Specific Privilege
```sql
GRANT CREATE,SELECT ON naresh_db.* TO 'naresh'@'%' WITH GRANT OPTION;
```

#### Remove Permission from user

* Remove all privileges

```sql
REVOKE ALL PRIVILEGES, GRANT OPTION FROM 'naresh';
```
