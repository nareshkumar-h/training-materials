## Normalization 
* Normalization is a database design technique that reduces data redundancy and eliminates undesirable characteristics like Insertion, Update and Deletion Anomalies. 
* Normalization rules divides larger tables into smaller tables and links them using relationships. 
* The purpose of Normalisation in SQL is to eliminate redundant (repetitive) data and ensure data is stored logically.


## Event Registration App

* Table Name: users

| name  | email |  event_names  | 
|---|---|---|
| Naresh | n@gmail.com | Coding Event, Singing Event 
| Suresh | s@gmail.com | Singing Event
| Ramesh | r@gmail.com | 

* If user registers for an event, we will keep adding the select event names in  **event_names** column.

#### Step 1: Convert to 1st Normal Form
* Each table cell should contain a single value.
* Each record needs to be unique.

* Refactor:
   * **event_names** column contains multi valued attribute. It contains two values - "Coding Event, Singing Event "

* Table Name: users

| id | name  | email | 
|---|---|---|
| 1 | Naresh | n@gmail.com | 
| 2 | Suresh | s@gmail.com | 
| 3 | Ramesh | r@gmail.com | 

* Table Name: user_events

| user_id | event_name  |  
|---|---|
|1 | Coding Event  | 
|1 | Singing Event  |
|2 | Singing Event  |


##### Scenario #2:  We want to add event timings

* Table Name: **user_events**

| user_id | event_name  |  event_timings |
|---|---|---|
|1 | Coding Event  | 11:00 |
|1 | Singing Event  | 12:00 |
|2 | Singing Event  | 12:00 |


##### Apply 2nd Normal Form

* In the second normal form, all non-key attributes are fully functional dependent on the primary key
* In the above table , **"event_timings"** is not dependent on **"user_id"** column


* Table Name: **events**


| id | event_name  |  event_timings |
|---|---|---|
|101 | Coding Event  | 11:00 |
|102 | Singing Event  | 12:00 |

* Table name: **user_events**

|id | user_id | event_id  |  
|---|---|---|
|10001 | 1 | 101  |
|10002 | 1 | 102  |
|10003 | 2 | 102  |

