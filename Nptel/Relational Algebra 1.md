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



