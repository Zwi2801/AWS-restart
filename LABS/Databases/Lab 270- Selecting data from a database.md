                         LAB 270 Selecting data from a database 

**Overview**
The main purpose of this lab was to learn about relational databases how data is stored, organized, and accessed in these relational databases. Relational databases are a type of database that keep information in structured tables with rows and columns, making the information easier to access and retrieve. My main goal was to learn how to connect to a database and navigate its environment which enabled me to explore how the data was structured and how the different tables related to each other.

                  Key Objectives

1. Learning how relational databases manage data
2. Using and getting an understanding of the SELECT statement to query a database
3. Using and getting an understanding of the COUNT() function
4. Using <, >, =, WHERE, AND and ORDER BY operators to query a database

          Process followed- Tasks breakdown

**Task 1: Connect to the Command Host**

Firstly, I navigated through the AWS Management Console and connected to the Command Host EC2 instance. I then ran "my sql-uroot" command in the terminal to connect to the database server.

<img width="2880" height="1371" alt="image" src="https://github.com/user-attachments/assets/c62db647-a7b7-44f3-9928-8b5bb0c6b4b4" />


**Task 2: Query the database**
In this task, I queried an existing database called World using various statements and database operators. I kicked off the task by verifying that a database named world is available and I ran a "SELECT" query that enabled me to list all rows and columns in the country table. I then used the COUNT() function in a SELECT statement to query the number of rows in a table for example to count the number of rows that have a value in a specific column, I included the column name as a parameter in the COUNT() function: for example, COUNT(Population). Additionally I ran more SELECT statements using AS, ORDER BY and the DESC option with ORDER by query more information from the database. Lastly, I ran SELECT statements with the WHERE and AND clauses using the < and > operators to query all rows with a population greater than 50,000,000 and all rows with a population less than 100,000,000 which yielded the required output.

              Key Takeaways, difficulties encountered and how I resolved them

Some of the challenges encountered include errors within the command, understanding table structures, and fully understanding and interpreting query results. I would get the output: command not found when running some of the commands so I resolved that by using trial and error to rule out all the possible errors I could have commited which was a missing apostrophe at times. One of the main take away from this lab is that one should develop and master the ability to come up with clear, precise queries as they will make it easier to maintain and troubleshoot systems. In addition, good practices in design and structure ensure the database runs efficiently and it is essential to  understanding these principles to keep a database running smoothly, and for the database to be continually scalable and reliable.



