# SQL
SQL is very Important

REFERENCE BY FREECODECAMP

Day - 1 

sql is relational database.
installing mysql.
writing queries in sql.
creating database.
database schema

company database code is available in giraffeacademy.com

what is database?????

Collection of related information ///Eg phone Book,Shopping List, Todo List,Your 5 Best Friends,Facebook UserBase.

Database can be stored in different ways : ///On paper,in mind,on computer,powerpoint.

Computers are great at keeping track of large amounts of Information.

Lets compare two databases 

  1. Amazon.com - keeps track products,reviews,orders,credits,users,media etc. Trillions pieces of information need to be stored and readily available.security is essential. stored in computers
  2. Shpping list - track of consumer products, 10-20 pieces of information need to be stored, security is not important. Information stored in piece of paper. or it will be in someones memeory.

DBMS

special software program that helps users to create and maintain database.

easy to manage information.
handles security
backups.
import/export data
concurrency.
can interasct with applications.

amazon.com will interact with DBMS to create,read,update and delete information. -------- UseCase

CRUD- Create ,Read ,Update and Delete.

two Types of Database:
1.Relational (SQL) -------  organize data in tables ---- table,row,colums, unique key
2.No-Relational (NoSQL) ------- organize data is anything but traditonal table ------ documents xml,json,flexible,graphs,key-value stores.


Day-2

Relational Databases(SQL)        

for example student table      

id  name    major
1   jack    biology
2   mithun  psychology
3   john    chemistry

RDBMS ----  example  ----  mySQL,Oracle,postgreSQL
 
noSQL(Non Relational)
{
{
"_id":1,
"name":"Mithun",
"age":23
},
{
"_id":2,
"name":"Mithun",
"age":23
},
{
"_id":3,
"name":"Mithun",
"age":23
}
}

Document will be in json,xml.
Graphs are relational nodes.
Contains key value hashing pairs.

Non-Relational Databases(noSQL) ----- mongoDB,apache cassandra,firebase,dynamoDB etc

Database Queries  ---- asking database give specific information.

google search is also a query.

Tables and Keys

id  name      major     // here id is underscored means its a primary key.
1   Jack     Biology
2   Kate     sociology
3   claire   english
4   jack     biology     ///////column ----- Title  and rows---individual entry

email        password      type
m@gmail.com   sfjhgfygy73  admin  // //// here email is primary key
fake2gmail.com ugydgwq      free

employee table
empl_id   name      sex   salary   branch_id  super_id        ///empll_id is primary key
12121     sndjn     M     8736265   1         NULL
jgsyfg    hdghswag  F     35622     2         100             //here branch id is foreign key which is required to link one database table to another database table.
ifjeifji fiewjfij   M     731284    3         101
dlkndu    fkmwefme  F     46374     2         101             ///here super_id is also foreign key

mapping is done by foreign key,,,,you can have more than one foreign keys in table

branch table
branch_id  branch_name   mgr_id
2          Scranton      101        //branch_id is primary key here
3          Stamford      102
1          Corporate     108

branch supplier
branch_id   supplier_name     supply_type      /////here branch_id and supplier_name are primary key ,,,if more than one primary key present in table is called as composite key.
2          Hammer mill        paper
2           Uni-ball          writing utensils      ///here combination of two i.e branch_id and supplier_name jointly works as a primary key i.e composite key.
3          patriot paper      paper
2          Uni-ball           custom forms
3          Hammer mill        paper
3          stamford labels    custom forms


Day - 3

2 foreign keys of one table will considered as 1 primary key in that table   -----   which defines the relationship.

SQL Basics

SQL is language used for interacting with RDBMS.

1.Create,retrieve,update and delete data
2.manage databases
3.design and create database tables
4.perform administration task(security,import/export etc)

But here is a catch ,,, SQL implementations vary between system ,,, postegreSQL,mySQL(RDMS) commands varies slightly for these RDBMS. ///but concepts are same.

SQL basiclly made of 4 types of languages:
1.DQL(Data Query Language)  ----  query database for information
2.DDL(Data Definition Language)   ----  defining database schemas
3.DCL(Data Control Language)    ----  controll access to data in the database
4.DML(Data Manipulation Language)  ---- for inserting.updating,deleting data

