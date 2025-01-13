A new langs got introduced for db but most famous one was cobol.(comman business oriented lang) and FPS was most famous that time!!!

##### FPS (File processing System):

For example we have a Registeration dept , exam dept and the library dept. each dept has his own program and files. Now the problem here is suppose we have student name and roll no to save. This name and roll no must be comman in three but that was not the case with fps. and suppose the roll no changes or any one of students roll no changed and it does not reflected in exam dept but updated in other dept.

So this is redundant data!! that is the first problem and same data has stored at multiple location that is conflicting with each other...This is inconsistancy. and Inconsistency occur because of redundancy. Inconsistency cause by redendancy.

**Program Data inter dependancy :** We have desinged the application programs based on the files. Now if we changed any one of we need to change the other and it is interdependancy which is not logical at all.
So FPS rejected and DB approach got introduced where all programs controllled or reach to DBMS and DBMS integrated with shared Database. (Kind of shared collection). Relational data get stored (Logical data).DBMS is huge collection of softwares, It manages the users (security wise,who can acess what) and it manage the data.

**Advantage:**

1. Data sharing
2. Reduced Redundancy. (It reduces but not completely vanish)
3. Program data independance.
4. Better data Integrity.( Integrity mean Correct)
5. Better Data Consistency.

Data Base Environment:

<img width="498" alt="image" src="https://github.com/user-attachments/assets/1917258d-9bf5-4350-91c5-1767ad38d07e" />

<hr>

In dB World you can visualised data as a..

1. Real world data
2. Metadata (data about data). The first word (Data) is structure and second data is actual data.
   Schema is nothing but metadata!!!
   extra data needed to store data thats called metadata.

   like for example: we store real world human data using follow metadata.
  ``` c++
   struct human{
     isman;
     iswoman;
     name;
     age;
   }
  ```
   likewise.
   
4. Data Occurances is nothing but instance of data.

#### DBMS Architecture:

It is a Three level architechture and It is same throughout all databases. So architecture is same throughout...

<img width="401" alt="image" src="https://github.com/user-attachments/assets/491a55f5-5dfb-40c6-89d0-c499fcd1d4f3" />

We have at external level External views....For example if we have 50 column table!! to store the data so that table is logical or conceptual view. Now suppose you have multiple dept in your company, You cannot show to every dept this whole columns. So logical and conceptual views gives us an bais to view  external views. (or desired data view). View is what we see...Table along with data and Schema is nothing but Empty table!!!

**External Level:** It has multiple external view which are independant, so 50 columns can destributes 10 10 column wise section and one cannot affect other!!! This views maybe one for sales team then another view is for your engineering team , another one for marketing. Like wise so each external view can be own by single user group.

**DBA or databases Admin has Logical/Conceptual View:** What data we have stored in databased is shown by locgical and conceptual view. 

###### and How data stored in database is shown by Physical/Internal schema/view.

The complete description of data is given by logical view so it sometimes called as a Community view!.

**Internal/Physical view:** Every algorithm,,,Data compression..hashing..encryption...decryption...indexing stored here in this schema.

Here changes at one level does not affect...Especially...changes at lower level will not affect upper levels. Thats how here we acheive data independancy.
