2. Installations of MongoDB Server, Compass and Shell
The general steps for installing MongoDB Server, Compass and MongoShell:
1. MongoDB Server Installation:
Step1: Visit the MongoDB Download Center
(https://www.mongodb.com/try/download/community) in your web browser.
Step 2: Select the appropriate version of MongoDB Server for your operating system.
Choose the Community Server edition, which is free.
Step 3: Choose the version and operating system that matches your requirements and
click on the download button.
Step 4: Once the download is complete, open the installer file.
Step 5: Follow the installation wizard and accept the license agreement.
Step 6: Choose the components you want to install. Make sure to select the MongoDB
Server option.
Step 7: Choose the installation directory or keep the default location.
Step 8: Select the options for MongoDB as per your preferences, such as enabling
MongoDB as a service or adding MongoDB to the system's PATH.
Step 9: Click on the "Install" button to start the installation process.
Step 10: Once the installation is complete, you can proceed to configure and start
MongoDB Server.
2. MongoDB Compass Installation:
Step 1: Visit the MongoDB Download Center
(https://www.mongodb.com/try/download/compass) in your web browser.
Step 2: Select the appropriate version of MongoDB Compass for your operating system.
Choose the Community edition, which is free.
Step 3: Choose the version and operating system that matches your requirements and
click on the download button.
Step 4: Once the download is complete, open the installer file.
Step 5: Follow the installation wizard and accept the license agreement.
Step 6: Choose the components you want to install. Make sure to select MongoDB
Compass.
Step 7: Choose the installation directory or keep the default location.
Step 8: Select the options for MongoDB Compass as per your preferences.
Step 9: Click on the "Install" button to start the installation process.
Step 10: Once the installation is complete, you can launch MongoDB Compass.
3. MongoShell:
To set up the MongoDB Shell, you can follow these steps:
Step 1: Visit the MongoDB Download Center
(https://www.mongodb.com/try/download/shell) in your web browser.
Step 2: Select the appropriate version of MongoDB Shell for your operating system.
Choose the Community edition, which is free.
Step 3: Choose the version and operating system that matches your requirements and
click on the download button.
Step 4: Once the download is complete, extract the downloaded contents
Step5: Launch mongosh application, accept default connect string (press enter) and run
commands



3. CRUD Operations in MONGODBExercise–I: Student Database
AIM: To perform CRUD operations in Student Database
THEORY:
CRUD in MongoDB refers to the basic operations that can be performed on data
stored in a MongoDB database. CRUD stands for Create, Read, Update, and Delete,
representing the four fundamental actions that can be applied to database records or
documents.
Create (C): This operation is used to insert new documents into a MongoDB collection.
To create a new document, you typically construct a JSON-like object with the desired
data fields and values, and then insert it into the collection using the insertOne() or
insertMany() method.
Read (R): The read operation is used to retrieve data from a MongoDB collection.
MongoDB provides several methods to query documents, including find(), findOne(),
and aggregate(). You can use query criteria to filter the results and specify the fields
to be returned.
Update (U): The update operation allows you to modify existing documents in a
collection. MongoDB provides methods like updateOne() and updateMany() to
update documents. You specify a filter to identify the documents to be updated and the
modifications to be applied. Here's an example:
Delete (D): The delete operation is used to remove documents from a collection.
MongoDB provides methods such as deleteOne() and deleteMany() to delete
documents that match a specified filter
PROGRAM:
Create database, Create collection, insert data, find, find one, sort, limit, skip, distinct,
projection.
Create a student database with the fields: (SRN, Sname, Degree, Sem, CGPA)>
>use student1
Switched to db student1
>db.stud1col1.insert({srn:110,sname:"Rahul",degree:"BCA",sem:6,CGPA:7.9})
OR
> doc1=({srn:110,sname:"Rahul",degree:"BCA",sem:6,CGPA:7.9})>db.studcol1.insert
(doc1)
Note:insert 10 such documents.
Questions:1.display all the documents
>db.studcol1.find()
2.Display all the students in BCA
>db.studcol1.find({degree:"BCA"})
3.Display all the students in ascending order
>db. studcol1.find().sort({sname:1})
4.Display first 5 students
>db. studcol1.find().limit(5)
5.display students 5,6,7
>db. studcol1.find().skip(4).limit(3)
6.list the degree of student "Rahul"
>db. studcol1.find({sname : "Rahul"},{degree:1})
7.Display students details of 5,6,7 in descending order of percentage
>db. studcol1.find().sort({CGPA:-1}).skip(4).limit(3)
8.Display the number of students in BCA
>db. studcol1.find({degree:"BCA"}).count()




4. CRUD Operations in MONGODBExercise–II: Employee Database
AIM: To perform CRUD Operations in Employee database
PROGRAM:
Update modifiers ($set, $unset, $inc, $push, $pushAll, $pull, $pullAll, $addToSet)
Create an employee database with the fields: {eid, ename, dept, desig, salary, yoj,
address{dno,street, locality, city}}
> use empdb
switched to db empdb
> doc1 = {eid:001, ename:"Rahul", dept:"production", desig:"developer", salary:30000,
yoj:2015,address:{dno:397, street:2, locality:"rmnagar", city:"bangalore"} }
>db.emp.insert(doc1)
WriteResult({ "nInserted" : 1 })
Note:insert 10 documents.
Questions:1.Display all the employees with salary in range (50000, 75000)
>db.emp09.find({salary:{$gt:50000, $lt:75000}})
2.Display all the employees with desig developer>db.emp09.find({desig:"developer"}
3.Display the Salary of “Rahul”
>db.emp09.find({ename:"Rahul"},{salary:1})
4.Display the city of employee
>db.emp09.find({ename:"Rahul"},{"address.city":1})
5.Update the salary of developers by 5000
>db.emp09.update({desig:"developer"},{$inc:{"salary":5000}})
6.Add field age to employee Rahul
>db.emp09.update({ename:"Rahul"},{$set:{age:"22"}})
7.Remove YOJ from “Rahul”





3. Use Of Operators in CRUD in MongoDB
AIM: To demonstrate use of various Operators in MongoDB
THEORY:
In MongoDB, operators are used to perform various operations on data. Here are some
examples of operators commonly used in MongoDB:
Comparison Operators:
$eq: Matches values that are equal to a specified value.
$ne: Matches values that are not equal to a specified value.
$gt: Matches values that are greater than a specified value.
$lt: Matches values that are less than a specified value.
$gte: Matches values that are greater than or equal to a specified value.
$lte: Matches values that are less than or equal to a specified value.
Logical Operators:
$and: Joins query clauses with a logical AND.
$or: Joins query clauses with a logical OR.
$not: Inverts the effect of a query expression.
Array Operators:
$in: Matches any of the values specified in an array.
$all: Matches arrays that contain all the specified elements.
$size: Matches arrays with a specific number of elements.
Array Update Operators:
$push: Appends a value to an array field.
$pull: Removes all instances of a value from an array field.
$addToSet: Adds a value to an array field if it does not already exist.
$pop: Removes the first or last element of an array field.
These are just a few examples of the operators available in MongoDB. MongoDB
provides a rich set of operators to query and manipulate data efficiently.
PROGRAM:
Create users collection with name, age
// Find documents where the age is greater than 30
db.users.find({ age: { $gt: 30 } });
// Find documents where the name is not equal to "John"
db.users.find({ name: { $ne: "John" } });
// Find documents where the age is greater than 30 AND the name is "John"
db.users.find({ $and: [{ age: { $gt: 30 } }, { name: "John" }] });
// Find documents where the age is less than 25 OR the name is "Jane"
db.users.find({ $or: [{ age: { $lt: 25 } }, { name: "Jane" }] });
Create articles collection with tags fields
// Find documents where the "tags" field contains either "mongodb" or "database"
db.articles.find({ tags: { $in: ["mongodb", "database"] } });
Create students collection with scores in subjects
// Find documents where the "scores" array has exactly 3 elements
db.students.find({ scores: { $size: 3 } });
Array Update operators
Create required collections with documents before.
// Add a new element to the "tags" array field
db.articles.updateOne({ _id: ObjectId("articleId") }, { $push: { tags: "mongodb" } });
// Remove all occurrences of the value "completed" from the "status" array field
db.tasks.updateMany({}, { $pull: { status: "completed" } });
// Add the value "John" to the "names" array field if it doesn't exist
db.users.updateOne({ _id: ObjectId("userId") }, { $addToSet: { names: "John" } });
// Remove the last element from the "scores" array field
db.students.updateOne({ _id: ObjectId("studentId") }, { $pop: { scores: 1 } });
// Remove the first element from the "scores" array field
db.students.updateOne({ _id: ObjectId("studentId") }, { $pop: { scores: -1 } });
These commands demonstrate how to use the array update operators in
MongoDB to modify array fields within documents. Remember to replace the
placeholders like "articleId," "userId," and "studentId" with the actual document IDs or
appropriate query conditions.





4. Index Management in MongoDB
AIM: To demonstrate Index Management MongoDB
THEORY:
Indexes support the efficient resolution of queries. Without indexes, MongoDB
must scan every document of a collection to select those documents that match the
query statement. This scan is highly inefficient and require MongoDB to process a large
volume of data.
Indexes are special data structures, that store a small portion of the data set in
an easy-to-traverse form. The index stores the value of a specific field or set of fields,
ordered by the value of the field as specified in the index.
PROCEDURE:
The createIndex() Method
To create an index, you need to use createIndex() method of MongoDB.
Syntax
The basic syntax of createIndex() method is as follows
>db.COLLECTION_NAME.createIndex({name:1})
Here key is the name of the field on which you want to create index and 1 is for
ascending order. To create index in descending order you need to use -1.
In createIndex() method you can pass multiple fields, to create index on multiple fields.
The dropIndex() method
You can drop a particular index using the dropIndex() method of MongoDB.
Syntax
The basic syntax of DropIndex() method is as follows().
>db.COLLECTION_NAME.dropIndex({name:1})
PROGRAM:
Example of CreateIndex
>db.mycol.cretaeIndex({"title":1})
{
 "createdCOllectionAUtomatically" : false,
 "numIndexesBefore" : 1,
 "numIndexesAfter" : 2,
 "ok" : 1
}
Example of CreateIndex (MultiField Index)
>db.mycol.createIndex({"title":1,"description':-1})
use >db.col.getIndexes() to list out all Indexes in the collection
Example of dropIndex
>db.mycol.dropIndex({"title":1})




5. CRUD Operations in MONGODB from Python Exercise–I: Sports
database
AIM: To insert Sports Data in MongoDB from Python Program using Pymongo Drivers
THEORY:
PyMongo is a Python library that allows you to interact with MongoDB, a popular NoSQL database.
PyMongo provides a convenient and intuitive way to work with MongoDB by translating Python code
into database operations.
PROGRAM:
In Jupyter Cell execute ‘pip install pymongo’
After execution Restart Kernel
Write following Code in Jupyter and execute
import pymongo
url='mongodb://localhost:27017/'
client=pymongo.MongoClient(url)
db1=client['sports']
col1=db1['col11']
doc1={'name':'cricket','level':'international','no':11}
col1.insert_one(doc1)
doc2={'name':'hockey','level':'national','no':10}
col1.insert_one(doc2)
doc3={'name':'FootBall','level':'international','no':10}
col1.insert_one(doc3)
#Inserting documents with embedded documents with array fields
import pymongo
url='mongodb://localhost:27017/'
client=pymongo.MongoClient(url)
db1=client['sports']
col4 = db1['cricket']
doc4={'name':'cricket','level':'ipl','no':11,'players':{'batsmen':['virat','dhoni','rohit','kl
rahul','sky'],'bowlers':['shami','kuldeep','ashwin','jadeja','bumrah'],'wicketkeeper':'dhoni'}}
col4.insert_one(doc4)
Now Open MongoShell or Compass and test the data
.





6. CRUD Operations in MONGODB from Python Exercise–II: Fruits
Database
AIM: To insert Sports Data in MongoDB from Python Program using Pymongo Drivers
THEORY:
PyMongo is a Python library that allows you to interact with MongoDB, a popular NoSQL database.
PyMongo provides a convenient and intuitive way to work with MongoDB by translating Python code
into database operations.
PROGRAM:
In Jupyter Cell execute ‘pip install pymongo’
After execution Restart Kernel
Write following Code in Jupyter and execute
import pymongo
# Connect to MongoDB server
client = pymongo.MongoClient("mongodb://localhost:27017/")
# Create the Fruits database and New collection
db = client["Fruits"]
collection = db["New"]
# Define the documents to insert
document1 = {
 "name": "banana",
 "color": "yellow",
 "no": 5,
 "price": 10
}
document2 = {
 "name": "grape",
 "color": "dark blue",
 "no": 100,
 "price": 2
}
# Insert the documents into the collection
collection.insert_many([document1, document2])
# Create the Countries database and New1 collection
db = client["Countries"]
collection = db["New1"]
# Define the documents to insert
document1 = {
 "name": "India",
 "capital": "delhi",
 "no_states": 28
}
document2 = {
 "name": "USA",
 "capital": "Washington DC",
 "no_states": 50
}
# Insert the documents into the collection
collection.insert_many([document1, document2])
 To test data in MongoDB, open Mongoshell or compass and check data
