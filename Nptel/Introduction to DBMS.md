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


