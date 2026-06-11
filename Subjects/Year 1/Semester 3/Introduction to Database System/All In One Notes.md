---
aliases:
  - All in One Notes
tags:
  - Notes
  - Database
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
# Definitions
- [?] **Primary key** ^5c2873
	- The *attribute* with unique values
	- Value is not null
	- Is not an intelligent identifier
		- It's values does not have any significant meaning
- [?] **Secondary key**
	- The alternate key
- [?] **Foreign key** ^813f80
	- Used to connect multiple tables together. 
	- The foreign key in one table must be the primary key the other table
	- The table with foreign key is the child table/existence dependent table
- [?] **Composite key** ^caf96e
	- Unique key that exists when you combine **two or more fields**
		- Usually composite keys that get too long are replaced by **surrogate keys**
			- Surrogate keys are keys that hold no meaningful value other than to just uniquely identify a tuple ^15be6b
	- **Usually comprises fields that are primary key in other tables**
	- ![[composite_key.png|Composite key]]
		- We can see that only when both **S_ID** and **COURSE_ID** are paired together, a **unique key** exists
- [?] **Relational keys**
	- Table name(**Attributes go here**)
	- SuperKey = {key1, (key1,key2),......}
	- Candidate Key = {key1, key2}
	- Primary Key = {key1}
- [?] **Parent table** ^143a2a
	- Stores the original value
	- Contains the **primary key**
	- Original table
- [?] **Child table** ^08061e
	- Stores the reference value
	- Contains **foreign key**
- [?] **NULL value**
	- Represents values that are currently unknown or not applicable for tuple
	- Deals with incomplete data
	- **it is not space or 0**
- [?] **Existence dependency**
	- *Existence dependent*
		- An entity cannot exist without association with another entity
	- *Existence independent*
		- An entity that can exist apart from one or more entity
# Business rules
- [?] Brief, unambiguous, precise description of procedures, policies and rules of an organisation
- [?] Description of operations that create and enforce actions in an organisation
- [?] Used in any organisation that handles user data
- [?] Formalised statement of the usual, customary, generalised course of action taken by the organisation
**Structural business rule**
- Defines how information is stored and how information elements interrelate
**Procedural business rule**
- Related to procedures and workflow
**Enterprise constraint**
- Additional rules determined by the user and database administrators
## Why business rules is important
- Allows database designer to understand the nature, role, and scope of the data
- Allows database designer to develop appropriate relationship and constraint
- A form of communication tool between user and database designer
- Standardise the organisation's view on data

# Creating Relationship by Repeating Data
![[0_nf.png]]
The best way to handle the above data is to separate them into separate tables. *Foreign key* will be used to connect these two tables. This practice can also reduce the values that are repeating.

- [!] Student table here is the child table since it contains foreign key
![[child_table.png]]

# How to decide the key
**Steps**
1. Determine the super key
	1. This forces us to determine possible pairs including composite keys
	2. **Meta-Steps**
		1. Determine singles
			- IF it does not exist, skip to finding composite keys
2. Determine the candidate key
3. Determine the primary key
	1. **IT can be foreign key**
- [!] **Do this for every table**

**Precautions**
IF [[All In One Notes#^caf96e|composite key]] consists of more than 3 columns, it's better to just create a third column holding an id ([[#^15be6b|surrogate key]]). Usually composite keys are [[All In One Notes#^5c2873|primary keys]] in other tables.
# Data Integrity
- [?] The accuracy and consistency of data across multiple tables stored in a database
	1. Entity Integrity
		- Constraints on [[All In One Notes#^5c2873|Primary key]]
		- no repeating primary key value
		- No null primary key
	2. Referential Integrity
		- Constraints on [[All In One Notes#^813f80|foreign key]]
		- Foreign key value must match a candidate key value of some tuple in its parent table or foreign key value must be wholly null
		- [[All In One Notes#^08061e|Child table]] should be updated with the [[All In One Notes#^143a2a|parent table]]
		- Only existing [[All In One Notes#^5c2873|primary key]] can be used as [[All In One Notes#^813f80|foreign key]]
		- **Enforcing- actions to be taken**
			1. Cascade delete/Cascade update
				- Updating every tuple that has been affected by the change in the [[All In One Notes#^143a2a|parent table]]
				- IF cascade delete/cascade update
					- Any information deleted in the parent table, the row in the child table would be deleted
					- ![[appropriate_cction_c_cont.png]]
			2. No action/Restrict
				- Does not allow any changes to be made
				- Cannot change the value of *TrainerNo* in the table *Client* to a **rogue** value.
			3. Set Default
				- Put a default value in the *client* table after a row in the *trainer* table has been deleted 
			4. Set Null
				- Put all **NULL** value
	1. Domain integrity
		- Only allows certain values to be in the table
		- Limits the value that can be placed in a specific field. 
		- **Contrains**
			1. Check constraints
				- Field value must be a specific value or fall within a range of values
				- s_class CHAR(2) CONSTRAINT student_s_class_cc CHECK ((s_class = "FR")) OR (s_class = "SO") OR ( s_class = "JR") OR (s_class = "SR")
			2. NOT NULL
				- Specify whether a field value can be NULL
			3. UNIQUE constraints
				- Specify that each instance must be a unique value
			4. DEFAULT contraints
				- Specify that each instance should have a default value that the DBMS assigns when no other values are specified. 
# Example - appropriate action
![[appropriate_action_b.png]]
![[appropriate_action_c.png]]
# Normalisation
## Conditions
### First normal form
1. no repeating groups
2. each cells must contain only one value
3. Each attributes must be dependent on a primary key
### Second normal form
1. Watch out for composite keys
2. Table must be in 1NF. 
3. Each attributes must be dependent on the composite key
4. no partial functional dependencies
### Third normal form
1. Table must already be in 2NF
2. no transitive dependencies