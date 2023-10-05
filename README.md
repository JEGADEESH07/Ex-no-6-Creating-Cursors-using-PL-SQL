# Ex. No: 6 Creating Cursors using PL/SQL

### AIM:
To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table
```
CREATE TABLE A1 (emp_id number,emp_name char(20),emp_dept char(20),emp_salary number);
```
### Inserting the values:
```
INSERT INTO A1 VALUES(1,'Jakie Chan','HR',70000);
INSERT INTO A1 VALUES(2,'Chin Chan','MD',95000);
```

### PLSQL Cursor code
```
SQL> set serveroutput on
SQL>  declare
      cursor A1_cursor is
      select emp_id, emp_name,emp_dept,emp_salary
      from A1;
      emp_id number;
      emp_name varchar(90);
      emp_dept varchar(90);
      salary number;
      emp_salary number;
      begin
      open A1_cursor;
      loop
      fetch A1_cursor into emp_id,emp_name,emp_dept,emp_salary;
      exit when A1_cursor%notfound;
      dbms_output.put_line('Employee ID: '||emp_id);
      dbms_output.put_line('Employee Name: '||emp_name);
      dbms_output.put_line('Department: '||emp_dept);
      dbms_output.put_line('Salary: '||emp_salary);
      end loop;
      close A1_cursor;
      end;
      /

```
### Output:
![image](https://github.com/JEGADEESH07/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/113497131/42a0b6e5-471b-4451-b37c-95510fc6417f)


### Result:
To create a cursor using PL/SQL is executed successfully.
