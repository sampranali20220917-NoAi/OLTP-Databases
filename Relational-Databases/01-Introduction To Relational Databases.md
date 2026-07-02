We have heard of Relational Databases very very frequently. Almost every engineer on the planet knows at a high level what Relational Database stands for!

So, lets begin with the Boring defintion of Relational Database.

## Functional Definition:
A Relational Database is a System that stores Data in the Form of Tables (similar to excel/Google Spread sheets). It helps us to organize data cleanly in the format of Rows & Columns which is Structured Data. Data which Humans can read and understand without any extra effort.

## Technical Definition: 
A Relational Database is a System that stores Data in "Relations" i.e. "Tables" and uses a Special Language i.e. "Structured Query Language aka SQL" to manage and query data while enforcing and maintaining Data Integrity, Consistency Principles.

A Table is called a "Relation".
A Row in a table is called a "Tuple".
A Column in a table is called an "Attribute".

Relations are simple Correct!

Healthy relationships help people collaborate, grow, and solve problems together. In a similar way, relational databases thrive on well-defined relationships between data. Clear relationships make data easier to organize, query, and maintain.

For example:
Table 1 or Relation 1: Customer
Now what Attributes a Customer can have?
In plan language, what Characteristics a Customer can Have?
A Customer can be anyone -> what about Customer's Name, Address, Phone Number, Age, Does Customer has a Job etc etc, Unique identifier like an ID or Mark on the body (LOL).

| Customer ID | Customer Name |
|------------:|---------------|
| 1 | ABC |
| 2 | XYZ |

1, ABC & 2, XYZ is our Tuple or Row, the values for Attributes Customer ID & Name

Table 2 or Relation 2: Order
We have a Customer and now our Customer wants to order something.
We can have the following Attributes -> Order ID, Order Date, Order Amount etc

| Order ID | Order Amount |
|------------:|---------------|
| 1 | 500 |
| 2 | 1000 |

Now, how do we link Customer with Order.?
We will link Customer with order by creating a Solid, Beautiful Relationship.
This relationship is called a Parent-Child Relationship like Mother-son.

So, Customer is a Parent and Order is a child. Why? Because if there is no Customer, there will be no Orders! There can't be a child if there is no Mother (thats the natural process)

Hence, we will bring Parent to the Child and make the relation Official.
So my Relation 2 or Table 2 becomes

| Order ID | Customer ID | Order Amount |
|---------:|------------:|-------------:|
| 1 | 1 | 500 |
| 2 | 1 | 100 |

So, Customer ID helps us to link both Relations (Customer & Order) Together.

This is how Relational Database System works in real time projects and Applications by connecting n no. of Tables or Relation using the Parent-Child Relationship Philosophy. 

In next section we will understand what led Engineers to Create Relational Database Systems.