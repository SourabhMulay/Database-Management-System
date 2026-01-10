"""""

`DATABASE SCHEME:`

1. BOOK_SCHEME ( ACC_NO, Year, Title )
2. USER_SCHEME ( CARD_NO, Name, Address )
3. SUPPLIER_SCHEME ( S_NAME , S_Address )
4. BORROWED_BY ( ACC_NO, CARD_NO , Date of Issue )
5. SUPPLIED_BY ( ACC_NO, Price, Date of Supplied, S_NAME )

Now here we have a Database Definations!

`Instances:`

1. Book(BOOK_SCHEME)
2. User(USER_SCHEME)
3. Supplier(SUPPLIER_SCHEME)
4. Borrow(Borrowed_By)
5. Supplier(Supplied_By)

"""""

# Relational Algebra

**Concept of Relation:**

We'll Quickly review the relational model...

Suppose `K = (A,B,C)` and each is SET of Attributes.

For each we have domain of attributes and Domain of Attribute is defined as DOM(A), DOM(B), DOM(C).

`DOM(A) = {1,2,3}`

`DOM(B) = SET Of all Strings OF Length = 50`

`DOM(C) = {'Saurabh', 'Sarah'} `

**So now `Relation R` of Attribute (A and B) is Subset of `DOM(A) * DOM(B)`. (Cross Product).**

So relation have both A and B and have all possible Combinations of Values from A and B.

Suppose we have BOOK: (Acc_No, YR_PUB, TITLE). (assume table has data). and Suppose Acc_no is integer values < lakh and TITLE is String of length upto 50. So i can say that now Title can be the subset of all Strings which length upto 50 and valid for other attributes as well which are in table with diff data type with given constraints. Book relation is subset of all those possible values but valid one with available books in the library! Each row is called a `Tuple` in relation.

<hr>

Relational Algebra is formal query language based on set of Operations on Relations! it's a procedural query lang. 

Fundamental Operations: 

1. Select
2. Union
3. Project
4. Set Difference
5. Rename
6. Cartesian Product


Addtional Operations:

1. Natural Join
2. Division/Quotient
3. Intersection
4. Assignment
5. Theta - Join

<hr>

`Select Operation:` It has purpose to identify the Set of Tuples in table to extract out. It shows in symbol "Sigma".

<img width="500" height="160" alt="image" src="https://github.com/user-attachments/assets/bf050848-e18c-4ad5-9b19-aa23e3871be2" />

So now above we say, Select all the books where YR_PUB = 1992. So this select operation will return a table of relation contain specific Tuples as per the constraints.

Another Example could be:

<img width="500" height="260" alt="image" src="https://github.com/user-attachments/assets/94256c6a-c81a-4fdb-bd04-0fb36d863e5c" />

This shows rhe standard boolean expression. ( ^ shows AND Operation ).

<hr>

`Project Operation:` It identify as Symbol Pi. Its differ than select in many ways.

This work as SET! So it whatsoever data it return won't have the DUPLICATES.

Pi (Acc_No, Title)  (Book). 

So it does project On Acc_No and Title or certain attributes which we mention in project Query. 

<img width="500" height="396" alt="image" src="https://github.com/user-attachments/assets/1fffc0ce-14e0-4230-99f8-7204c451efa5" />

So the second query mean: Find out All Books Titles (Unique) which has YR_PUB > 1992. 

and 3rd query mean PROJECT Title and YR_Pub from Book and then select from that table where YR_PUB = 1991.

<hr>

`The Cartesian Product: (X)` 

It's not possible combination of individual attributes of tables but the Tuple Tuple combination. (Like row0 from table 0 to all tuples/rows from table 1)

Suppose one table got attribute 'A' and the Other Table has attribute 'B'.

a has values {1, 2, 3} 

b has values {A, B}

So now the Cartesian product is nothing but combination of values/tuple of both of the tables. So we'll get the resultant table having both attribute 'A' and 'B'.

`(A,B) = {(1,A), (2,A), (3,A), (1,B), (2,B), (3,B)}`.


Lets have relation 'r' having attributes (A,B) and lets have relation 's' having attributes (B,C). So the (r X s) shown as :

Domain is nothing but possible values of attributes!! So here and in cartesian product case, `(r X s) != DOM(A) * DOM(B) * DOM(c).`

<img width="500" height="451" alt="image" src="https://github.com/user-attachments/assets/04238ca0-e3ae-47ac-94cb-bc38a2f80dea" />


<hr>

> Find the Acc No Of All Books issued by Saurabh. 

Referance to above Relationships mentioned! We need (USER X Borrow) to have all possible combination of user with borrow relation.

r = USER X Borrow

**r Has Attributes:**

User.Card_No, User.B_Name, User.B_Address, Borrow.Acc_No, Borrow.Card_No, Borrow.DateOfIssue. 

Now i can say that "Saurabh" as user share one unique Card_No. and I can say that i need my relation or cartisian product outcome to have filter or tuples must have same Card No as user. So when i get the same Card_No then only i'll return those Acc No's.

So I can say now, `User.Card_No == Borrow.Card_No AND User.B_Name == 'Saurabh'.` These conditions must statisfy to collect the required tuples from table.

and we'll project out only the Acc No.

<img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/d140d75f-181f-4f01-ac27-7eed8ca433d6" />




