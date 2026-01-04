# Conceptual Modeling

We already have learned about KEY attributes (Superkey, Candidate key, Primary Key).

Now lets learn Concept of **Generalisation!**.

Consider a **TICKET** (In railway reservation system) can have several Attributes. (ATTR: Ticket No, Start, Destination, Date Of Issue, Fare, Distance). So this makes a Ticket! Now if we wanted to distinguish the reserved ticket or unreserved ticket or a express Ticket or a Normal Ticket! Now differentiating can be possible in many ways. For example if we have one more attribute Reserved/Unreserved to just identify if ticket is reserved or not! but is it suffice???? nope! It still don't make any sense till we have information about, if reserved then which train, what seat no, if any extra fare charge?  So we may have to saparate entity itself one is reserved entity Ticket and another is unreserved. But conceptually a lot of attr are comman. 

What we'll do suppose we have a **TICKET.** ans we have a `IS A` Relatationship!

<hr>

<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/94415d1c-8a18-42cb-9e8c-a023392a3534" />

<hr>
So now 2 type of special cases! Ticket can be reserved or unreserved. So ticket is generalisation of reserved and unreserved ticket. What about attribute?? So Comman Attributes will be on TICKET. (Start, Destination, Ticket No, Date of Issue) and the Other attributes is on those 2 entities.

**Reserved Ticket:** (Attr: Train No, Seat No, Fare, Reservation Upto....)

**Unreserved Ticket:** (Attr: Local/Express, Fare ...)

<hr>

### Aggregation

Let's consider an example.

We have a SET of **TEACHERS** which forms a one form of Entity set and we also have another Entity Set called **SUBJECTS**. and We have one relationship **TEACHES**.

Attributes: 

TEACHER: (Attr: Name, Dept ...)

SUBJECT: (Attr: Title, Subject Code, UG/PG, LTP ...)

Now we want to model the set of BOOKS used by a Teacher to TEACH a SUBJECT.

We have Entity Set BOOK. and also we have relationship USES which shows `TEACHER USES B1 to TEACH SUBJECT S1`.

<hr>
<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/8b61994e-9b53-4f7e-be47-fd98e068ef3c" />
<hr>


Now there maybe conceptual problems over here! we have multiple relationships here and TEACHER TEACHES SUBJECT so we have TEACHES relationship but again which books Teacher used to teach, so to identify TEACHER USES Book1. So this shows us which book Teacher USES but again now sure for which subject? So we done this to only get an answer or statisfy the Statement that **" TEACHER USES BOOK b1, b2 to TEACH SUBJECT T1 "**. The sole purpose is to establish the relationship between the Entities  "TEACHES" and "USES". but normally we do not allow the relationships between the RELATIONS and RELATIONS like in our case TEACHES and USES that is why we forced to model this above entities. and one more thing to note that the RELATIONSHIPS ENTITIES comprises the Set of Attributes from Both TEACHER or SUBJECT or BOOKS. So whatsoever relationships are build on the top of these tables will comprises the comman attributes of these tables. So considering one BIG ENTITY comprises the (TEACHER, TEACHES, SUBJECT) we can say the ENTITY is 
aggrigate entity of itself and his relationships!

Why we have used the aggregation! ??? 

The reason is if you looked at the above diagram (Conceptually) so we dont have to model one scneario where if teacher aint teaches subject s1 but teacher used the book b1 for subject s1. so that's not what we wanted to model. we dont want that, we want "TEACHER USES Book B1 to TEACH SUBJECT S1". but the above conceptually can model "TEACHER DONT TEACHES SUBJECT S1 BUT USES BOOK B1 FOR SUBJECT S1". So aggregated entity Model it better conceptually. **So aggregation allowed us to RELATE or map RELATIONSHIPS with RELATIONSHIPS.**

<hr>
<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/5ce725eb-d31b-4f23-a1a4-17320008b6e5" />
<hr>


Now if you look above the aggregation! then the teachers who teaches the subjects are aggregated as one relation and that relation is related to USES now! so the teacher who teaches the subject can only USES the BOOKS to teach!


Lets look how relational Model helps!! We can visualise these entitites with help of Tables!! 

<hr>
<img width="800" height="394" alt="image" src="https://github.com/user-attachments/assets/380f4da3-1b87-471e-be37-7f77912ae599" />
<hr>

Now suppose we have the Entity BOOK, BORROWED BY, USERS

Now suppose we wanted to map the attribut of USERS and BOOKS to BORROWED BY! Now suppose the Given Attr of the BOOK IS: (Acc No, Title...etc) and for USERS : ( Card No, Name, Address, etc.)! so for the relationship we can have the unique keys from both of the table or primary key from both of tables in this case! (Acc No from BOOK and CardNo USERS) to be the attributes of relationship BORROWED BY. and let say DOI is also an additional attribute so comprises all attributes we have the BORROWED BY Relationship! 

why we cant club everything together?? (BOOK + USER + BORROWD BY) in single table? because here the user may or may not have a book associated or it is not mandatory for user to borrow a book! so we cant club everything together!!

Lets understand it further!! Lets say X entity is Strong entity and Y entity is Weak Entity! so Y's existing depends on X! there must be relationship exist XY inorder for Y to exist! So we cant club the X and Y together to be one relationship! 

lets understand further:

<hr>
<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/9cf534af-efba-418e-b182-397f5c335740" />
<hr>


Here the X entity has its attributes and the Y entity has it's attributes! but if the Y entity is the weak entity then it may or may not have the PRIMARY KEY or unique identifier becuase its existance depend on the strong entity (assumption). Now for X entity we have one PRIMARY KEY attribute and let say that is differnt Table all together! and RELATIONSHIP XY also exist and have its own attributes! But if we merge the XY with Y then we may have all the attributes of Y in XY only becuase **Y is Weak Entity.**


<hr>

<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/4a0714e7-d615-4de6-b16b-888f1d901395" />

<hr>

Now look at the above Model! Now here the multiple books can be borrowed by a USER but one Book cannot be shared amongs the multiple user! So the relationship between the USER and BOOK is One to Many or One to One! here we have 5 tables total.

**DATABASE SCHEME:**

1. BOOK_SCHEME ( ACC_NO, Year, Title )
2. USER_SCHEME ( CARD_NO, Name, Address )
3. SUPPLIER_SCHEME ( S_NAME , S_Address )
4. BORROWED_BY ( ACC_NO, CARD_NO , Date of Issue )
5. SUPPLIED_BY ( ACC_NO, Price, Date of Supplied, S_NAME )


Now here we have a Database Defination! 

Instances:

Book(BOOK_SCHEME)

User(USER_SCHEME)

Supplier(SUPPLIER_SCHEME)


