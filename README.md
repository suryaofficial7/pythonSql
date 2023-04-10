# pythonSql
<b>py and Sql<b>

Download and install "MySQL Connector":
C:\Users\Your Name\AppData\Local\Programs\Python\Python36-32\Scripts>python -m pip install mysql-connector-python

-------------------------------------------------------------------------
demo_mysql_test.py:
import mysql.connector
-------------------------------------------------------------------------
Create Connection
Start by creating a connection to the database.
Use the username and password from your MySQL database:
demo_mysql_connection.py:

import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="yourusername",
  password="yourpassword"
)

print(mydb)


-------------------------------------------------------------------------

Creating a Table
To create a table in MySQL, use the "CREATE TABLE" statement.

Make sure you define the name of the database when you create the connection


Create a table named "customers":

import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="yourusername",
  password="yourpassword",
  database="mydatabase"
)

mycursor = mydb.cursor()

mycursor.execute("CREATE TABLE customers (name VARCHAR(255), address VARCHAR(255))")

-------------------------------------------------------------------------
Select From a Table
To select from a table in MySQL, use the "SELECT" statement:


Select all records from the "customers" table, and display the result:

import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="yourusername",
  password="yourpassword",
  database="mydatabase"
)

mycursor = mydb.cursor()

mycursor.execute("SELECT * FROM customers")

myresult = mycursor.fetchall()

for x in myresult:
  print(x)
-------------------------------------------------------------------------

  
<h2>select in all elements</h2>
<pre>
c1 = ds.cursor()
c1.execute("select * from students")
n1 = c1.fetchall()

for i in n1:
      print(i)
<b>OUTPUT</b>
PS D:\AAA\PYTHON\studentResult> & C:/Users/surya/AppData/Local/Programs/Python/Python311/python.exe d:/AAA/PYTHON/studentResult/db.py
(1, 'AC1Q34', 'suryask', '9', datetime.date(2023, 4, 12))
(2, 'AQ567', 'jonny', '10', None)
(3, 'AC1Q34', 'jonny', '10', datetime.date(2017, 4, 12))
</pre>
-------------------------------------------------------------------------
  
  
    
<h2>select specifc text</h2>
```
c1 = ds.cursor()
c1.execute("select * from students")
n1 = c1.fetchall()

for i in n1:
      print(i[Give index])
      break
<b>OUTPUT</b>
PS D:\AAA\PYTHON\studentResult> & C:/Users/surya/AppData/Local/Programs/Python/Python311/python.exe d:/AAA/PYTHON/studentResult/db.py
suryask
```
-------------------------------------------------------------------------
  
