# EX.NO 4 Data Control Language (DCL) Commands and Transaction Control Languages (TCL) in SQL
### DATE:
## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY
## Data Control Language (DCL) commands
* Data control language (DCL) is used to access the stored data.
* It is mainly used for revoke and to grant the user the required access to a database.
## List of DCL commands: 
1. GRANT : It is used to insert data into a table.
2. REVOKE: It is used to update existing data within a table.
## Transaction control language(TCL) commands
1. COMMIT : COMMIT command in SQL is used to save all the transaction-related changes permanently to the disk
2. START TRANSACTION : to start the transaction
3. ROLLBACK : undo the transaction upto savepoint 
4. SAVEPOINT : create a savepoint to save the different parts of the same transaction using different names

### Q1) Create a table employee with employee id ,name and Address

### QUERY:
```
sql
create table employee(
emp_id numeric,
emp_name varchar(10),
addr varchar(40)
);
```


### OUTPUT:
![dbms-41](https://github.com/22008650/DBMS/assets/122548204/057b8ea2-7bb2-4ba8-9ac0-b63b081e374d)


### Q2) Insert three rows into emploee table 


### QUERY:
```
insert into employee values(1,'Luffy','EastBlue');
insert into employee values(2,'Shanks','GodValley');
insert into employee values(3,'Grap','MarinFord');
```


### OUTPUT:
![dbms-42](https://github.com/22008650/DBMS/assets/122548204/122c17e8-b0eb-4b9b-9f5f-44ab2e36d77c)


### Q3) Start the transaction and create a save point s1.

### QUERY:
```
savepoint A;
```

### OUTPUT:
![dbms-43](https://github.com/22008650/DBMS/assets/122548204/4818c104-7631-4ef2-88cc-81519953e649)


### Q4) Perform insertion into employee table.

### QUERY:
```
insert into employee(4,'Robin','EniesLobby');
```

### OUTPUT:
![dbms-44](https://github.com/22008650/DBMS/assets/122548204/1f5635d6-a7fc-4e4a-a0a9-5f514f404d7a)


### Q5)	Display the employee table and create a save point s2 .


### QUERY:
```
sql
select * from employee;
savepoint s2;
```


### OUTPUT:
![dbms-45](https://github.com/22008650/DBMS/assets/122548204/9e891499-97da-496b-b1a9-19b182dd7aca)


### Q6)	Perform updation on any one of the row.


### QUERY:
```
sql
update employee set emp_name='Nico Robin' where emp_id=4;
```


### OUTPUT:
![dbms-46](https://github.com/22008650/DBMS/assets/122548204/08aebe80-aaba-4296-ab72-54c6b28e110c)



### Q7) Display the employee table and rollback to  save point s2 


### QUERY:
```
sql
select * from employee;
rollback to s2;
```


### OUTPUT:

![dbms-47](https://github.com/22008650/DBMS/assets/122548204/fc8b88f2-6c2a-41da-9375-6fff732b7b05)


### Q8) Display the employee table and commit the changes; 


### QUERY:
```
sql
select * from employee;
commit;
```

### OUTPUT:
![dbms-48](https://github.com/22008650/DBMS/assets/122548204/cd23e682-0f14-4cbd-9ce3-07975ac7adea)

### Q9) Rollback to save point s1;


### QUERY:
```
sql
rollback to A;
```


### OUTPUT:
![dbms-49](https://github.com/22008650/DBMS/assets/122548204/b48a0dba-5649-4370-a721-407d70f50917)


### Q10)	Create a new user and grant access to any one database with "insert and update"


### QUERY:
```
CREATE USER new_user;
GRANT INSERT, UPDATE ON database_name TO new_user;
```


### OUTPUT:
![dbms-410](https://github.com/22008650/DBMS/assets/122548204/efe67c09-fa7a-4439-9d46-77e77270cf37)
![dbms-411](https://github.com/22008650/DBMS/assets/122548204/cfffdc05-4f3d-4d64-89a6-b9d55d02a3c3)



### Q11) Check the user access and display the result 


### QUERY:
```
SHOW GRANTS FOR new_user;
```


### OUTPUT:
![dbms-412](https://github.com/22008650/DBMS/assets/122548204/8a9512ca-12ae-42ae-b3ec-3e4b45d74af4)


### Q12) Revoke the privillages.

### QUERY:
```
SHOW GRANTS FOR new_user;
REVOKE INSERT, UPDATE ON database_name FROM new_user;
SHOW GRANTS FOR new_user;
```


### OUTPUT:
![dbms-413](https://github.com/22008650/DBMS/assets/122548204/11b93c01-17af-435c-bce8-6433b4bbb1db)

## RESULT :
Thus the basic TCL and DCL commands are executed.
