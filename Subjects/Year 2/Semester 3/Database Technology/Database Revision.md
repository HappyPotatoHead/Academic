---
aliases: 
tags:
  - Notes
  - Database
  - SQL
  - DBMS
  - DDBMS
  - NoSQL
  - BigData
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
# Lecture 1
Database Concepts
1. Data 
	- raw facts that does not serve much purpose out of context
	- Example, \<dates>
2. Information
	- Data that has been given context
	- Data that has been processed
	- It is more useful now
		- Give examination context
3. Knowledge
	- The ability to know when to apply information
	- Apply the examination dates when making a studying schedule to determine which subject should be prioritised first.

File-based approach
What is a file-based approach? 
Each department or area has their own application that manage and process their respective data, isolated from one another. 


1. Separation and Isolation of data
	- This can lead to data inconsistency
	- If two data that is related, but in a separate, isolated environment, the changes to one data may not be propagated to the other side of the data
2. Duplication of data
	- Since each application is isolated, copies of the same data has to be made if there are more than one department or section that requires the same data.
3. Incompatible file format
	- Since each application is isolated, they may have their own method in managing and processing the data.
	- An issue can happen when one department requests data from another department, and the format of the data sent is not the same, resulting in additional overhead in converting the file format to a compatible one
4. Inefficient use of storage
	- A lot of the same copies of the data will be made


Database - Collection of logically related data and a description of the data (meta data) to meet the organisation's information need. 

DBMS (Database Management System) - software that create, define, maintain, and control access to the database.
(Advantages)
	- Recovery services (roll-forward, roll-backward, deferred update, shadow paging, immediate update) (Persistent/Durable)
	- Security services (authorisation, roles, responsibility, view) (Secure)
	- Concurrency control (Locking, Timestamping) (Shareable)
		- Multiple users can access the database at the same time
	- Highly sharable (The existence of Distributed DBMS that allows multiple geographically distant sites to have access to the database) (Shareability) (Massive)
		- Multiple users can access the database at the same time

Disadvantages
1. Complex
	- Depending on whether it is NoSQL or SQL, a new syntax, method of querying has to be learnt.
	- Relational database has SQL language in order to perform operations on the database
	- Non-relational database has multiple types: Key-value based, document-based, column-based, and graph-based types
	- A lot of things to learn
2. Hardware and software costs
	- A stable and powerful infrastructure is needed to create a durable database
	- High investment cost
	- A strong network or server has to be maintained which also increases the costs to build a powerful network
	- Certain DBMS require subscription or licensing to fully utilise its capabilities
3. Costs of conversion
	- Hire trainer to train staffs on how to use the new technology
	- Replacing old tools and technology with a new one
	- Existing data is huge and converting them to fit with the new database system can be difficult and costly. 


ANSI-SPARC Architecture
3 levels in ANSI-SPARC Architecture
1. External level
	- User view of the database
	- Each user can have his or her own customised view of the database
		- This points to ANSI-SPARC's characteristics 
			- Customisable View
2. Conceptual level
	- Community view of the database
	- Refers to what kind of data is being stored and the relationships
3. Internal level
	- Refers to how the data is being physically stored
	- Physical representation of the database in the computer

What ANSI-SPARC Architecture does is that it separates user from the inner-workings of the database. Database administrator can make changes to the database storage structure without affecting the external observable behaviour of the database. Or they can make changes to the database physical aspect without affecting the internal structure of the database 

External level -> External schema
Conceptual level -> Conceptual schema 
Internal level -> Internal schema

DBMS functions 
- Query Processing
- Concurrency control
- Security control
- Data Communication services
- Recovery services
- Data Dictionary

Database Architecture
- File-Server Architecture
	- The server is the one that stores the data files
	- Each workstation has a copy of dbms and does the data processing
	- Issues
		- Hardware requirements
			- Since the workstation is the one that handles the data processing, each workstation has to be powerful enough.
		- Redundant copies
			- Each workstation has a copy of DBMS and 
		- Integrity, Recovery, and Concurrency control is more complex
			- Each workstation is independent from one another. 
			- Changes made to the file server may not be controlled
		- Burden on the network traffic
			- Multiple work station is downloading files from the same file-server
		- Not scalable
			- Centralised system
			- Workstation is expensive
