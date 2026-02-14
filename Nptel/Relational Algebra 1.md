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


Note: It should be Borrow.Acc_No not User.Acc_No.

<hr>

This is the database scheme we'll be using goin forward!

<img width="500" height="952" alt="Screenshot 2026-01-30 at 10 08 59 AM" src="https://github.com/user-attachments/assets/26d8da49-06ca-495f-aaa0-1fbc4fe3cbb4" />


1. INTERSECTION operation

   So if we have  r INTERSECTION s ! then it returns those tuples which are comman in both relations.

   suppose r have two attributes A and B and s also have same attributes and containing the data or tuple: (a,1). (b,3) and in s we have (a,1),(b,4) then the comman between both will be (a,1). and that is the result of Intersection.

   Now r INTERSECTION s can also been shown as `r - (r-s)`. (r-s) is nothing but those set of tuples in r which is not in s in our case (b,3) is such a tuple.


2. NATURAL JOIN

    <img width="500" height="100" alt="image" src="https://github.com/user-attachments/assets/098f04bc-30f1-4705-bd3e-270069e7ace4" />

   Suppose I have relation r and relation s. and If r INTERSECTION s == Null (Likely no comman attributues) then

   `r NATURAL JOIN s == r * s` and r * s is nothing but a Cartesian product! All attributes from r and s are combined in relationship table.

   Natural Join is useful when there is commanality between the attributes. Suppose take an example : r as relationship has "" A, B. C ""  as attributes. and s as a relationship has ""B, D "" as an attribues.

   Now `r NATURAL JOIN s` has attributes "" A, B, C, D "". and this is nothing but `r UNION s`.

   As here the B is a Comman Attribute. Suppose we take a cartesian product! (Combining one row of r with all in s) but here in Natural Join we need to check the comman attribute. It must match! it'll combine in natural join with one which has comman B's attribute value.

   for example:

   <img width="500" height="892" alt="image" src="https://github.com/user-attachments/assets/34754591-0715-40ae-92af-24ead126e547" />


   So it will only select those tuples where `r.B == s.B` and it'll project out `(r.A, r.B, r.C, s.D)`.

   This is very useful in many cases, So let's check some examples. We got the books and the Borrow relationships.

   Book: (Acc_No, YR_Pub, Title)

   Borrow: (Acc_No, Card_No, DateOfIss)

   So `Book NATURAL JOIN Borrow` has (Acc_No, YR_pub, Title, Card_no, DateOfIss). and here Acc_No is thre comman key or joining key.

   Finding the Title of all Books issued under Card No: F53!

   <img width="500" height="258" alt="image" src="https://github.com/user-attachments/assets/c1fa3cda-cb61-4487-926d-8925846a4c23" />

   Find out the Title of All Books issued by Vijay! (FROM USer: (Card_No, Name, Address).

   <img width="500" height="306" alt="image" src="https://github.com/user-attachments/assets/6fd74f2b-d979-4d1e-b372-a80f172c42ee" />

    But we can write it in other ways also:

    <img width="500" height="658" alt="image" src="https://github.com/user-attachments/assets/ebc0a731-aed7-4379-bddc-9774c5967e84" />


    Let's quickly understand what Natural Join does when there are more than 1 comman attributes:

   So lets have relation `r: (A, B, C)` and `s: (B, C, D)`.

   now `r NATURAL JOIN s` has (A, B, C, D). So here from r relation the (B, C) sub-tuple must match sith sub-tuple of s: (B, C).

   <img width="500" height="607" alt="image" src="https://github.com/user-attachments/assets/1a46a889-84f9-45ab-9e93-e2d39da8728a" />

   So in NATURAL JOIN if there are multiple comman Attributes then all must be matched to find tuples in resultant relationships. So we'll come back what we did already! we had a `( (USER JOIN BORROW) JOIN BOOK)` and we also had other option  `( (USER JOIN BOOK) JOIN BORROW ) ` so the question is are they identical? USER has got comman attribute with borrow that's a CARD_NO and the relationship (USER JOIN BORROW) got attributes and amongst all the ACC_No is comman with BOOK.

   And (USER JOIN BOOK) has no comman Attribute so it takes the cartesian product that has all the attributes and amongst all attributes the Card_No, Acc_No is cooman to BORROW. SO whatever you get out of 1st relationship is same as second. So WE Can say that `the NATURAL JOIN Operation is Not only associative Operation but also Communtative Operation.`

   Take REF:

   <img width="500" height="545" alt="image" src="https://github.com/user-attachments/assets/29187808-20ae-43e2-a7ba-f8a27447457e" />

   Lets see one QUERY: FIND out the Names of All Supplier Who have Supplied Books Issued By Vijay.

   We have to find out name of Supplier... Supplied By realtionShip has (Acc_No, Supp_Name).. so Acc_No is primary key again.... User schema has (Card_No, B_Name, B_Address) and Borrowed_By has (Acc_No, Card_No) so between two relationships the Card_No is comman! so we can take NATURAL JOIN Of (USER WITH Borrowed_By) and that gives us a Comman attribute ACC_No. and again if we take Natural Join of these relationship with SuppliedBy then we can find out the Supplier Name because ACC_NO is one of attribute that matches with recent relationship..

   Overview:

   USER ( Card_No, B_Name, B_Address ).

   Borrowed_By ( ACC_NO, Card_No, DOI ).

   USER NATURAL JOIN BORROWEDBY will give us (CARD_NO, ACC_NO, DOI, B_NAME, B_ADDrs ).

   SUPPLIED BY (ACC_NO, S_NAME, PRICE, DOS).
   
   and NOW ( (USER JOIN BORROWED_BY) JOIN SUPPLIED_BY)  Has ACC_NO as Join KEY. So we can easily find out the Supplier Names.
   
   So,
   
   <img width="500" height="427" alt="image" src="https://github.com/user-attachments/assets/ef366d2b-786a-4151-87a6-757d4fb6fc15" />


   

   
   

   

   

