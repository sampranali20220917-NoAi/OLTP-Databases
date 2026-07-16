## Partitions in SQL Server

## Meaning of Partitions
When we hear Partitions, it is very simple to visualize what it means. It means to divide or create some sort of layers which separate other objects from one another.

Like for example, Imagine entering an ice cream shop with hundreds of flavours. If every flavour were placed randomly, finding your favourite flavour would take a long time.

Instead, the shop groups similar flavours together. Mango flavours are in one section, chocolate in another, and strawberry in another.
Rather than searching the entire shop, you go directly to the Mango section.

SQL Server partitioning works in a similar way. Instead of searching the entire table, SQL Server can search only the partition that contains the required data.

Table partitioning is a technique used to logically divide a large table or index into smaller, more manageable pieces called partitions, while allowing the application to continue treating it as a single table.

Any table or index can be partitioned. However, partitioning is most beneficial for very large tables where data is naturally divided by a key such as date, region, or customer identifier.

## Objectives of Table Partitioning

Partitioning is primarily introduced to improve the manageability of very large tables.

Some of its major objectives are:

- Improve query performance through **Partition Elimination**.
- Reduce index maintenance time by rebuilding individual partitions.
- Enable fast archival of historical data using **Partition Switching**.
- Support rolling window scenarios for time-series and transactional data.
- Improve data management for tables containing millions or billions of rows.
- Reduce maintenance downtime.

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
Partition scheme acts as a mapping layer between partitions and filegroups.
It defines where to Place each Partitions(across filegroups).
For On-Prem SQL Server, we can specify 'N' no. of File group names.
For Azure SQL Database, the ONLY File group we use is **"Primary"** File group. 

## Key difference between Partition Function and Scheme is:
**Partition Function**: how to divide the data.
**Partition Scheme**: where to store the chunks of data 