Queries

Query is set of instructions given to RDBMS that tell RDBMS what information you want it to retrieve for you.

For ex: Select employee.name , employee.age from employee where employee.salary >30000;

MySQL Windows Installation

Search MySQL community server

 click on Windows 64/MySQL MSI installer  --- Download ----  No thanks ,,just start my download ---- Accept --- Custom  --- MySQL server 5.7 add it to right side --- mySQL shell 64 bit  ---- next --- standalone --- next  ---- password --- next ---- next --- configure --- finish 
 
 Search in Windows MySQL 5.7 Command Line Client --- password --- logged in --- connected mysql server .
 
 create database giraffe;
 
 You can do it in terminal
 
 Instead we can use popSQL which is better than terminal work.
 
 search popsql.io
 
 download for windows.  /// use it as text-editor.
 
 Day - 4
 
 sign in with google
 
 Connect to your database
 
 type:mysql
 hostname:localhost
 port:3306
 database:giraffe
 username:root
 password:kjnjngoejrg
 
 connect
 
 Now text editor is hooked up to the database.
 
 Creating Tables
 
 In PopSQL.
 
 Basic Data TYpes in sql are:
 1.INT
 2.Decimal(M,N)  Here M is length of number and N is number of decimals after decimal places.
 3.Varchar(l)
 4.Blob
 5.Date
 6.Timestamp
 
 Day - 5
 
 CREATE TABLE student (                                                          
 student_id INT PRIMARY KEY,
 name VARCHAR(20),                                                              
 major VARCHAR(20)                                                                 
 );                
                                                                                 
  student_id    name    major
  1        jack    biology
  2        kate    sociology
  3        claire  english
  
DESCRIBE student;

DROP TABLE student;

ALTER TABLE student ADD gpa DECIMAL(3,2);

ALTER TABLE student DROP COLUMN gpa;

--------------------******----------------------
Inserting Data:

