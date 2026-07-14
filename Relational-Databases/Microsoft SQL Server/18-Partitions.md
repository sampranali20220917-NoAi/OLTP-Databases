## Partitions in SQL Server

## Meaning of Partitions
When we hear Partitions, it is very simple to visualize what it means. It means to divide or create some sort of layers which separate other objects from one another.
Like for example, when we go to an Ice-cream store, there are "N" no.s of ice-creams available. Of course we can't eat all the ice-creams at once (we need to be the Owner of the Shop or brand for that matter!! :))

But let say we want Alphanso-Mango ice-cream.

Now, there are 100's of ice-cream infront of me in the shop. If I will try to go to each flavour and check which one is Alphanso-Mango, then that will probably take me couple of Hours. I may take more hours to find my ice-cream because I am not the only one who wants Ice-cream. There are other folks too who wants to have the same flavour. They will not wait for hours for me to search and get my beloved ice-cream. 

There got to be some way to make my search optimize and quick.

So, instead of going through all the flavours one by one I will go to the section only where Mango Flavours are kept. Correct!

I won't have to search all the shop. I will go to only that block or designated area in the shop where they keep Mango Flavours together. 

So, that way I will take only couple of minutes, instead of hours to get my ice-cream.

What is happening in the shop is: each flavour is Partitioned or Separated from each other. So that whoever comes, they can get their ice-cream as soon as possible. That way every one gets what they want plus there is no rush or traffic in the shop. People can buy ice-creams parallely.

This is what Partitions mean in SQL Server too.
It is a Meta-data Management Activity which helps us to retrieve the information or Query result much faster because it doesn't have to scan the entire table. It will seek only the rows where Our requested Data lies in th given Partition.

We can apply Partitions to 'N' no. of tables in SQL server but, in general they are applied on dataset which has Humoungous data. Like 100 million rows or on a Table which is populated every 1 hour with a decent amount of data frequency and an Application is running queries at the backend to fetch results and there are parallel users who are also trying to get the same data from the same table and that is resulting in Application Time out issues or Query performance issues.

## Objectives of Partitions:
SQL Server Partitions enables efficient query performance, manageability, and scalability of large tables by implementing table partitioning.

**Partitioning will**:
*   Improve query performance through **partition elimination**.
*   Improve **maintenance operations** (index rebuild, truncate, switch).
*   Support **data lifecycle management** (archiving, rolling window data).
*   

## Technical Terminologies for Partitions:
- **Partition Function**:
Its a column which is decided for Partition data life cycle as well as query filter. The most commonly used Partition Function key are date columns because most of the Fact tables or Transactional tables filter there data based on Date columns. So Date column becomes an Ideal candidate for Partition column.
For example, in my day to day work 95% of the time data is fitered or queried on Date column.
(Note: it doesn't mean, we should only use Date cols. No. We can use any column for Partitions. But depending on the Table usage and what type of data it is storin, we should make the decision.)

Partition Key works in two different Ranges. **Think of Range as when data comes to which Bucket it should go to**.! Because each partition works like a Box and we define boundary value for each box.
When we create partition Function, we must decide to which boundary the data should go into

1. **Left Range**: let say we have these dates as an example. 2023-12-31,2024-01-01,2024-01-02,2024-01-03.
How SQL Server assigns Partitions if used Left Range:
Partition 1: < 2024-01-01, this includes 2023-12-31
Partition 2: >=2024-01-01 and <=2024-01-02 (because boundary 2024-01-01 belongs to the left)
Partition 3: >=2024-01-02 and <=2024-01-03
Key Rule for Range Left is, **The Boundary value belongs to the previous Partition**.

2. **Right Range**: same date range we have, 2023-12-31,2024-01-01,2024-01-02,2024-01-03.
How SQL Server assigns Partitions if used Right Range.
Partition 1: everything which is <= 2024-01-01
Partition 1: will also have 2024-01-01
Partition 2: >2024-01-01 and <2024-01-02
Partition 3: >2024-01-02 and <2024-01-03
Key Rule for Range Right is, **The Boundary values belongs to the next Partition**.

In Practise, Left range is to be used when we want our Boundaries to close previous Buckets and Right Range is to be used when we want our Boundaries to add or open new Buckets.

- **Partition Scheme**
Partition scheme works like a Map which maps or tells SQL Server which filegroup each partition of table or index should stay or Live in!
It defines where to Place each Partitions(across filegroups).
For On-Prem SQL Server, we can specify 'N' no. of File group names.
For Azure SQL Database, the ONLY File group we use is **"Primary"** File group. 

## Key difference between Partition Function and Scheme is:
**Partition Function**: how to divide the data.
**Partition Scheme**: where to store the chunks of data 
