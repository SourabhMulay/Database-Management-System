# Conceptual Modeling

We already have learned about KEY attributes (Superkey, Candidate key, Primary Key).

Now lets learn Concept of **Generalisation!**.

Consider a **TICKET** (In railway reservation system) can have several Attributes. (ATTR: Ticket No, Start, Destination, Date Of Issue, Fare, Distance). So this makes a Ticket! Now if we wanted to distinguish the reserved ticket or unreserved ticket or a express Ticket or a Normal Ticket! Now differentiating can be possible in many ways. For example if we have one more attribute Reserved/Unreserved to just identify if ticket is reserved or not! but is it suffice???? nope! It still don't make any sense till we have information about, if reserved then which train, what seat no, if any extra fare charge?  So we may have to saparate entity itself one is reserved entity Ticket and another is unreserved. But conceptually a lot of attr are comman. 

What we'll do suppose we have a **TICKET.** ans we have a `IS A` Relatationship!

<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/94415d1c-8a18-42cb-9e8c-a023392a3534" />


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

<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/8b61994e-9b53-4f7e-be47-fd98e068ef3c" />


Now there maybe conceptual problems over here! we have multiple relationships here and TEACHER TEACHES SUBJECT so we have TEACHES relationship but again which books Teacher used to teach, so to identify TEACHER USES Book1. So this shows us which book Teacher USES but again now sure for which subject? So we done this to only get an answer or statisfy the Statement that **" TEACHER USES BOOK b1, b2 to TEACH SUBJECT T1 "**. The sole purpose is to establish the relationship between the Entities  "TEACHES" and "USES". but normally we do not allow the relationships between the RELATIONS and RELATIONS like in our case TEACHES and USES that is why we forced to model this above entities. and one more thing to note that the RELATIONSHIPS ENTITIES comprises the Set of Attributes from Both TEACHER or SUBJECT or BOOKS. So whatsoever relationships are build on the top of these tables will comprises the comman attributes of these tables. So considering one BIG ENTITY comprises the (TEACHER, TEACHES, SUBJECT) we can say the ENTITY is 
aggrigate entity of itself and his relationships!

Why we have used the aggregation! ??? 

The reason is if you looked at the above diagram (Conceptually) so we dont have to model one scneario where if teacher aint teaches subject s1 but teacher used the book b1 for subject s1. so that's not what we wanted to model. we dont want that, we want "TEACHER USES Book B1 to TEACH SUBJECT S1". but the above conceptually can model "TEACHER DONT TEACHES SUBJECT S1 BUT USES BOOK B1 FOR SUBJECT S1". So aggregated entity Model it better conceptually. **So aggregation allowed us to RELATE or map RELATIONSHIPS with RELATIONSHIPS.**


<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/5ce725eb-d31b-4f23-a1a4-17320008b6e5" />




