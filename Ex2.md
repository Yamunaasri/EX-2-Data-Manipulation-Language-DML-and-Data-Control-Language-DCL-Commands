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
update manager set salary=salary+(salary*0.10);

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/e514ce75-5476-4af0-861c-57df41df6377)

### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
delete from manager where salary<2750;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/330eca4a-968a-4e68-9f6e-340eb7eac0fc)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

### QUERY:
select ename as "Name",salary*12 as "Annual salary" from manager;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/367fe3a3-d13e-4e7b-a714-6b67aba3ab3a)

### Q4)	List the names of Clerks from emp table.

### QUERY:
select name from manager where designation='clerk';

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/d3e45669-748a-4dfa-a5c1-99f1915a9e0e)

### Q5)	List the names of employee who are not Managers.

### QUERY:
select name from manager where designation !='manager';

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/03cb4af7-0748-49d1-bf02-61221575055f)

### Q6)	List the names of employees not eligible for commission.

### QUERY:
 select name from manager where commission=0;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/cd9f5e2e-f4ee-4a0b-a9d8-cef7fe70cf37)


### Q7)	List employees whose name either start or end with ‘s’.

### QUERY:
select ename from manager where ename like '%S' or ename like 'S%';

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/7edb1d26-09f3-4ebe-a5e8-c9816922b22d)

### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.

### QUERY:
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/9a0e8b35-6561-4769-b4c5-b8cea95de6e0)

### Q9) List the Details of Employees who have joined before 30 Sept 81.

### QUERY:
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/08d9d083-1370-4137-9a39-8533aae18939)

### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.

### QUERY:
select ename,deptno,salary from manager order by deptno asc,salary desc;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/93396b2f-4462-4260-9cf3-e98a1fefd77e)

### Q11) List the names of employees not belonging to dept no 30,40 & 10

### QUERY:
select ename from manager where deptno not in (30,40,10);

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/ab4cae78-bf78-43fd-aef0-ae73a3916820)

### Q12) Find number of rows in the table EMP

### QUERY:
select count(*) from manager;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/675e21ba-7406-4aa9-ae99-1bb24ae5f062)

### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:
select max(salary) from manager;
select min(salary) from manager;
select avg(salary) from manager;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/50ac643e-4237-41ae-ac2b-4dd678fca6dd) ![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/33603c8e-cbb3-4ca8-bfcf-ec0d2ea9a2fe) ![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/f15abcd6-951c-48a4-8493-5b9d67b81945)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;

### OUTPUT:
![image](https://github.com/Yamunaasri/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115707860/ce17fa74-e1c8-4d27-858b-27c3e026706a)

### RESULT:
To create a manager database and execute DML queries using SQL is executed successfully.
