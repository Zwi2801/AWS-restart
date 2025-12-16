                     LAB 275 Introduction to Amazon DB

**Overview**
In this lab, I got hands-on and practical experience with Amazon DynamoDB through the creation of a table to store information about a music library then I also queried the music library and then deleted the DynamoDB table. Amazon DynamoDB is a fast and flexible NoSQL database service with a fully managed database that supports both document and key-value data models. It is ideal  Its flexible data model and reliable performance make it a great fit for all applications that need consistent, single-digit millisecond latency at any scale, specifically mobile, web, gaming, ad-tech, Internet of Things (IoT), and many other applications.

              Key Objectives

1. Understand how DynamoDB stores data using tables and attributes
2. Created a table in DynamoDB and I called it Music
3. Insering music records with attributes such as artist and song
4. Modifying existing data with errors and correcting the errors
5. Querying data from a DynamoDB table to retrieve the data
6. Deleting the Music table, which will resulted in the deletion of all the data in the table


                      Process followed- Task Breakdown

 **Task1: Create a new table**

I kicked off this lab by accessing the AWS Management console and from the Services menu, I navigated to DynamoDB under the Database section. I then selected create table and I named the table Music. I set Artist as the Partition Key with the data type set to String, and I added Song as the Sort Key, also with the data type String then I confirmed for the table to be created and waited until its status changed to Active. 

<img width="1628" height="796" alt="image" src="https://github.com/user-attachments/assets/e668a8d4-74ae-48b0-af52-ead1a37be602" />


**Task2: Add data**

In this task, I selected the Music table and chose Create item where I added the first item with attributes such as Artist, Song, Album and year. Secondly, I created a second item with additional attributes, including Genre, to demonstrate DynamoDB’s schema-less design. Lastly, I created a third item that included a new attribute called LengthSeconds, showing the flexibility of NoSQL databases.

**Task 3: Modifying an Existing Item**

I navigated to Explore Items in the DynamoDB dashboard then I selected the Psy record where I corrected the Year attribute from 2011 to 2012 then I saved the changes, successfully updating the item.

<img width="1622" height="852" alt="image" src="https://github.com/user-attachments/assets/b88da0eb-7623-4177-8b07-019daf10067a" />


**Task 4: Querying the Table**

I used the Query option to retrieve a specific item efficiently. I specifically entered Artist:Psy and Song:Gangnam Style then I ran the query and confirmed that the correct item was returned almost instantly. I then used the Scan option to find items released in a specific year where I applied a filter for the Year = 1971, which returned only Imagine by John Lennon. This demonstrated the difference between Query which fast and indexed and Scan which is less efficient.

<img width="1814" height="830" alt="image" src="https://github.com/user-attachments/assets/06f56abc-2342-4632-a7bd-595514396326" />


**Task 5: Deleting the Table**

From the DynamoDB dashboard, I selected the Music table and chose Actions then clicked on Delete table. I then confirmed the deletion by typing delete and the table and all its data were permanently removed.

          Key Takeaways

Overall, this lab provided practical experience with DynamoDB and helped me understand how NoSQL databases differ from traditional relational databases, particularly in terms of flexibility and scalability. I also discovered that there are two ways to query a DynamoDB table namely query and scan. A query operation finds items based on the primary key and optionally the sort key and is fully indexed, so it runs very fast and is the most efficient way to retrieve data from a DynamoDB table. Alternatively, you can scan for an item which involves looking through every item in a table, so it is less efficient and can take significant time for larger tables.













