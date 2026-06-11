---
aliases:
  - September 2023
tags:
  - PYQ
  - Database
Date: 2025-05-22
Finished Date: 2025-05-22
Completion: true
obsidianUIMode: preview
---
# Section A

## Question 1

### Question A

>[!TIP]- How to Answer?
> Start from the basics
> Talk about referential integrity:
> - null values
> 	- If it is nullable, it indicates that this instance is not tied to any instances found in the parent table
> 	- Commonly found in optional participation relationship
> - Match values
> 	- The value would not be allowed
> 	- Since the value has to match to indicate relationship
> 	- You can't have a relationship with a non-existent instance


According to referential integrity, the value of the foreign key in a relation must match value of the primary key of another table, or it must be wholly null. If the foreign key nullable, and the value is null, this means that the instance in this relation has no relationship with any of the instances in the parent table. There is no violation of referential integrity. However, if the value does not match any of the primary key value in the parent relation, there would be a violation of referential integrity, as a relationship with a non-existent instance is trying to be made. 

### Question B

>[!TIP]- How to Answer?
>This talks about the 3 problems without concurrency control. Keep the examples simple if needed. (e.g. transactions). *Think concurrent!*
>1. Lost update
>	- Two users trying to update the savings account value concurrently
>	- Account has 100\$
>		- User A tries to withdraw 10
>		- User B tries to deposit 50
>	- Serially, it would be 140, but without concurrency control it would either be 90 or 150. 
>2. Inconsistent Analysis Problem
>	- Two users trying to update the savings account value concurrently
>	- Account has 100\$
>		- User A tries to withdraw 10
>		- User B tries to deposit 50
>	- If user A withdraw 10 but aborts afterwards and user B reads the value after the withdraw but before the abortion, user B would be updating 90\$ instead of 100\$
>3. Uncommitted Dependency Problem (emphasis on reading)
>	1. User C reads the value while User A and User B is updating the database/.


1. Lost update
	- When the complete update operation by one user is overridden by another user.
2. Inconsistent Analysis Problem
	- Lost update and uncommitted dependency problem is concerned with updating data items.
	- But, reading a data item that is being updated by operations from other transaction can also cause problems.
	- This problem happens when a transaction is allowed to view the partial effect of another uncommitted transaction.
3. Uncommitted Dependency Problem
	- When a transaction is allowed to read the partial result of another transaction that is updating the database.

### Question C

>[!TIP]- How to Answer?
>Read the passage carefully and consider their lifespan. 
>*A COURSE may be offered in the multiple CLASS SECTIONS*
>Course and class section are related. *For example, one course can have L1, L2, L3*. Without the course, the lecture sessions make so sense
>1. Dependent lifespan
>2. Inability to exist separately
>3. Ownership and nature of realtionship

Composition. The relationship between Course and Class Section is a whole-part relationship with COURSE being the whole and CLASS SECTION being the part.

1. Inability to exist separately
	- One of the major properties of composition is the part belongs exclusively to the whole and cannot exist separately. In this case, the COURSE SECTION existing own its own outside the context of a course does not make sense.
2. Dependent life span
	- The existence of CLASS SECTION is dependant on the existence of COURSE. If an instance of COURSE dies, the related CLASS SECTION dies with it.
3. Ownership and nature of relationship
	- It is a strong association relationship
	- The class section belongs to only that course. 

### Question D

>[!TIP]- How to Answer?
>Define what each of them are
>State which condition they would strive best
>Give an example

Online analytical processing is designed to handle large volume of historical data and complex analysis. This processing is to help with decision making within an organisation. Online Analytical Process is more efficient in this because of its use of denormalised database which makes retrieving data much quicker.

For example, a sales manager generating a quarterly sales report analysing sales performance across multiple regions.  

Online transaction processing is design to handle large volume of frequent, simple transactions in day-to-day businesses. This processing focuses on high throughput while ensuring data integrity. This processing is efficient in this aspect due to it's normalised structure that allows it maintain data integrity while allowing fast and quick database operations. 

For example, online transaction processing is used by cashiers in malls. 

### Question E

