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

Non-Relational Databases(noSQL) ----- mongoDB,apache cassandra,firebase etc
