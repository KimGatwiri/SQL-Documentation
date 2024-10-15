# SQL DOCUMENT
## SQL JOINS
### 1.Inner Join.
The inner join is used to combine rows from two or more tables based on a similar column between them.It then returns rows when there is atleast one match in both tables.
Syntax:  
SELECT<table1.column1>,<table1.column2>  
FROM table1 INNER JOIN table2    

### Example:
Residents table  
![Residents table](images/residents-table.PNG)  
cities table  
![cities table](images/cities%20table.PNG)  
inner join    
![inner join](images/inner%20join.PNG)

## 2.Left Join  
The left keyword returns all records from the left table (residents table) and matching records from the right table (cities table)
syntax:  
SELECT column_name(s)  
FROM table1  
LEFT JOIN table2  
ON table1.column_name = table2.column_name;
### Example

![Left join](images/Left%20join.PNG)
## 3.Right join
The right join key word returns all records from the cities table and the matching records from the residents table.
syntax:  
SELECT column_name(s)  
FROM cities  
RIGHT JOIN residents
ON table1.column_name = table2.column_name;
 ### Example
 ![Right join](images/Right%20join.PNG)

## ACID PROPERTIES
ACID is abbreviation for ATOMICITY,CONSISTENCY,ISOLATION and DURABILITY
Example:
Imagine you are transferring money from your savings account to your checking account. Let's say you want to transfer $500.

### ATOMICITY

It is a property that ensures that a process takes place at once or doesnt happen at all.There is no in between .  
Using our scenario, If any part of the transfer fails, the whole transaction is taken back.It is either the $500 is fully transferred, or nothing changes at all.
Example: If the bank deducts $100 from your savings account but fails to add it to your checking account due to a system crash, the system will stop the process , and no money will be deducted.
### CONSISTENCY
According to this property, only valid data is written to the database. Consistency enforces integrity constraints to maintain the accuracy and correctness of data.
After the transfer, both accounts should reflect a total balance of $500 if that was the balance before the transaction. If there were inconsistencies, such as $100 disappearing, the database would be in an invalid state, violating consistency.

### ISOLATION
Running transactions independently is the core of isolation. Changes in one transaction will not impact others until committed. Isolation maintains data integrity across concurrent transactions. 
If two people are transferring money at the same time, one transaction won't affect the other. Your $500 transfer will complete independently, even if someone else is also transferring money between their accounts.
### DURABILITY
Durability guarantees that all committed transactions are permanently recorded in the database. They persist even after system failure. Durability provides recoverability.
Example: Once the $100 is successfully transferred and the transaction is completed, the changes are saved permanently. Even if the bank’s system crashes, the record of your transfer will remain intact when it recovers.