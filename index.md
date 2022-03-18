## Index

* **Indexes** are used to find rows with specific column values quickly. 
* Without an index, MySQL must begin with the first row and then read through the entire table to find the relevant rows. The larger the table, the more this costs. 
* If the table has an index for the columns in question, MySQL can quickly determine the position to seek to in the middle of the data file without having to look at all the data. 
* This is much faster than reading every row sequentially.
* Most MySQL indexes (PRIMARY KEY, UNIQUE, INDEX, and FULLTEXT) are stored in **B-trees**.


##### Task 1: Create an Index
```sql
CREATE INDEX users_email_idx ON 
naresh_eventapp_users(email);
```

##### Task 2: Search by Email (  Since index is created for "email" column, search results will be faster )

```sql
SELECT * FROM naresh_eventapp_users WHERE email='siva@gmail.com';
```

##### Task 3: Drop an index
```sql
ALTER TABLE naresh_eventapp_users DROP INDEX users_email_idx;
```

##### Reference:
* https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html