INSERT INTO student VALUES(1,'Jack',"Biology');
INSERT INTO student VALUES(2,'Kate',"sociology');
INSERT INTO student VALUES(3,'claire',"english');

select * from student;

If student do not have any major than we can write query as follows:
INSERT INTO student(student_id,name) VALUES(4,'claire john');                /// amjor will be NULL

You cannot duplicate primary key!!!!!!!!!!!!!!!!!!!!!!!

--------------------------------**************--------------------------

Day - 6

C:NOT NULL,UNIQUE,DEFAULT,AUTO_INCREMENT ------ THese are called as Constraints.

 CREATE TABLE student (                                                          
 student_id INT,  
 name VARCHAR(20) NOT NULL,       ////Student Name is compulsory   otherwise,,,it will give syntax error                                                     
 major VARCHAR(20) UNIQUE,        ////If other major have same value then row will be rejected.
 PRIMARY KEY(student_id)
 );  
 
INSERT INTO student VALUES(1,'Jack',"Biology');
INSERT INTO student VALUES(2,'NULL',"sociology');  ///Syntax error will be thrown because name is declared as not null
INSERT INTO student VALUES(3,'claire',"Biology');   //// Duplicate entry 'Biology' for key 'major'

 CREATE TABLE student (                                                          
 student_id INT PRIMARY KEY,
 name VARCHAR(20),                                                              
 major VARCHAR(20) DEFAULT 'undecided'    /// If user do not have entry for major by default undecided string will be presented in table.
 );  
 
 CREATE TABLE student (                                                          
 student_id INT AUTO_INCREMENT,
 name VARCHAR(20),                                                              
 major VARCHAR(20),
 PRIMARY KEY(student_id)
 );  
 
INSERT INTO student VALUES('Jack',"Biology');
INSERT INTO student VALUES('NULL',"sociology');   /// If user do not even specify student_id it will be auto_filled by numbers using AUTO_INCREMENT constraint

-----------------------------------**********************-------------------------------------------

Update and Delete

UPDATE student                       
SET major = 'Bio'
WHERE major = 'Biology';

UPDATE student 
SET major = 'Comp Sci'
WHERE student_id=1;

UPDATE student                       
SET major = 'Biochemistry'
WHERE major = 'Bio' OR major = 'chemistry';

UPDATE student 
SET name = 'Tom' , major = 'undecided'
WHERE student_id=1;

UPDATE student 
SET major = 'undecided';

DELETE FROM student
WHERE student_id = 5;

DELETE FROM student
WHERE name='Tom' AND major = 'undecided';

-------------*****************---------------

Basic Queries:

SELECT * FROM student; /// everything in student table will be displayed. * means all

SELECT name FROM student; //// only names will be displayed from student table

SELECT student.name,student.major FROM student; //// displays only name and major from table student.

Day -7

SELECT student.name,student.major 
FROM student
ORDER BY name DESC;
/// If you DESC name will come in opposite alphabetic order.
////Name will be ordered according to alphabetic order.

SELECT * 
FROM student
ORDER BY student_id ASC;

///ASC by default

SELECT * 
FROM student                       //// First it will order by major with alphabetic order.
ORDER BY major,student_id;

SELECT * 
FROM student
LIMIT 2;  

///only 2 rows from table will be fetched.

SELECT * 
FROM student
ORDER BY student_id DESC
LIMIT 2;  

// order student_id with descing and limits it to 2 rows

SELECT * 
FROM student
WHERE major = "Biology" OR major = "Chemistry";  /// displays who is under biology or chemistry major.


SELECT * 
FROM student
WHERE major = "Biology" OR name = "kate";  ///  displays who is under biology or having name kate.

opeartors: ---

<> - Not equal to
<= - less than or equal to
>= - greater than or equal to
AND, OR


SELECT * 
FROM student
WHERE student_id < 3;  /// displays students list having student_id less than 3


SELECT * 
FROM student
WHERE student_id <= 3 AND name <> 'Jack';   //// student_id 1 2 3 and name should not be jack.

SELECT * 
FROM student                                 ///// Display student table having name claire,kate ,mike
WHERE name IN ('claire','kate','mike');

SELECT * 
FROM student                                 ///// Display student table having name claire,kate ,mike and student_id should be greater than 2
WHERE name IN ('claire','kate','mike') AND student_id > 2;

-----------------------**************************---------------------------------------

Company Database Into::::

We are going into more complex database schema

Emplyee table:

emp_id  first_name last_name birth_date sex salary super_id branch_id       ///// here emp_id is primary key and supervisor_id,branch_id is foreign key.

Branch table:

branch_id  branch_name  mgr_id  mgr_start_date               /////// branch_id is primary key,,, mgr_id is foreign key.

Client Table:

client_id client_name branch_id                       ///// client_id is primary key and branch_id is foreign key.

Branch Supplier Table:

branch_id  supplier_name  supply_type                ////// here we have composite primary key both will considered as one primary key,,,branch_id,supplier_name

Works_with Table:

emp_id client_id total_sales                   ///// emp_id and client_id is composite primary key.

-----------------------------****************-----------------

Creating Company Database:

DROP TABLE student;

employee table:

CREATE TABLE employee{
emp_id INT PRIMARY KEY,
first_name VARCHAR(40),
last_name VARCHAR(40),
birth_date DATE,
sex VARCHAR(1),
salary INT,
super_id INT,
branch_id INT
}

///// You have seen that super id and branch id are foreign keys but they are not mentioned as foreign keys because still we have not created tables for branch and supervisor so
we kept as normal attribute.

Day - 8

branch table:
create table branch (
branch_id INT PRIMARY KEY,
branch_name VARCHAR(40),
mgr_id INT,
mgr_start_date DATE,
FOREIGN_KEY(mgr_id) REFERENCES employee(emp_id) ON DELETE SET NULL);

In Employee table still super_id and branch_id is normal attributes so we need to alter table employee with:

ALTER TABLE employee
ADD FOREIGN KEY(branch_id)
REFERENCES branch(branch_id)
ON DELETE SET NULL;

ALTER TABLE employee
ADD FOREIGN KEY(super_id)
REFERENCES employee(emp_id)
ON DELETE SET NULL;
);

CREATE TABLE client(
client_id INT PRIMARY KEY,
client_name VARCHAR(40),
branch_id INT,
FOREIGN KEY(branch_id) REFERENCES branch(branch_id) ON DELETE SET NULL
);

CREATE TABLE works_with(
emp_id INT,
client_id INT,
total_sales INT,
PRIMARY KEY(emp_id,client_id),
FOREIGN KEY(emp_id) REFERENCES employee(emp_id) ON DELETE CASCADE,
FOREIGN KEY(client_id) REFERENCES client(client_id) ON DELETE CASCADE
);

INSERT INTO employee VALUES(100,'David','Wallace','1967-11-17','M',25000,NULL,NULL);

INSERT INTO branch VALUES(1,'corporate',100,'2006-02-09);

UPDATE employee
SET branch_id = 1
WHERE emp_id = 100;

------------------*************---------

 More Basic Queries:
 
 1.find all employees
 
 select * from employee;
 
 2.Find all employees ordered by salary
 
 select *
 from employee
 order by salary;
 
 3.Find all employees ordered by sex then name

select *
from employee
order by sex, first_name,last_name;

4.Find first 5 employees in the table

select *
from employee
limit 5;

5. Find first and last names of all employees

select first_name,last_name
from employee;

6.Find the forename and surname of employees

select first_name as forename,last_name as surname
from employee;

7. find out all different genders

select distinct sex
from employee;

-----------*88888888*-------------------------

Functions:

1.Find number of employees

select count(emp_id)
from employee;

2.Find number of female employees born after 1970

select count(emp_id)
from employee
where sex='F' AND date > '01-01-1971';

3. Find average of all employees salaries
 
 select avg(salary)
 from employee;


Day - 9


4.Find sum of all employees salaries

select sum(salary)
from employee;

AGGREGATION:

1.Find how many males and females

select count(sex),sex
from employee
group by sex;

2.Find total sales of each salesman

select sum(total_sales),emp_id
from works_with
group by emp_id;

------------------**************-------------

WILDCARDS::

% , _  are popular wildcards

1.Find any client's who are an LLC

select * 
from client
where client_name like '%LLC';

2.Find any branch suppliers who are in label business.

select *
from branch supplier
where supplier_name like '% Label%';

3.Find any employee born in october.

select *
from employee
where birth_date like '____-10%';


4.Find any clients who are schools

select * 
from client
where client_name like '%school%';

-----------**********************---------------------

UNION:::

1.Find list of employee and branch names

select first_name                 //if you add one more attribute last_name then it throws error 
from employee                        because of more than one column in first retrive compared to    
UNION                               second and they should be of same data type.U can use multiple
select branch_name                  UNION operators in one query.
from branch;

2.Find list of all clients and branch suppliers name

select client_name
from client
UNION
select supplier_name
from branch_supplier;

Day -10

3.Find a list of all money spent or earned by company.

select salary
from employee
UNION
select total_sales
from works_with;

JOINS

Insert into branch values(4,'Bufalo',NULL,NULL);

1.Find all branches and names of their managers.

select employee.emp_id,employee.first_name,branch.branch_name
from employee
join branch
on employee.emp_id = branch.mgr_id

select employee.emp_id,employee.first_name,branch.branch_name
from employee
left join branch
on employee.emp_id = branch.mgr_id;   /// left out people other than manager are displayed i.e is from employee table.

select employee.emp_id,employee.first_name,branch.branch_name
from employee
right join branch
on employee.emp_id = branch.mgr_id;

//even buffalo branch also added which dont have manager i.e from branch table.

Nested Queries::::::

-- 1.Find names of all employees who have 
-- sold over 30000 to single client.

select first_name,last_name
from employee
where emp_id IN (
select emp_id 
from works_with
where total_sales>30000;
);

--2.Find all clients who are handled by branch
--that michael scott manages
--assume you know michaels ID

select client_name
from client
where branch_id = (
select branch_id
from branch
where mgr_id = 102);


