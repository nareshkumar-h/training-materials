
#### Project: In Banking App , I have two user accounts.

* **Table Name**: accounts

| ACCOUNT_NO  | USER_ID  | ACCOUNT_TYPE  | BALANCE  | 
|---|---|---|---|
|  101 | Naresh  | SAVINGS  | 10000  | 
| 102  | Siva  | SAVINGS  | 2000  |  

* **Table Name:** transactions

| TRANSACTION_ID  | ACCOUNT_NO  | TRANSACTION_TYPE  | AMOUNT  | STATUS  |
|---|---|---|---|---|
|  |   |   |   |   |

##### Scenario #1: In Banking App , I want to withdraw Rs.3000 from my bank account in ATM

* **Table Name**: accounts

| ACCOUNT_NO  | USER_ID  | ACCOUNT_TYPE  | BALANCE  | 
|---|---|---|---|
|  101 | Naresh  | SAVINGS  | <del>10000</del> 7000  | 
| 102  | Siva  | SAVINGS  | 2000  |  

* **Table Name:** transactions

| TRANSACTION_ID  | ACCOUNT_NO  | TRANSACTION_TYPE  | AMOUNT  | STATUS  |
|---|---|---|---|---|
|  1 | 101  | DEBIT  | 3000  | SUCCESS  |


## Definition of Transaction

* A transaction is a single logical unit of work which accesses and possibly modifies the contents of a database. 
* Transactions access data using read and write operations. 
* In order to maintain consistency in a database, before and after the transaction, certain properties are followed. 
* These are called **ACID properties**. 

## ACID Properties

* Atomicity
* Consistency
* Isolation
* Durability

![image](https://user-images.githubusercontent.com/2763774/158994244-00f19386-8ff3-4dcd-8433-38f121f50d75.png)


#### Scenario #2: Fund Transfer  Rs.500 from Person 1 account No (101) to  Person 2 account No (102) .

* **Table Name**: accounts

| ACCOUNT_NO  | USER_ID  | ACCOUNT_TYPE  | BALANCE  | 
|---|---|---|---|
|  101 | Naresh  | SAVINGS  | <del>7000</del> 6500  | 
| 102  | Siva  | SAVINGS  | <del>2000</del> 2500  |  

* **Table Name:** transactions

| TRANSACTION_ID  | ACCOUNT_NO  | TRANSACTION_TYPE  | AMOUNT  | STATUS  |
|---|---|---|---|---|
|  2 | 101  | DEBIT  | 500  | SUCCESS  |
|  3 | 102  | CREDIT  | 500  | SUCCESS  |

* Transaction Control Statements : COMMIT, ROLLBACK
* From Account 1, amount is deducted.
* From Account 2, amount is credited.
* Both the transaction is successful, so we will give **"COMMIT"** command.

#### Scenario 3: Fund Transfer from account 1 to account 2 ( Account No 2 is invalid account no )

* Transaction Control Statements : COMMIT, ROLLBACK
* From Account 1, amount is deducted.
* Then, we found Account 2 is invalid. Then we have to revert the entire transaction using **ROLLBACK** command.

