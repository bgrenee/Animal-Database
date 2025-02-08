Mongo CRUD Python Module
About the Project
The goal of my project is to create a Python module that uses CRUD (create and read) operations in a MongoDB database. Essentially, this allows me to store data (create) and retrieve (read) that data when I need it.

Motivation
The motivation for this project is to focus on the management of large amounts of information. Using spreadsheets for large amounts of data is unrealistic. Spreadsheets lack role-based access and scalability, and spreadsheets are all manual. This makes spreadsheets a bad pick for larger applications. So, to fix this, this project creates the solution for larger applications which connects MongoDB an a NoSQL database that can handle larger datasets. 

Getting Started
For MongoDB database, we must set up authentication to connect to the server. This would be 
🌺 USER: root
🌺PASS: xEtjPRaT9l
🌺HOST: nv-desktop-services.apporto.com
🌺PORT: 34179
🌺DATABASE: AAC
🌺COLLECTION: animals
The Create method will allow us to add a new animal to the database. There were many challenges with this connection. I was unfamiliar with how to properly set up a connection and before fixing my errors, I was setting up my code, check the image down below.

!image

I am still unsure if this will work however, after some research, it seems that this is not standard practice due to the possibility of exposing sensitive information. So, I changed that to how it should have been done which looks like, check the image down below.

!image
 
I overcame these problems by reviewing my resources and doing some extra research.

Installation
How to set up:
•	Download Python, MongoDB, and Pymongo library
•	Install Pymongo into your IDE
•	You can clone the repository and put it into the IDE
         o	Git clone >> “link”>> cd repository
•	For your MongoDB details, update your connection string so you have a proper connection
•	Run project: run test_script.py to insert data into MongoDB

Usage

For this project, we specifically apply the Create and Read operations of CRUD to our Python module so that we can insert data and create a database for that data.  

Code Example
The code down below shows the connection between the client and server. We have the user, pass to the server, host, port, and both the database and the collections. Line 18 is the request for the connection to the MongoDB server.

!image

The code below is the Create function that is part of CRUD. Line 31 inserts a single document into the collection. However, if there is no data to be inserted, then nothing is saved. Or if there is an issue with inserting a document into the system, it will output an error message when returned false.

!image

The code down below is the Read function that is part of CRUD. Line 45 will find a document in our collection and if found, it will return the list of data in the collection. If the search for a document fails, it returns an empty list and an error message stating that it has failed due to an empty list.

!image
 
Tests
For our test, we ran this using Jupyter Notebook. It creates a new animal; in this case, the animal is Pussnboots. That will be in the MongoDB database. This test script is from out mongo_crud.py and imported to the animal database. 

Screenshots
The code down below imports the animal shelter class from the crud.py.

!image
 
This line of code read database helper is assigned to the animal shelter object. This is how the object interacts with the database.

!image
 
When it comes to creating a new animal record we create a dictionary, such as the animal being a cat, the name being Pussnboots, and the age being 12 (these are attributes). When the creation is successful, then the document will be inserted into the MongoDB database. 

!image
 
We need to make sure that the doc was added successfully. We do this by an if-else statement. If failed, error message will be outputted for the user.

!image

This code below will question if there is an animal with the name Pussnboots in the database with the help of the read method. That’s what db.helper.read(query) is for. Once it confirms that this animal does exist, it then is stored in the animal variable.

!image
 
To show the results of the query, we have these few lines of code. It will iterate through an animal list and that list is returned by the read method. If there are animals in this list, it will print the list. If not, then it will print an error message.


!image
 

Author
Bianca Gutierrez
