1-------------------------------------------------------
CREATE DATABASE Company;
CREATE TABLE `company`.`departments` (
`Dept_ID` INT NOT NULL AUTO_INCREMENT,
`Dept_Name` NCHAR(10) NOT NULL,
PRIMARY KEY (`Dept_ID`));

USE company;
INSERT INTO departments (Dept_Name)
VAlUES ('HR'),
('Software'),
('Admin'),
('Payroll'),
('Security'),
('Info');

USE company;
UPDATE departments SET Dept_Name = 'HRD'
WHERE Dept_Name = 'HR';
UPDATE departments SET Dept_Name = 'Finance'
WHERE Dept_Name = 'Payroll';

USE company;
CREATE TABLE branches (
BID INT NOT NULL AUTO_INCREMENT,
Branch_Name NCHAR(20),
PRIMARY KEY (BID));

USE company;
INSERT INTO branches (Branch_Name)
VAlUES ('Mumbai'),
('Delhi'),
('Chennai'),
('Kolkata');

2-------------------------------------------

USE company;
Create table Employees(
EmpID INT PRIMARY KEY,
Emp_FirstName nchar(20),
Emp_LastName nchar(20),
Emp_City nchar(20),
DOJ date,
Salary int,
Dept_ID smallint references departments(Dept_ID),
BID smallint references branches(BID)
);


INSERT INTO company.employees
VALUES (1,'Abhishek','Kataria','Delhi','2015-12-10',70000,1,2),
(2,'Akhil','Arya','Chennai','2016-12-10',80000,2,1),
(3,'Will','Smith','Mumbai','2017-12-10',90000,2,2),
(4,'Rohan','Kawatra','Kolkata','2018-12-10',80000,3,3),
(5,'Amit','Kumar','Delhi','2019-12-10',88000,4,1),
(6,'Abhi','Karla','Chennai','2020-12-10',75000,5,2),
(7,'Randeep','Hooda','Mumbai','2021-12-10',65000,4,4),
(8,'Sunny','Deol','Kolkata','2015-01-10',95000,5,2),
(9,'Bruce','Lee','Delhi','2016-05-10',82000,3,4),
(10,'Vladimir','Putin','Chennai','2017-09-10',78000,1,1),
(11,'Rahul','Sharma','Mumbai','2018-11-10',85000,2,2),
(12,'Raju','Rastogi','Kolkata','2019-12-25',92000,5,3)
;


DELETE FROM company.departments WHERE Dept_Name = ‘info’;

3------------------------------------------------------------------------
The following sample anonymous block 
selects an employee last name into a variable and prints the name:
DECLARE
 v_lname VARCHAR2(25);
BEGIN
 SELECT last_name INTO v_lname
 FROM employees
 WHERE employee_id = 101;
 DBMS_OUTPUT.PUT_LINE('Employee last name is '||v_lname);
END;


