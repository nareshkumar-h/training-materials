## Joins
* To fetch data from more than 1 table.

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