>[!TIP]- How to Answer?
>Instead of thinking just about file-based system's advantages, focus on why not other systems? (*Basically disadvantages of DBMS*)
>
>*Why not?*
>- Cost of conversion to new technology
>- Complexity
>- Cost of development
>- Large amount of data
>
>*Why keep?*
>- There is no reason to switch to a larger, more complex system for simple data storage 


1. Cost of conversion to new technology
	- The staffs are required to learn a new tool and system which is time consuming. 
	- New tools and hardware may have to be bought to support the new system
	- Training program also has to be organised for the employees to get used to the new tool.
2. Cost of migrating data
	- If the organisation already has a large volume of data that is difficult to migrate to a new system, migrating to a new system can be costly and time-consuming. The data from the file-based system has to be cleaned and restructure to fit the new database schema. 
3. Suitability for basic data storage
	- The organisation may have limited, basic data structure that only requires simple data retrieval and storage. The overhead and complexity that comes with implementation of DBMS may not be necessary for the organisation. 

## Question 2

### Question A

#### Question I

>[!TIP]- How to Answer
>Define what it is 
>Define the what makes it up
>Define the types 
>Give example

Functional Dependencies refers to when the value of one attribute determines the value of other attributes. In functional dependencies, there are fully functional dependencies, partial dependencies, and transitive dependencies. The attribute that determines the value of other attributes is called determinant. For example, $A \rightarrow B$ means that the value of attribute A will determine the value of attribute B.

#### Question II

>[!TIP]- How to Answer?
>Pay attention to the description. 
>*One suppler may supply the **same** product many times, with **different** delivery date and time*
>	- This means that product id is repeated and delivery date and time is unique. 
>**Don't think too much about it**

**Primary key dependency** 

$$\text{supplier\_id, delivery\_date\_time} \rightarrow \text{supplier\_name, street, city, postcode, product\_id, product\_name, quantity}$$

**Partial dependency**

$$
\text{supplier\_id} \rightarrow \text{supplier\_name, street, city, postcode}
$$
$$
\text{delivery\_date\_time} \rightarrow \text{product\_id, product\_name, quantity}
$$
**Transitive dependency**

$$
\text{product\_id} \rightarrow \text{product\_name}
$$
**Candidate dependency**

$$\text{product\_id, delivery\_date\_time} \rightarrow \text{product\_id}$$

$$\text{postcode} \rightarrow \text{city}$$

#### Question III

>[!TIP]- How to Answer?
>Indicate the primary keys and foreign keys

1NF
$\text{R (suppler\_id<pk>, supplier\_name, street, city, postcode, product\_id, product\_name, quantity, delivery\_date\_time <pk>)}$
2NF

suppliers(supplier_id \<pk>, supplier_name, street, city, postcode)
suppliers_products(supplier_id \<fk>, delivery_date_time \<fk> product_id, product_name, quantity)

3NF
suppliers(supplier_id \<pk>, supplier_name, street, city, postcode)
products(product_id \<pk>, product_name)
suppliers_products(delivery_date_time \<pk>, supplier_id \<pk,fk>,, product_id \<fk>, quantity, delivery_date_time)

### Question B

#### Question I

$\pi_{\text{name}}(\sigma_{\text{city = "Los Angeles" } \lor \text{ city = "New York" }\text{ Customer}})$

#### Question II
$$\pi_{\text{name, steet, city}}((\sigma_{\text{make = "Toyota"}} \text{ Car }) \bowtie \text{ Owner } \bowtie \text{ Customer })$$

## Question 3

>[!TIP]- How to Answer?
>Go line by line
>Keep it simple
>Gather information by the line

### Question A

clinics (clinics_number \<pk>)
staffs (staffs_number \<pk>, clinics_number \<fk>)
owners (owners_number \<pk>)
pets (pets_number \<pk>, owners_number \<fk>)
healthcare_exams (healthcare_exams_number \<pk>)
treatments (treatments_number \<pk>)
pets_exams (pets_number \<pk, fk>, healthcare_exams_number \<pk, fk>, staffs_number \<pk, fk>)
pets_treatments (pets_number \<pk, fk>, treatments_number \<pk, fk>, staff_number \<pk, fk>)

### Question B

![[clinic_ERD.png|700]]

### Question C

>[!Tip]- How to Answer?
>Define what type of relationship that the question is trying to say
>Give the entities
>Explain the characteristics of the relationship in terms of the entity.

