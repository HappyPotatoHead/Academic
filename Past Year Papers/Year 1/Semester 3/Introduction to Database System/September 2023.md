---
aliases: 
tags:
  - Database
Completion: true
Date: 2024-04-21
Creation Date: 2024-04-21T21:38:00
---
# Section A
## Question 1
### Question A
#### Question I
```SQL
SELECT bookTitle, bookCost, bookYear 
FROM Book 
ORDER BY bookTitle;
```
#### Question II
```sql
SELECT auID, auFname, auLname, bookTitle
FROM Author a 
JOIN BOOK b ON b.auID = a.auID
WHERE bookTitle LIKE '%Cloud%';
```
#### Question III
```SQL
SELECT bookNo, bookTitle, Count(bookNo) as "Checked out"
FROM Book b
JOIN Checkout c ON c.bookNo = b.bookNo
WHERE HAVING COUNT(bookNo) > 5
GROUP BY bookNo
ORDER BY COUNT(bookNo);
```
### Question B
#### Question I
```SQL
SELECT COUNT(ProjNo)
FROM Project
WHERE ProjValue BETWEEN 50000 AND 100000;
```
#### Question II
```SQL
SELECT EmpName, JobDescription, TO_CHAR(EmpHireDate, 'Day') as "Day"
FROM Employee
```
#### Question III
```SQL
SELECT EmpName, JobDescription, AsgnDate, (AsgnHours * JobChgHour) as "Payment"
FROM Employee e
JOIN Assignment a ON a.EmpNo = e.EmpNo
JOIN JOB j ON a.JobCode = j.JobCode;
```
## Question 2
### Question A
#### Question I
**Staff**
*Primary key*
- StaffId
*Foreign key* 
- BranchNo references Branch(BranchNo)
**Branch**
*Primary key* 
- BranchNo
*Foreign key*
- StaffId references Staff(StaffId)
- RegionCode references Region(RegionCode)
**Region**
*Primary key*
- Region Code
*Foreign key*
- NONE
#### Question II
VARCHAR2 
#### Question III
*Parent table*
- Region
*Child table*
- Staff
- Branch
### Question B
#### Question I
Derived attribute is linePrice. The value can be obtained by multiplying the line units with the prodprice.  
#### Question II
Invoice. Its primary key is derived from table Customer and table Line. Invoice table itself  cannot exist without the creation of Customer Table and Line table first. 
#### Question III
prodDesc. If one word description is used, there may be multiple description that is needed to provide a complete description of the product. For example, a table product may have descriptions "Black", "Wooden", "Birch" and more
#### Question IV
entity relation can be applied by assignment a unique attribute to each of the entities and ensuring the unique attribute does not repeat and is not null. Referential integrity can be enforced between a parent table and its child tables. Restrict delete can be applied whereby values from the parent table cannot be deleted unless the values that in the child table is deleted first.
## Question 3
### Question A
#### Question I
No. Not every cell only contain one value. The values in row sourCode each contain more than one value
#### Question II
Attributes must be single valued and no repeating group
#### Question III
![[Past Year Papers/Year 1/Semester 3/Introduction to Database System/Diagrams/september_2023/dependency_diagram|500]]
#### Question IV
Book(BookID\<pk\>, BookName, Edition)
Shelf(ShelfCode\<pk\>, shelfDept)
Publisher(bookID\<pk\>\<fk\>, shelfCode\<pk\>\<fk\>, soucreCode)
### Question B
#### Question I

| EmpID | EmpName     | EmpDept       | ClubID | CName     | Role   | EnrolSDate | EnrolEDate |
| ----- | ----------- | ------------- | ------ | --------- | ------ | ---------- | ---------- |
| MX20  | Lea Sofea   | Finance       | B101   | Badminton | member | 11/11/2021 | 11/11/2022 |
| MZ18  | Albert Wong | Production    | T121   | Tennis    | member | 03/02/2019 | 03/02/2020 |
| MZ18  | Albert Wong | Production    | B101   | Badminton | member | 02/05/2023 | 02/05/2024 |
| PK17  | Raymond Foo | Control Audit | S144   | Squash    | member | 23/09/2017 | 23/09/2018 |
| MX20  | Lea Sofea   | Finance       | A878   | Archery   | member | 14/08/2022 | 14/08/2022 |
#### Question II
Primary key is empID
# Section B
## Question 4
### Question A
*Parent relation*: Agent
*Child relation*: Sales

Set NULL. This is because even if the agent has been fired or resigned, the sales made is still valid and existed. If the sales record is deleted along the agent, it will affect the report or analysis done on the sales by the end of the month. *The agent ID in sales will be set to null.*
### Question B
Multivalued attributes are attributes that may contain multiple values at once. For example, the phone number on a person may be from work, home, or personal. The database designer can create a new entity to store the values or create more attributes to hold each values from the multivalued attribute.
### Question C
#### Question I
![[job_application_erd|5000]]
#### Question II
*Entities:
1. Employee
	1. Primary key: e_ID
	2. Foreign key: NONE
2. EmpExp
	1. Primary key: e_ID and exp_ID
	2. Foreign key: e_ID and exp_ID
3. Expertise
	1. Primary key: exp_ID
	2. Foreign key: NONE
4. Interview
	1. Primary key: e_ID and h_ID
	2. Foreign key: NONE
5. Hire
	1. Primary key: h_ID
## Question 5
### Question A
#### Question I
![[automotive_erd|5000]]
#### Question II
Existence dependent. Entity only exists in a database when it is associated with another relation
Existence independent. Entity can exist on its own apart from one or more entities.
#### Question III
Most demanded items
Most active supplier
### Question B
#### Question I
![[ChasmTrap.png]]
Chasm trap occurs when the model suggests that there is a defined relationship between entities but the relationship becomes non-existence under certain entity occurrences. In the ERD diagram, since the relationship between the staff and property is optional one-to-many, when the property is under no supervision, we do not know which branch it belongs to
#### Question II
![[fan_trap.png]]
Fan trap occurs when the relationship between entities are defined but the relationship becomes ambiguous in certain occurences. The issue happens when a staff belongs to multiple department and since the ERD diagram only permits one faculty per staff, we do not know exactly which department the staff belongs to. 