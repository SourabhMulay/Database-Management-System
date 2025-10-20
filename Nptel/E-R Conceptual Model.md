# ER MODEL (Entity-Relationship Model)

So model contain the entity, the attributes of entities and the relations!! and this is conceptual model to conceive the structure of database! and also it helps to identity the contraints that occur in integrated design of complete database system!

**Concept of Entity:**

An entity is a distinguishable object of a Database! (hmmmmm .... not fully get it right!)

Lets see some of the examples: (LIBRARY)

So in Library. Assume any perticular book,

**BOOK:**

`Compiler design by Aho,Ulimen ,pub by: addison wiseley, acc No: 732756, call no: 001-3276`

so this is clear distinguishable element of Library and it's one of the entities.

Another you can have,

**USER:**

`Ajay Kumar Singh, Project Staff, Cyrogenic Dept, Card No: c-124`

This is also a one of distinguishable entity of library!

another you can have,

**Supplier**

`M/S Narisa Book Distributor, 53 Syed, Amir ali Avenue, Cal-53`

and there might be several other entities!

So each such distinguishable object, which can be identify for perticular DB is called as an entity! So they can have same structure as a BOOK, PERSON, SUPPLIER, USER! 

**So all those entities which has same type or structure they form an Entity Set!**

### **Attribute:**

Attribute is mapping from an entiity set to a Domain!! 

More clear:
<img width="1149" height="330" alt="image" src="https://github.com/user-attachments/assets/ba77c796-9f9d-45bd-94bd-01383024477a" />

Considering an Example of Entity set: Student. (which has Name, Roll No)

So suppose (s1 has name: Ak and RollNo: 1), (s2 has name: Bk and roll no: 2) , (s3 has name: Ck and rollno: 3). so now here,

Entity Set `E = {s1, s2, s3}`

`Domain of Name = set of all strings`

`Domain of Age = set of all integers`

So attribute specify the part of an entity structure! and it's a mapping from an entity set to a Domain of Values!!

So consider another example:

Entity Set **Book:**

1. Name/Title (STRING) This is maapping from entity set book to a STRING!! 
2. Author (STRING)
3. Year of Publication (DATE)
4. publisher (STRING)
5. Acc No (INTEGER)
6. Call No (STRING)

So, Each entity (like one row) gets assigned one value from that domain (like one possible value from the allowed set). and possible values in allowed set can be (STRING, DATE, INTEGER, FLOAT)!!

Now i think you're understanding a bit!


### Relationship

> This is Association or a Mapping between Entities!!

So if we have two entities `Book` and `User`!! and if the book has been issues by k user then this can be shows using relationship `Borrowed By`!


