# Ex. No: 6 PL/SQL program to perform addition and subtraction of two number 
### DATE: 
### AIM: To create PL/SQL program to perform addition and subtraction of two number.

### Steps:
1. Declare the variable a, b and necessary variables in Declare section.
2. Perform addition of two numbers
3. Perform subtraction of two numbers 
4. Display the result 
5. End the begin section.

### Program:
```
DECLARE
 a NUMBER := 550;
 b NUMBER := 450;
 c NUMBER;
BEGIN
 c:=a+b;
 dbms_output.Put_line('addition of two numbers is '||c);
 c:=a-b;
 dbms_output.Put_line('subtraction of two numbers is '||c);
END;
```

### Output:
![image](https://github.com/22008650/DBMS/assets/122548204/64800f1c-089b-4145-88f4-40fa9944ad7d)


### Result:
Thust the program was performed sucessfully.