Pet owner and pet. The relationship between the two is an aggregation relationship. The pet owner is the whole and the pet is the part. This is an aggregation relationship because of independent lifespan. When the pet owner is gone, the pet still exists and can be transferred to another owner. When the pet is gone, the pet owner still exists and can adopt another pet.

Additionally, the whole, pet owner, and the part, pet, can exist independently on their own. The pet can switch owners and the owners can replace their pets

### Question D

>[!TIP]- How to Answer?
>Read the passage. Identify places where the same nouns are used. 
>Yes or No
>Define what specialisation is in terms of the entities (attributes and relationships)


Yes, specialisation exists in this scenario. Specialising Staff entity into Manager entity or Consultant entity type. Staff is a generic entity type while Manager role or  Consultant role are specific entity types. Specialisation exists here because Manager and Consultant role each have their own attributes and behaviours. Managers have a unique relationship of managing clinics, and consultant have responsibility and possibly unique attribute related to healthcare examinations and treatments which may not be applicable to all staff members.  

# Section B

## Question 4

### Question A

#### Question I

>[!TIP]- How to answer
>Update the transaction examples to fit with the situation.
>In the bread **shop** case, think about transaction, inventory and report. 


1. Lost update
	- The final result of a transaction may be overridden by another user. 
	- For example, this can happen when two different users tries to update inventory count for a product. The final inventory count would then depend on the relative timing of the execution of each transaction.
2. Uncommitted Dependency problem
	- This happens when a transaction is allowed to see the partial effect of an uncommitted transaction.
	- This happens when a transaction from one branch reads a data item that is being updated by a transaction from another branch, but has not yet committed. This is known as 'dirty read'.
3. Inconsistent Analysis problem
	- This happens when a transaction is allowed to see the partial effects of another transaction that is currently updating the database.
	- For example, if a report that calculates the total sales across several branches is generated, it may retrieve sales data item from a branch before it has been updated. This inconsistency leads to an inaccurate sales report.

### Question III

>[!TIP]- How to Answer?
>*See lecture notes for two*
>1. Performance
>	1. Global application that requires data from fragments located on multiple sites and fragments
>	2. **Sales**
>		1. Talk about sales report that requires data from multiple branches and you have to merge them.
>		2. Talk about how slow it is and what it might mean
>2. Integrity
>	1. Integrity control is difficult when data and functional dependency is spread across multiple fragments
>	2. **Sales**
>		1. Talk about prices or product code
>		2. Should have the same prices across the country
>		3. Product code should be the same too
>3. Complexity of data management
>	1. Has to record how the fragmentation is done, their allocation, control the strategy to reconstruct them and operations spanning across multiple fragments. 
>	2. **Sales**
>		1. 

1. Performance
	- Global applications that require data from several fragments from different sites.
	- If a report concerning company-wide sales report is needed, there is a need to retrieve and combine data across multiple branches, which is slower than accessing data from a local database, which can potentially affect the company's sales insight.
2. Integrity control
	- Hard to control integrity when data and functional dependencies are distributed.
	- For example, to enforce the unique product code across all fragments in different branches or ensuring referential constraint on a fragmented "Products" table and "Orders" table can be complex and difficult. 
3. Complexity of data management
	- The DBMS has to record how the fragmentation is done, their allocation, and control the strategy to reconstruct them. 

#### Question III

1. Local DBMS
	- A standard DBMS to handle local data at each branch.
	- There would be a local DBMS in each branch of ABCBread responsible to handle data from only that branch, allowing faster processing as data is only fetched from local branches
2. Data communication 
	- To allow communication between sites.
	- It allows each branch to transfer data to one another. For example, the transfer of inventory count information from one branch to another.
	- *Company-wide analysis works too*
3. Global system catalogue
	- Contains information of the nature of the distributed system -> fragmentation, allocation, replication
	- This contains information of the fragments such as the strategy used for ABCBread's data fragmentation, location of the fragments, and replication of the fragments.
4. Distributed DBMS
	- Control unit of the distributed system, ensuring consistency, concurrency control, and integrity across all branches of ABCBread. 

# Next Paper

[[Past Year Papers/Year 2/Semester 3/Database Technology/May 2023|May 2023]]