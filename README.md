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
<pre>
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="yourusername",
  password="yourpassword",
  database="mydatabase"
)

mycursor = mydb.cursor()

mycursor.execute("CREATE TABLE customers (name VARCHAR(255), address VARCHAR(255))")
</pre>
-------------------------------------------------------------------------
Select From a Table
To select from a table in MySQL, use the "SELECT" statement:


Select all records from the "customers" table, and display the result:
<pre>
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
  
  </pre>
-------------------------------------------------------------------------

  <pre>
select in all elements

c1 = ds.cursor()
c1.execute("select * from students")
n1 = c1.fetchall()

for i in n1:
      print(i)
output
PS D:\AAA\PYTHON\studentResult> d:/AAA/PYTHON/studentResult/db.py
(1, 'AC1Q34', 'suryask', '9', datetime.date(2023, 4, 12))
(2, 'AQ567', 'jonny', '10', None)
(3, 'AC1Q34', 'jonny', '10', datetime.date(2017, 4, 12))
</pre>
-----------------------------------------------------------------
  
  
    
select specifc text
<pre>
c1 = ds.cursor()
c1.execute("select * from students")
n1 = c1.fetchall()

for i in n1:
      print(i[Give index])
      break
output
PS D:\AAA\PYTHON\studentResult>  d:/AAA/PYTHON/studentResult/db.py
suryask
</pre>
-------------------------------------------------------------------------
  Inserting in mysql from pytho
  <pre>
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="myusername",
  password="mypassword",
  database="mydatabase"
)

mycursor = mydb.cursor()

sql = "INSERT INTO customers (name, address) VALUES (%s, %s)"
val = ("John", "Highway 21")

mycursor.execute(sql, val)

mydb.commit()

print(mycursor.rowcount, "record inserted.")
  </pre>