- Client-Server Architecture
	- It is an architecture where the client handles the presentation logic and application. The server contains the database and handles data access logic. 
	- Tiers of architecture:
		- 2-Tier
			- One client and one server
		- 3-Tier
			- One client server
			- One application server
			- One database server
		- N-Tier
			- Additional web server

OLTP vs OLAP
OLTP is more efficient for high volume, simple transactions while OLAP is more efficient for lower volume, but more complex transactions. OLTP is more commonly found in day-to-day transactions such as cashiers in the supermarket while OLAP is more commonly found in analytical setting where complex queries are commonly found. OLTP typically has normalised datasets where high throughput and data integrity is important while OLAP has denormalised dataset because of its nature in handling complex transactions involving vast amount of data; it makes retrieving data easier and quicker.

Distributed Database 
- Database (collection of logically related data and description of the data)
- Distributed (the data is fragmented and physically placed at different sites over a network)

Distributed DBMS
- Control unit of the distributed system

Distributed processing
- Allows multiple users at different sites to access the centralised DBMS

Characteristics of DBMS
1. Collection of logically related data and description of the data
2. The data is fragmented
3. The data can be replicated
4. Each fragment is then distributed to multiple sites
5. The sites are connected via a communication network
6. Each site is managed by its own DBMS
7. DBMS handles local app autonomously
8. Each DBMS is a part of at least one global application 

# Lecture 2

ERD is not enough to capture of all of the information needed in the system. 

Imagine this, there are multiple roles under Employee. If the database is built from the ERD, the relations would have a lot of null values, since each role under Employee would have their own special attributes and relationships. 

This is where EER comes in; EER will implement inheritance (specialisation and generalisation)

In EER, `Employee` would be consider a super type. Supertype refers to a generic entity type that contains the common attributes and relationships that the subtypes will inherit. Subtype like `Programmer` will have its own specific attribute like `programming_language` and his own relationship. With inheritance, the subtype is able to inherit the attributes and relationships of the supertype while allowing the subtype to have its own unique attributes and relationships. 

To determine subtypes from supertypes:
1. Generalisation
	- A bottom-up approach
		- Determine the generic entity type from the specialised types 
		- Identify common attributes and relationships in each of those entity types
2. Specialisation
	- A top-down approach
		- Determine the subtypes from the supertypes
		- Identify the special attributes or characteristics

Subtype can only exist in the context of a supertype. A subtype can also be a supertype of another entity type (multilayer inheritance)


subtype discriminator
1. Disjoint
	- An instance of a supertype can only be a member of one subtype
		- A person can only be a doctor without being a computer scientist at the same time
2. Overlap
	- An instance of a supertype can be a member of more than one subtype
		- A person can be a student and an employee
3. Partial
	- A member of a supertype may not belong to any of the entity types
		- A person may not have any of the roles
4. Total
	- A member of a supertype must belong to at least one of the entity sub types
		- An employee in a company will have at least one role

Superkey
- attribute or a set of attribute that uniquely identifies a tuple in a relation
Candidate key
- Reduced superkey. When removing an attribute from a superkey no longer makes it unique
Primary key
- Attribute that uniquely identifies a tuple in a relation
Foreign key
- Attribute that is used to maintain a relationship between entities in a database system
Surrogate key
- A primary key that is created to uniquely identify a tuple in a relation if there is no other suitable keys
- No real meaning or relationship to the record 

Constraints

Integrity constraints
1. Entity integrity
	- Involving primary key
	- Each relation in the database system
		- Primary key has to be unique
		- No repetition
		- No null
	- Composite key
		- Can involve multiple attributes
2. Referential integrity
	- Involving foreign key
	- The value of a foreign key must match the value of a candidate key or a primary key of another relation
	- Can be nullable
	- Enforcing
		- Cascade update/cascade delete
		- No action
		- Set null
		- Set Default

Domain constraints
1. Check
	- Ensure that the fits within the domain set for the attribute
2. Unique
	- Ensure that the value for every tuple in the attribute is unique
3. Not null
4. Default
	- Provide a default value if no specified value is set

