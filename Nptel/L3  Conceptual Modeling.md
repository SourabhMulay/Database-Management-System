# Conceptual Modeling

We already have learned about KEY attributes (Superkey, Candidate key, Primary Key).

Now lets learn Concept of **Generalisation!**.

Consider a **TICKET** (In railway reservation system) can have several Attributes. (ATTR: Ticket No, Start, Destination, Date Of Issue, Fare, Distance). So this makes a Ticket! Now if we wanted to distinguish the reserved ticket or unreserved ticket or a express Ticket or a Normal Ticket! Now differentiating can be possible in many ways. For example if we have one more attribute Reserved/Unreserved to just identify if ticket is reserved or not! but is it suffice???? nope! It still don't make any sense till we have information about, if reserved then which train, what seat no, if any extra fare charge?  So we may have to saparate entity itself one is reserved entity Ticket and another is unreserved. But conceptually a lot of attr are comman. 

What we'll do suppose we have a **TICKET.** ans we have a `IS A` Relatationship!

<img width="1377" height="744" alt="image" src="https://github.com/user-attachments/assets/94415d1c-8a18-42cb-9e8c-a023392a3534" />


So now 2 type of special cases! Ticket can be reserved or unreserved. So ticket is generalisation of reserved and unreserved ticket. What about attribute?? So Comman Attributes will be on TICKET. (Start, Destination, Ticket No, Date of Issue) and the Other attributes is on those 2 entities.

**Reserved Ticket:** (Attr: Train No, Seat No, Fare, Reservation Upto....)

**Unreserved Ticket:** (Attr: Local/Express, Fare ...)

