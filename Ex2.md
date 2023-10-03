# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
 update manager set Salary = Salary + (Salary * 10/100);

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/c289f07c-2c4e-43fc-a441-8cbd5b1476c0)

### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
 delete from manager where salary<2750;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/08a838d9-7880-4435-9915-2b04319b4b04)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

### QUERY:
 alter table manager rename column ename to name;
 alter table manager rename column annualsalary to Annual_salary;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/26082c02-4fd2-4fc9-9334-8d5e406e0109)

### Q5)	List the names of Clerks from emp table.

### QUERY:
select name from manager where designation='clerk';

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/fef82741-7586-4d60-a1b4-3711b1ce3277)

### Q6)	List the names of employee who are not Managers.

### QUERY:
select name from manager where designation !='manager';

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/c62adf04-8d86-4590-a4c2-4b6d3e96696c)

### Q7)	List the names of employees not eligible for commission.

### QUERY:
 select name from manager where commission=0;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/767f26e8-c541-42db-93af-f8f657794921)

### Q8)	List employees whose name either start or end with ‘s’.

### QUERY:
SELECT * FROM manager WHERE name LIKE '%S' AND name like 'S%';

### OUTPUT:
![Screenshot 2023-10-03 084712](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/e34e4c07-6996-4061-abdb-d7c0384e3dd9)

### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.

### QUERY:
select * from manager order by Hiredate,name, designation,deptno asc;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/ddd6b923-1e0b-48ea-b390-c2a7cce78ab5)

### Q10) List the Details of Employees who have joined before 30 Sept 81.

### QUERY:
select * from manager where Hiredate<1981-09-30;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/d57c6c7b-3530-43d8-b893-de6e95244d3d)

### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.

### QUERY:
select name, deptno ,salary from manager order by deptno asc;
select name, deptno ,salary from manager order by salary desc;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/f20ff1f5-ccf2-4999-a428-2686020affff)

![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/8813a891-2329-4789-b307-b80e7dd9332f)

### Q12) List the names of employees not belonging to dept no 30,40 & 10

### QUERY:
 select name from manager where deptno != 10;
 select name from manager where deptno != 30;
 select name from manager where deptno != 40;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/b13d588b-cb70-4d71-a060-1ba997b1c24f)

![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/8c213c88-09dc-424e-9167-63b6fa4b3815)

![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/9c1f2b56-f59e-4c66-aba3-c54f07f001cd)

### Q13) Find number of rows in the table EMP

### QUERY:
 select count(*) as no_rows from manager;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/70cdb928-33a3-4bd4-be3e-5223d3b9ea4d)

### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
select min(Annual_salary) as Minimum from manager;
select max(Annual_salary) as Maximum from manager;
select avg(Annual_salary) as Average from manager;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/c774fdbf-5d84-4bb1-b161-9a059b3785c3)

![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/1dc5bfa2-4646-426e-80ed-a13c5729b6eb)

![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/05cefc22-9a5b-4bf6-8787-402e31dc1f02)

### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:


### OUTPUT:
