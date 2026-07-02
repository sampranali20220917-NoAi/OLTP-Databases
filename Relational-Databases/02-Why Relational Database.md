## What Problems People Faced Before Relational Databases?

- **Major Problem 1 – Data Redundancy**
  - Duplicate copies of the same data were stored across multiple files.

- **Major Problem 2 – Data Inconsistency**
  - Different copies of the same data often contained conflicting information.

- **Major Problem 3 – No Proper Relationships**
  - There was no clean mechanism to link related data across multiple files.

- **Major Problem 4 – Program–Data Dependency**
  - Even a small change in data structure often required changes in application code.

- **Major Problem 5 – Difficult Data Access**
  - Every new report or query required writing custom programs.

- **Major Problem 6 – Poor Data Integrity**
  - There was no systematic way to enforce business rules.

- **Major Problem 7 – Concurrency Issues**
  - Multiple users accessing or modifying data simultaneously often caused conflicts.

- **Major Problem 8 – No Transaction Management**
  - Operations were not atomic, making partial updates common during failures.

- **Major Problem 9 – Poor Scalability**
  - As data volume increased, systems became increasingly difficult to maintain and perform efficiently.

## How Relational Databases Solved These Problems

| Problem | Solution |
|----------|----------|
| Data Redundancy | Normalization and relationships |
| Data Inconsistency | Single Source of Truth |
| No Proper Relationships | Primary Keys and Foreign Keys |
| Program–Data Dependency | Logical and Physical Data Independence |
| Difficult Data Access | SQL |
| Poor Data Integrity | Constraints |
| Concurrency Issues | Locking and Isolation |
| No Transaction Management | ACID Transactions |
| Poor Scalability | Indexing, Partitioning, Replication and Query Optimization |
