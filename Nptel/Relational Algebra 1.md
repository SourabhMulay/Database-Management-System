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