Base relation
- A named relation that corresponds to an entity in the conceptual scheme where the relation is physically stored in storage
View
- A dynamic relation that is generated on user request. 
- It is a virtual table
- It is not stored physically
- Each user can have his or her customised view of the database
- Essentially a subset of the database
- Issues:
	- Update
		- Views are only updatable if:
			- SELECT clause only uses field names; no functions and calculations
			- Involves one relation with the primary key
			- Does not involve multiple relations
			- Does not have GROUP BY clause or ORDER BY clause
			- No nested query
	- Structure
		- Views are only limited to specific attributes and tuples 
		- In base relation, the user is shown every attributes and tuples
	- Performance
		- It is a virtual table that is generated dynamically upon request
		- Can slow down performance if there are a lot of users who are generating views

# Lecture 3

# Lecture 4

# Lecture 5

Transaction properties:
1. Atomicity
	- It is an all or nothing property where all of the operations in a transaction has to be applied or none of them are applied.
	- Example
		- There is a transaction that will withdraw 50 dollars from the savings account and transfer 50 dollars to the check account. If an error occurs after the withdraw transaction, and before the transfer transaction, both operations will not be committed
2. Consistency
	- Committed transaction must bring the database from one consistent state to another consistent state
	- Example
		- After both operations are committed into the database, the new value in savings and checking must be applied.
3. Isolation
	- The partial effects of incomplete transactions is not visible to other transaction
	- Example
		- Assuming there is another user who is trying to view the savings and check accounts amount while the transferring transaction is still ongoing. The user will only be able to see the values before the transfer or values after the transfer. The user will not be able to see an instance where 50 dollars has been deducted but not yet added to check.
4. Durability
	- The effects from committed transaction is not lost or undone in the event of a future failure
	- Example
		- The new amount in Savings and Check is not changed after a failure in the future.

Concurrency control is the process of scheduling transactions in a way that prevents them from interfering with one another. 

Issues if there is no concurrency control:
1. Lost update
	- When the effect of a committed transaction is overwritten by another user.
	- Example
		- An initial value of 100$. One transaction is attempting to withdraw 50\$ while another transaction is attempting to deposit 50\$. If not managed, depending on the relative timing of the execution of the transaction, the value would either be 50\$ or 150\$
2. Uncommitted Dependency problem
	- This happens when a transaction is allowed to see the intermediate results of another transaction before it has committed.
	- Example
		- An initial value of 100\$. One transaction deposits 100\$ but it aborts before committed. At the same time, another transaction wants to withdraw 50\$. If there is no concurrency control, the other transaction will be withdrawing from 200$ rather than 100\$
3. Inconsistent Analysis Problem
	- The other two revolves around updating the database
	- An error can still occur if one transaction is allowed to read the partial effect of an uncommitted transaction
	- Example
		- A transaction is used to read and total the balance from check account and savings account. At the same time, a transaction is withdrawing from the savings account. If the first transaction reads from the savings account before the update transaction has committed, it would end up with the wrong total.

Serialisability
- Scheduling the transactions in a way that does not interfere with one another. 
Schedule
- A sequence of read/write operations from a section of concurrent transaction that preserves the order of execution in each transaction
Serial schedule
- A schedule where operations in a set of transaction executes consecutively without interleaving. 

In transactions that read/write the same data item, the order of execution is extremely important. 

Non conflict serializable -> the transactions cannot be ordered to ensure serialisability. Draw the precedence graph.

Concurrency control techniques
1. Locking 
2. Timestamping
These techniques are pessimistic, which means they are used to prevent conflict
Optimistic, check for conflicts only at commit. 

Locking
Can be applied on the entire database, row, relation, attribute, ...
- Binary Lock
- Exclusive Lock/Shared lock
	- Exclusive lock is for writing
		- Only one transaction can have exclusive lock on the data item at a time
		- No other transaction can read or write
	- Shared lock is for reading
		- Multiple transactions can have the same shared lock on the data item
		- No other transaction can write

2PLP
Growing phase
- Transaction is only allowed to request locks
Shrinking phase
- Transaction is only allowed to release locks

Prevents releasing locks too early. Causes non-serializable schedules. Can prevent concurrency control issues

