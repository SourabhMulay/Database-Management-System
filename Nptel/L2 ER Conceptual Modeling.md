# Conceptual Modeling

There are some other interesting constraints! these help to characterise the mapping relationships!

**Mapping Constraints:**

we got these mappings between two binary relationships,

1. One - One Mapping
2. One - Many
3. Many - One
4. Many - Many


One - One is like each element mapped to exactly one element in other set! like from 1st set element x mapped to element y from other set! but it does not mean that it should be mapped!

One - Many mean x can be mapped to more than one element from other set! but other set elements can be mapped to only one from first set!

Many - One is opposite of above!! 

Many - Many is allowes bother of above!! like many elements from 1st set can be mapped to many elements from other set!!

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/558c2917-cba5-4a91-b9c7-617291fe20ea" />


<hr>

Now considering the element of Books to the Users how can we define these mapping constraints! lets see!

If On any entity we put the incoming arrow then the entity to other participate in one to one `or` one to many relationship!

<img width="1029" height="206" alt="image" src="https://github.com/user-attachments/assets/f53f6de1-bd8b-4368-ac83-181d5762174a" />

But if we have dont mentioned or dont have an arraow! then that entity participate in many to one and many to many relationship!!

<img width="894" height="123" alt="image" src="https://github.com/user-attachments/assets/3ae37348-2baa-4293-bf93-d28f90a7113d" />

So if the book and User relationship has no arrows then they are in many to one or many to many relationships! and if both has arrows then they are either in one to one or one to many!!


<hr>

#### Existence Dependencies

Suppose the relationship exist between customer and Account!!

Customer may have or may not have account. So suppose if we say that Account must be related to customer then the account's existence depends on the customer! so here the Customer is dominant entity and the Account is subordinate entity!! If the customer is removed the account is gone! becuase account's existence depends on the customer! If we want to ensure Customer must have account then we can do it other way around! 

<img width="1367" height="766" alt="image" src="https://github.com/user-attachments/assets/68a582c8-cb96-4540-ac43-64076bf69f74" />


<hr>

#### Key Attribute

**SuperKey:** A set of one or more attributes which taken collectively, allows us to uniquely identify an entity in an entity set!

In an example of Book data entity!! the Accession Number can be superkey and in Users data entity the Card No can be a SuperKey! So superkey identify the entity instance uniquely in an entity set!

A super key is any set of attributes that uniquely identifies a tuple (row) in a relation.

👉 It may contain extra attributes.
Example (User table):
User(CardNo, Name, Address, Status, Code)

If CardNo is unique, then all of these are super keys:

{CardNo}

{CardNo, Name}

{CardNo, Address}

{CardNo, Name, Address, Status, Code}

All uniquely identify a user.


**Candidate Key:**  This is a Super Key for which no proper subset is also a superKey!

To understand this!! Lets say User has attributes: (Card No. (Superkey), Name, Address, staus, code)..

Now if you start removing attributes (Name,....etc) so suppose it's still superkey then it's not candidate key.

So candidate key is ... It is a super key from which you cannot remove any attribute without losing uniqueness.

Apply this to your example

Assume:
CardNo uniquely identifies a user
Case 1: {CardNo, Name}
It is a super key (because CardNo is unique)
Remove Name → {CardNo}
Still uniquely identifies the user
❌ So {CardNo, Name} is NOT a candidate key

Case 2: {CardNo}
It is a super key
Remove CardNo → {}
No longer identifies a user
✅ So {CardNo} IS a candidate key


