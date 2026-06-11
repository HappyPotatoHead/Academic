---
aliases:
  - R&U
tags:
  - Notes
  - Database
  - SQL
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
>[!NOTE] Lecture
>[[lecture_1_introduction_to_data_modelling_and_design_part_1.pdf]]

# Warm-up
>[!DEFINITION] Data
>Raw material. Useless on its own

>[!DEFINITION] Information
>Processed formed of data. It is now more useful.

>[!DEFINITION] Knowledge
>Knows what to do with the information given to us. 

>[!EXAMPLE] Data vs Information vs Knowledge
>Data: Random, raw dates
>Context: Birthdays
>Information: We now know what these dates are birthdays. 

# File-based Approach
The issues with this approach are:
1. Separation and isolation of data
	1. Files and folders are independent of one another. 
2. Duplication of data
	1. If the files are not updated or synchronised properly
3. Data dependence 
4. Incompatible file formats
5. Fixed Queries/ Proliferation(increase of application programs)

# Database
>[!DEFINITION] Database
>Collection of logically related data and a description of the data. 
>>[!DEFINITION] Metadata
>>Data about data

## Database Management Systems
>[!DEFINITION] DBMS
>Software or tools that allows user to define, create, maintain, and control access to the database. 
>>[!EXAMPLE] DBMS
>>1. MySQL
>>2. Oracle SQL
>>3. PostgreSQL
>>4. MsSQL


# Three-level ANSI-SPARC Architecture
## Objective
- Allows independent customised user views
- Hides the physical storage details from users
- Allows database administrator to change the database storage structures without affecting the users' views. 
- The internal structure of the database should be unaffected by changes to the physical aspects of the storage. 
	- *Imagine you have a big toy box where you keep all your toys. One day, you decide to move your toy box to a different room or maybe you get a new toy box, but no matter where the toy box goes or how it changes, your toys are still in the same neat little sections inside.* 
	- Essentially, the data remains the same even after maintenance
		- Moving to a new server
		- Moving to a new hard drive
## The levels
1. External Level
	- Users' view of the database
	- Describes that part of database that is relevant to a particular user.
2. Conceptual Level
	- Community view of the database
	- Describes what data is stored in database and relationships among the data
		- It's like the ER or EER diagram
3. Internal Level
	- Physical representation of the database on the computer
	- Describes how the data is stored in the database
	- Depends on specific database software
## Schemas, Mapping, and Instance
>[!DEFINITION] Database Schema
>Description of the database which is specified during design process. This is not changed frequently unlike actual data.

>[!DEFINITION] Database Instance
>The data in database at particular point in time. The same database schema with many instances. Describes that part of database that is relevant to a particular user. 

>[!DEFINITION] Conceptual/ Internal mapping
>Find actual record in physical storage

>[!DEFINITION] External/Conceptual mapping
>Map names in user's view to the relevant part of the *conc.* schema.

# Database Architecture
## Client-server Architecture
Generally, a DBMS is divided into:
1. Client
	- Handles the main business and data processing logic and interfaces with the user
2. Server
	- Manages and control access to the database
## Two-tier Client-Server Architecture
In this architecture, the server holds both the database and the DBMS, and the client manages user interface and runs applications. 

However great this architecture may be, there are some issues, 
3. Scalability issues
	1. The application and database layers are tightly coupled
4. Performance bottlenecks
	1. If there are a lot of database queries, there may be performance bottlenecks
5. Limited Reusability
	1. Business logic is often embedded on the client server. This makes reusability more difficult. 

To answer these issues, a **three-tier architecture** is introduced. 
## Three-tier Architecture
This is the current *standard* architecture. In this architecture, there are 3 *stages*. 
1. Client server
2. Application server
3. Database Server

>[!INFO]- Clarification
>Application refers to applying, not the software!
## N-tier Architecture
N-tier architecture is essentially an extension of [[Lecture 1 - Revision#Three-tier Architecture|three-tier architecture]]. 

## Web services and Service-oriented Architectures
### Services-oriented Architectures
These software allow users to use them without the existence of a GUI such as terminal. Another example would be calling an API.

>[!DEFINITION] Service-oriented Architecture
>Software system that supports interoperable machine-to-machine interaction over a network. 
>- No GUI

# Distributed DBMS
## Distributed database
This refers to the actual, physical database that is stored. 

*Think of it as the location of data centers.*
## Distributed DBMS
Essentially, this is how the same data is transferred to different users in different regions. 

>[!EXAMPLE] YouTube in Malaysia
>A user accessing a video in YouTube in Malaysia will fetch the video from a YouTube database in the Malaysian region. 
>
# Distributed Processing
Refers to how the data is being accessed or processed by different users over the network.  