Locking also introduces deadlock. Where two or more transactions is waiting for locks held by each other to be released. Can happen due to hold and wait. No 2PLP protocol. 

To deal with deadlock there are three methods:
1. Timeout
2. Deadlock Prevention
	1. Transaction timestamp
		- Wait-die
			- Only older transaction waits
		- Wound-Wait
			- Only younger transaction waits
3. Deadlock detection and recovery
	- WFG graph
	- No cycle means no deadlock
	- Look ahead and see if the order of execution of the transaction would cause deadlock.

Timestamping
A way to order transactions based on age. 
- Unique identifier for each transaction to keep track of the age of the transaction
	- Can be system clock
	- Or logical counter that increments when a new transaction starts
Allows updates on data item only when the last update on the data item is by an older transaction. 
Read-timestamp -> timestamp of last transaction to read item
write-timestamp -> timestamp of last transaction to write item

# Lecture 6

Database Modules
1. Transaction Manager
	- Coordinates transactions on the behalf of applications
2. Scheduler
	- Implement strategy for concurrency control
	- Locking
	- Timestamping
	- Concurrency control
3. Recovery Manager
	- Failure can cause inconsistencies in the database 
	- Ensures that the database is at a consistent state in the event of failure
4. Buffer Manager
	- Facilitate the transfer of data between disc storage and main memory

Backup
1. Full Backup
	- A complete copy of the database
2. Incremental Backup
	- Cumulative
		- Only back up changes the files that have changed since the last full back up 
	- Differential 
		- Only back up the files that have changed since the last backup
- Offline backup refers to backup while the database has been shut down cleanly and is not reopened throughout the backup
- Online backup (hot and inconsistent) is inconsistent because the online redo log file changes have not yet applied to the data files. Database in ARCHIVELOG mode. 

Types of errors:
1. Media error
	- The file needed for a database operation is missing.
2. Instance error
	- The database instance shuts down unexpectedly
3. Network error
	- The connectivity to the database is lost
4. User problem
	- The user successfully completes an operation, but it's the wrong operation. 
5. User process error
	- A single database session fails
6. Statement error
	- A single database operation fails

Recovery facilities
1. Backup mechanism
	1. Create backups of the database periodically
	2. In the event of failure, the database can be returned to a previously consistent state.
	3. Copies of the database and log file are made at a regular interval
2. Logging facility
	1. Keeps track of database state and changes made to the database
3. Checkpoint facility
	1. Enables updates to the database to be made permanent
4. Recovery manager
	1. Restore the database to a consistent state following a failure. 

Techniques
1. Roll-forward
	- Redoing operations from a transaction that has already committed in the event of failure
2. Roll-backward
	- Undoing operations from an uncommitted transaction in the event of failure

Update methods
1. Deferred update
	1. Updates from a transaction are only applied when the transaction has committed
	2. How it works:
		2. Writes transaction start in the transaction log
		3. If there is write operation, write the log record containing the after-image of the update
		4. When the transaction is about to commit, write transaction commit log record
		5. Write all the log records to disc
		6. Apply the updates to the database based on the log records
	3. You only roll-forward here because updates are only applied to the database when the transaction commits.
2. Immediate update
	1. Updates are applied as the transaction progresses
	2. How it works
		1. Write transaction start log
		2. If there is a write operation, write the log record first to the log file
		3. When the log record is written, write the update to the data buffers
		4. The updates are written into the database when the buffers are flushed in secondary storage. 
		5. Write transaction commit log
	3. It's important to write the log record first before applying the update so that the recovery manager knows which operations to roll back and roll forward.
		1. They would also know at which point the error occurs
	4. You apply both roll-forward and roll-backward when an error occurs since the updates are applied when the transaction commits.  
3. Shadow paging
	1. There are two pages during transaction
		1. Current page and shadow page
	2. Current page records changes made to the database 
	3. Shadow page remains unchanged
	4. When the transaction commits, the current page becomes the new shadow page
# Lecture 7

# Lecture 8

Query optimising is choosing the most efficient execution strategy to process a query. QP has 4 phases

1. Decomposition
	- The query is broken down and checked if its is syntactically correct and semantically correct
