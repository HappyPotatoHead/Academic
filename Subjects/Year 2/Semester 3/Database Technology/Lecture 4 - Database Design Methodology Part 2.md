---
aliases:
  - Database Lecture 4
tags:
  - Notes
  - Database
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
# Analyse Transactions
This is to understand the functionality of the transactions to the database and to analyse the important transactions. 

To determine what makes a good performance, a set of criteria has to be inspected:
1. The importance of the transaction to the business
2. The frequency of the transaction
3. The time and day where there is peak activity on the database. 

# File Organisations
The whole point of this is to find the most optimal file organisation for each database relation. The file relation can come from:
1. Heap
2. Hash 
3. Binary Tree
# Indexes
The purpose of indexes are to speed up data retrievals or queries. However, it's benefit can only be seen when:
1. The table being queried upon is large
2. The The transaction does not involve scanning the whole table

Otherwise, the difference in speed is negligible. 

# Duplicating Attributes
There are instances where duplicating the attributes is acceptable. Such instances are when:
1. The addition of the attribute would reduce the overhead of querying another, separate table
2. The transaction result would be more meaningful
3. The transaction is common. 

However, this does not mean the original table is removed. It is still needed for times where an analysis has to be taken place. 
# Partitioning relations
Rather than combining relations together, an alternative approach is to decompose them into smaller and manageable partition. 

There are vertical partitions and horizontal partitions. 

In vertical partition, the focus is on the columns of the relations, but in horizontal partition, the focus is on the tuples of the relations. 

>[!EXAMPLE] The use of partitioning
>The more important partition can be placed in a separate place that allows quicker and easier access while the less frequent or less important partition can afford some time delay.

# Monitor and Tune the Operational System
Changes are made to correct design flaws and to shift with changing requirements. These changes are important to improve the performance of the system. 

To measure the efficiency of the system, some factors are to be considered:
1. Transaction throughput
	- The number of transactions to be processed in a given amount of time
2. Response time
	- The time taken to complete a single transaction
3. Disk storage
	- The amount of storage space to store database files
# Normalisation
A relation should contain minimal data redundancy and allows user to insert, update, and delete without causing data inconsistency.
There are 3 anomalies:
1. Insert anomaly
	- Inserting a new tuple results in data duplication
2. Update/modification anomaly
	- Updating a tuple would have to force the update of other tuples 
3. Delete anomaly
	- Deleting a tuple causes loss of information which may be useful for future tuples
## Dependencies
There are 3 types of dependencies
1. Fully functional dependency
2. Partial dependency
3. Transitive dependency

In **fully functional dependency**, all of the non-key attributes are dependent on only the key attribute. The values of the non-key attributes are dependent on the value of the key attribute.

In **partial dependency**, an attribute or a number of attributes is dependent A, but if some attributes were to be removed form A, the dependency still holds

In **transitive dependency**, a non-key attribute is dependent of another non-key attribute which is dependent on a key attribute. In a way, the *first* non-key attribute is dependent on the key attribute transitively.

## Normalisation
The purpose of normalisation is to produce a set of relations with desirable properties. In the process of normalisation, the anomalies - insert, update, and delete - can be removed. Normalisation can also prevent unnecessary duplication of data. 

Normalisation takes place in different forms:
1. Unnormalised form, UNF
2. First Normal Form, 1NF
3. Second Normal Form, 2NF
4. Third Normal Form, 3NF
5. Boyce Codd Normal Form, BCNF 
6. Fourth Normal Form, 4NF
7. *Succeeding normal forms.*

### UNF
In the unnormalised form, the relation is not atomic - multiple values in one field. There are also one or more repeating group in the relation.

To fix this:
1. Placing appropriate data in empty rows of columns containing the repeating data
2. Placing the repeating data along with a copy of the candidate key in a separate relation

### 1NF
The conversion of UNF to 1NF result in a table that has eliminated the repeating groups, multivalued attributes, and the attribute field values are atomic. 

### 2NF
The conversion from 1NF to 2NF results in multiple relations that eliminated partial dependencies. This means that every non-key attributes in every resulting relation is dependent on only the key attribute.

### 3NF 
The conversion from 2NF to 3NF eliminated transitive dependency.

### Boyce Codd Normal Form
Every determinant in the table is the candidate key. 

A good way to spot this is when a determinant determines the value of another determinant, and the other determinant determines the value of the former determinant. So, it's circular. 

### 4NF 
The conversion from 3NF/BCNF happens removes multivalued dependency. 

>[!DEFINITION] MVD
>This happens when an attributes determine the values of other attributes, but the other attributes are independent of each other. 

## De-Normalisation
This happens when normalisation results in awkward, and a compromise in performance that is unacceptable. 

Advantages:
1. Reduce the need for joins
2. Reduce the number of index
3. Reduce the number of foreign keys
4. Reduce the number of relations

Disadvantage
1. Faster retrieval, but slower updates
	- Since you would introduce update anomaly into the database. 
2. Compromised flexibility
3. Larger sized relations