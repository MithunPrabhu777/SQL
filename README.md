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


