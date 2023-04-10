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
