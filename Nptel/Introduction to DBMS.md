# Introduction to DBMS

A databse is collection of inter-related data which we called database and the second major component is set of software tools or programs which able to do operations on data like "acess the data" and "process the data". (often called query and update mechanism). 

Examples of information systems that requires the databases:

1. Bank systems
2. Library Information Systems (Book borrowing, Donating, Supplier, Issueing the books)
3. Railway/Airline Reservation Systems.

Before evolution of database these problems were solved using early information system where these systems directly uses the operating syetem which gives direct access to files!

**Early Information Systems (Method of Solution):**

In early systems you have many programs (suppose debiting, crediting, interest calculation, fix deposites) and these all programs can access the file system directly! and every OS gives you file system and same disk is shared between all!! 

<img width="660" height="186" alt="image" src="https://github.com/user-attachments/assets/e2d82bd0-581a-437d-8f94-f63393f46ee4" />

**Problems with Early Information Systems:**

The first and most dangerous problems is **Disorganised Development/Management**! so actually nobody knew what process has updated what kind of data and whenever user wanted to use data they dont know which data is there and which is not, so they started replicating the same data. So problem come with **Data isolation and Data redundancy**, the relationship between data was unknown and the data seems lost becuase there is no formalisation over what information what we want!

So **Data Isolation and Data Redundancy** was two major problems!

Data become Redundant mean the same copy of data is there at multiple location/places. So there are high chances that same data has been access by differnt programs which can be at differnt places so data become inconsistant! suppose x is at 5 places they suppose one program changes x at some k position and second program changes at k1 position then x become inconsistant!! and this is very dangerous condition!

Another problem occur when the computers become modern! **The Concurrancy**!

Concurrancy mean updation of sane data! If data is shared between two concurrant program then there is problem! suppose two people trying to book same seat at a same time! We know that for those 2 users the program instance were different but the Database is same!! 

Suppose booking program first checks the availability of x seat. and then it first check the available seats in one of table and then it writes the ticket number in that perticular seat and then it increment the total number of seats! So this cannot be done in single go! every program take significant amount of time! so now at the same time other user tried booking so yet the seat x is not booked yet the seat x has been acessed as notbooked seat and it will write another number on that seat x and then there is problem that both gets the same seat or a ticket for seat x with maybe same of differnt ticket number.

<img width="712" height="365" alt="image" src="https://github.com/user-attachments/assets/ebb82cb0-ce9d-4418-ae42-e7b14de0df85" />

and if you programmed it in sequencial manner then you'll never ever get the ticket 🤡.

and early systems dont have any mechanism to tackle such problems!

**Security Problem**

You dont wanted to allow the acess of the database to the users who can make the changes in the data!

**Integrity Constraints**

so suppose the money is debited from bank account there should be check that not allow the balance to drop down at certain threshhold. and if bank branch is closed down then the accounts in that branch must not present under that branch so these are constraint needs to be there in databases. So early information systems aint have these.

<hr>

**Role of DBMS**

So now the DBMS layer has been added in between the Application Program and the File Accessing sofwere. 

<img width="702" height="393" alt="image" src="https://github.com/user-attachments/assets/de2f0533-1ecc-419d-b90f-4ee98c55ebea" />

**Overall Organization of Data: Data Abstraction**

So database can broken up into several abstracted layers!

1. Physical level/layer (what data has stored where and how!)
2. Conceptual Level/layer (Database administrator and programming of database)
3. view level/layer (Database application Users)
4. Users View (different set of users)

**Schema and Instance**

In programming as we first define the types of data then the variables! same in the database you have to define the schema (it's a defination) and the instance! instance is like different users may have different instances of same data!

**Components of Database**

1. Data Defination Language (DDL)
2. Data Manipulation Language (DML)


DDL: This is how you defined your whole database. (Like relationships)

DML: you'll write your functions to work on data to be manipulated. It maybe procedural or non procedural and maybe the combination. Main operations are INSERT, DELETE, UPDATE, RETRIEVE. and the portion of this DML called Query Language! this will retrieve the data from database.

<img width="852" height="605" alt="image" src="https://github.com/user-attachments/assets/3ee884c7-cac1-4c82-bd3c-2fb06787473a" />

Db Scheme is the struture of data and application programs designed to work on it! query are question asked to db for retrival! and API's are menu driven interfaces (like reservation, cancellation of tickets)! The structure of database or information about data is stored in the Data Dictionary! (like what are field and their association and the type, length all these things are getting stored in data dictionary). DML compiler will create a Object Code to run!and Data files may indexed to get the access of data in minimal complexity! so they are index means they are places in order so retrieval is easier and faster!! It uses most of data Structures! There is nothing to be more explained becuase picture itself is more explainatory!

1. Study of operating systems also used in DBs, Like handling the concurrancy! the updation of shared resources!
2. Recovery from Failure (like the fatal failure) is also one of topic to discuss!
   
<hr>

#### Data Models

**Logical Data Models**

1. Entity-Relationship Model
2. Relational Model
3. Network Model
4. Hierarchical Model
5. Object-Oriented Model
6. Semantic Data Model
7. Functional Data Model

2,3,4 often called as Record Based Models! 


### E-R Model

Suppose we want to conceptually model a Library! So first we need to identify the basic Entities the attributes and that will be core of Model,

So suppose we have Entities : " BOOK ". " Users " 

and the book has attributes:

`Book: (Acc.No, Title, Author, Year Of Publication, publisher)`

`Users : (Card No, Name, Address, Status (student, faculty, staff), Code (roll No, employee code, staff code))`

Other than entities we have Relations! the relationship between entities are shown as relations!!

Most comman relation between book and user is `Borrowed By` ! like mapping user with books!!

<img width="1334" height="694" alt="image" src="https://github.com/user-attachments/assets/baab988e-edff-4639-8b4d-e6161f129f54" />

Even the relation can have attributes: 

`Borrowed By: (Date of Issue)`

So this diagramatic representation or E-R Model! and you can express many type of constraints (like one book can be only borrowed by one user).






