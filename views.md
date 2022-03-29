##### Views

```sql
CREATE TABLE users
( id INT PRIMARY KEY AUTO_INCREMENT,
NAME VARCHAR(100) NOT NULL,
email VARCHAR(100) NOT NULL,
PASSWORD VARCHAR(100) NOT NULL,
UNIQUE(email)
);
```

```sql
SELECT * FROM users;
```

```sql
INSERT INTO users ( NAME,email,PASSWORD)
VALUES ( 'Naresh','n@gmail.com', 'pass123');
```

```sql
CREATE OR REPLACE VIEW user_vw AS 
SELECT id,NAME,email FROM users;
````

```sql
SELECT * FROM user_vw; 
```


##### Drop View

```sql
DROP VIEW user_vw;
```