2. Optimisation
	1. Heuristic
		- Based on standards and rules to refine the query
	2. Cost Based
		- The cost for executing a query is reduced systematically by determining the cost of several different execution plans
3. Code generation
	1. Once the execution plan has been determined, the actual access routine will be writen out. 
4. Execution
	1. Execute the access routine
	2. Any runtime errors is also returned

# Lecture 9

Distributed database 
- collection of logically related data that is physically distributed across the network.
Distributed DBMS
- Allows the management of the distributed database and maintains transparency to the user (user feels as though they're accessing one database.)
- At least one global application

Characteristics of DDBMS
1. Collection of logically related shared data
2. Data is split into multiple fragments
3. Fragments may be replicated
4. Fragments are distributed to each site
5. Each site can communicate with each other over the network
6. Each site has a DBMS that will handle its local data
7. The DBMS will handle local application autonomously
8. Each DBMS participates in at least one global application

Distributed processing
- Multiple users from different sites tries to access the centralised database system

Parallel DBMS
- Connecting multiple, smaller machines to achieve the same performance, or better than one singular, powerful machine. It is also more powerful
- This allows query processing workload to be distributed across multiple nodes 
	- Parallel scanning
	- Join and Sort technique

Advantages of DDBMS against centralised database system
- Greater scalability
	- Vertical scalability
		- Can improve the hardware of each site 
	- Horizontal scalability
		- Can add more sites and nodes to distribute the workload
	- Centralised DBMS is only limited to vertical scalability, but the every machine has its limit on vertical scalability due to cost and technological advances. No horizontal scalability
- Greater performance
	- The query processing workload can be distributed across multiple sites or nodes.
	- Does not put a lot of strain on each site, especially in situations where multiple users are querying complex transactions 
- Greater durability
	- When one site is down, the entire system is not down. 
	- Other sites can still work
	- For example, customers in Malaysia will still be able to connect to the database site even if the site in America shuts down unexpectedly 
- Greater shareability and local autonomy
	- Allows more places to have access to the data
	- For example, if a social media's main database is the United States and a centralised database system is used, other sites will have a harder time connecting to the social media. With DDBMS, users can use the social media in their own local sites, since there will be local data. 

Disadvantage
- Integrity problem
	- Can be difficult to synchronise data changes between sites and the central database server
		- Can happen due to connectivity issue, resulting in an inconsistent state
		- If no proper recovery strategy is implemented, data integrity will be lost due to inconsistency and duplication
- Cost
	- Maintaining multiple sites and enabling them to communicate with each other require a powerful and stable infrastructure. 
- Complexity
	- Managing multiple sites at the same time. 
- Lack of standards
	- Each site may use different DBMS
	- They may adopt heterogenous DBMS type where every site uses different DBMS
	- This happens when the DBMS is created without the thought of expansion. 
	- There has to be translation to allow communication between sites
		- This can introduce or increase overhead during communication, slowing down performance. 

Types 
1. Homogenous 
	- Each site uses the same DBMS
	- Easy to design and manage
		- Since every site uses the same DBMS, can save a lot of time configuring each site, since there will be a standard
	- Easy to add new sites
		- Easy to add new branches and expansion
	- Better performance
		- Parallel processing
			- Sharing processing workload
		- Since each site uses the same DBMS, communication between them is much simpler, removing the need for translation, thereby reducing overhead.
2. Heterogenous
	1. Each site uses different DBMS
	2. Happens when the DBMS is created first without the thought of expansion
	3. Requires translation
	4. Gateway as a solution

Functions of DDBMS
- Extended data dictionary
- Extended security control
- Extended concurrency control
- Extended recovery services
- Extended communication services
- Distributed query processing

Reference Architecture
- Global External Schema
- Global conceptual Schema
- Allocation Schema
- Local mapping schema
- Local conceptual schema
- Local internal schema

Components of DBMS
1. Local DBMS component
	- Located at each site that contains database
	- Meant to handle local data
2. Data communication component
	- Allows communication between sites
	- Allows transfer of data between sites
3. Global system catalogue component
	- Contains the information about the distributed system
		- Fragmentation
		- Replication
		- Allocation
4. Distributed DBMS component
	- The control unit of the DBMS system

Key issues
1. Fragmentation
	- The data is split into fragments.
2. Replication 
	- Copies of the fragments may be maintained at several sites
	- If there is a fragment that is involved in a lot of query, copies will be made and stored in each site for quicker transaction 
3. Allocation
	- Allocate the most relevant fragments to each site
	- Distribute the fragments optimally to each site
	- For example, Malaysia site would mostly contain Malaysia data

Strategies for place of data
1. Centralised
	- A single database and a single DBMS with users distributed across the network
2. Fragmented
	- Data is split into fragments and allocation to different sites
3. Complete replication
	- A complete copy of the database at each site
4. Selective Replication
	- A mix of centralised, fragmented, and replication 

Advantages
5. 

Reason
2. 

Disadvantages

Correctness


# Lecture 10

Mobile Databases
- Database that is physically separated from the database server but is capable of communicating with server from a remote site, allowing the sharing of data

Functionality
- Communicate data with centralised database server through modes such as wireless connection and the Internet
- Replicate data with centralised database server and mobile devices
- Analyse data with centralised database server and mobile devices
- Manage or analyse data on mobile device
- Capture data from various sources such as the internet

Issue
- Connectivity
	- Requires a strong connectivity, especially during data transfer between the database server and the remote mobile device. 
		- If connectivity is lost in the middle of data transfer, the data can become corrupted.
- Security
	- Can be stolen by a third party
	- Since connection is wireless, a man-in-the-middle attack can happen.
- Synchronisation issue
	- Causes inconsistency
	- Causes issue with data integrity

# Lecture 11

SQL vs NoSQL

SQL is mainly for relational database while NoSQL is for non-relational database. The data stored in an SQL database is structured data such as text while the data stored in NoSQL can be both structured and unstructured data which can be images, videos, audios, text, and documents. The characteristics of transaction in a SQL database follows the ACID property - Atomicity, Consistency, Isolation and Durability while NoSQL database follows BASE - Basically Available, Soft State, and Eventual Consistency. There are no complex relationship in NoSQL while SQL has complex relationship. SQL is slower when it comes to handling large unstructured data, while NoSQL is built for that

Basically Available
- A NoSQL database is guaranteed to be available in the event of a failure
Soft State
- The state of the data could change due to eventual consistency even without application interaction
Eventual Consistency
- System will be eventually consistent after the application input. 
- The data is replicated to several nodes and will eventually become consistent
- Consistency is not guaranteed at transaction level

Properties
1. Highly scalable
2. Distributed computing
3. Flexible schema
4. Support both structured and unstructured data
5. No complex relationships

Disadvantage
- No joins
- No standard
- Complex
- Large data

Big Data characteristics
- Velocity
	- The speed in which the system receives data
- Veracity
	- The trustworthy of the data flowing into the system
- Volume
	- The amount of data 
- Variety
	- Variations in the structure of the data format

Hadoop is an ecosystem that is used to handle and process big data. Hadoop Distributed File System enables the concurrent processing of multiple files and fault tolerance. 

NoSQL models
- Key-Value
	- Stores data in key-value pair
	- The value can be text, document, video, audio
- Document-based
	- Can be said to be a subset of key-value
	- The document is stored in value
		- Can be JSON, binary JSON, XML
	- Attempts to understand the relationship in the data
	- MongoDB
- Column-based
	- Stores data in key value where the key is mapped to blocks of rows or columns
	- Row centric 
		- Data is stored in blocks by row
		- Contains all of the columns in a given set of rows
			- Minimise disk read
	- Column centric
		- Data is stored in blocks by column
		- Contains all of the row in a column.
- Graph-based
	- For relationship rich environment
	- Facebook, Instagram, Tinder
		- In Instagram, the application would benefit from graph-based because of the commenting system
			- One comment leads to another comment
			- This allows the comments to be grouped together and keeps then in a relationship
	- Follows graph theory
		- Node
			- Contains an instance of the entity
		- Edge
			- Relationship between nodes
		- Properties
			- Attributes or characteristics of nodes or edges
		- Traversal
			- Query in a graph database. 