# Relational Calculas

Now we have learned the relational algebra! and it helps us to get relations as an outcome of the operations we perform on them! Likely suppose you are projecting out some column from relation r where columna = 'z'. Likewise it return something as an outcome.

This is Procedural in nature means "what are the sequence of steps required to obtain the desired outcome".

**Relational Calculus is another language to define relations in a database. and It also forms Basis of Query Language. and It's Non-Procedural in some sense. So order to expressed it does not require the sequence of steps at some point.**

**Relational Calculas uses the concept of Formal Logic to express relational Queries.**

there are two well known formulations:

1. Tuple Relational Calculas
2. Domain Relational Calculas


We'll be discussing the Tuple Relational Calculus.

## Tuple Relational Calculus.

The relation has been expressed as:

> { t  | p(t) }

this is represented in set format. the "t" is tuple variable and "p(t)" is predicate which must be TRUE for every element of the SET. i.e "p(t)" must be TRUE for each tuple in:

> S = { t | p(t) }

Lets get back to the our Defined Database Scheme:

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/9153f2f3-dd41-47ce-95a6-b86b38df1217" />


A Tuple relational calculus relation will look like:

> S = { t | t ∈ Book ^ t[YR_PUB] = '1991' }

or

> S = { t | t ∈ Book ( t[YR_PUB] = '1991') }


This Set S has all attributes of Table Book. There are other ways also to get subset of books. and For every tuple of S the relation   `( t[YR_PUB] = '1991') ` must be true. So the New Relation S contain the Books published in 1991. 

 

