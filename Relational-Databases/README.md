We have heard of Relational Databases very very frequently. Almost every engineer on the planet knows at a high level what Relational Database stands for!

So, lets begin with the Boring defintion of Relational Database.

Functional Definition:
A Relational Database is a System that stores Data in the Form of Tables (similar to excel/Google Spread sheets). It helps us to organize data cleanly in the format of Rows & Columns which is Structured Data. Data which Humans can read and understand without any extra effort.

Technical Definition:
A Relational Database is a System that stores Data in "Relations" i.e. "Tables" and uses a Special Language i.e. "Structured Query Language aka SQL" to manage and query data while enforcing and maintaining Data Integrity, Consistency Principles.

A Table is called a "Relation".
A Row in a table is called a "Tuple".
A Column in a table is called an "Attribute".

Relations are simple Correct!

Good relationships help humans to thrive and co-exists. Good Relationships is actually helping Humanity to survive all the crap and curelity we currently face.

Relational Databases also work in the similar fashion. They thrieve on Good and Clear Relationships. 

For example:
Table 1 or Relation 1: Customer
Now what Attributes a Customer can have?
In plan language, what Characteristics a Customer can Have?
A Customer can be anyone -> what about Customer's Name, Address, Phone Number, Age, Does Customer has a Job etc etc, Unique identifier like an ID or Mark on the body (LOL).

Customer ID     Customer Name
1               ABC
2               XYZ

1, ABC & 2, XYZ is our Tuple or Row, the values for Attributes Customer ID & Name

Table 2 or Relation 2: Order
We have a Customer and now our Customer wants to order something.
We can have the following Attributes -> Order ID, Order Date, Order Amount etc

Order ID, Order Amount
1         500
2         1000

Now, how do we link Customer with Order.?
We will link Customer with order by creating a Solid, Beautiful Relationship.
This relationship is called a Parent-Child Relationship like Mother-son.

So, Customer is a Parent and Order is a child. Why? Because if there is no Customer, there will be no Orders! There can't be a child if there is no Mother (thats the natural process)

Hence, we will bring Parent to the Child and make the relation Official.
So my Relation 2 or Table 2 becomes

Order ID   Customer ID    Order Amount
1          1              500
2          1              100

So, Customer ID helps us to link both Relations (Customer & Order) Together.

This is how Relational Database System works in real time projects and Applications by connecting n no. of Tables or Relation using the Parent-Child Relationship Philosophy. 

What Problems People faced when there were no Relational Databases?
Before relational databases early 1970s, Engineers used file-based systems and hierarchical/network databases (like IMS, CODASYL). These caused several serious (“grave”) problems.

Major Problem 1: Data Redundancy i.e. Duplicate Data Every where
Major Problem 2: Data Inconsistency i.e. different copies of same data but inconsistent. 
Major Problem 3: No Proper Relationship between the Data i.e. No clean way to link data across multiple Files.
Major Problem 4: Strong dependency between Program and Data.
Major Problem 5: Difficult to Read and Access data i.e. for every new query Folks had to write New Custom code.
Major Problem 6: NO data Integrity.
Major Problem 7: Concurrency Issues i.e. if multiple users are trying to read the data, then there will be Conflict.
Major Problem 8: No Transaction Management i.e. no Operation was Atomic in nature.
Major Problem 9: Poor Scalability i.e. with growing data, systems were did not scaled well hence difficult to manage,maintain

How Relational Databases solved these Major Problems?
Solution for Major Problem 1: Normalization + Relationships.
Solution for Major Problem 2: Data stored in single place, i.e. Single Source of Truth.
Solution for Major Problem 3: Primary key + Foreign Key making data more structured and simple.
Solution for Major Problem 4: Data Independence at 2 levels
1st Level: Logical Independence: change schema without affecting queries much.
2ndLevel: Physical Independence: change storage without affecting applications.
Solution for Major Problem 5: use SQL instead of writing custom codes every time.
Solution for Major Problem 6: Constraints 
Solution for Major Problem 7: Concurrency control + Isolation (row/table level locking)
Solution for Major Problem 8: ACID Transactions
Solution for Major Problem 9: Improve Scalability by adding Indexes, query optimization, Partition, Replication etc.
