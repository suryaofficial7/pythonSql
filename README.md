# pythonSql
py and Sql

Download and install "MySQL Connector":
C:\Users\Your Name\AppData\Local\Programs\Python\Python36-32\Scripts>python -m pip install mysql-connector-python


demo_mysql_test.py:
import mysql.connector

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
