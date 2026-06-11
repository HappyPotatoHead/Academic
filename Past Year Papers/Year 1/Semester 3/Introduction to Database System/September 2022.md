---
aliases:
  - September 2022
tags:
  - PYQ
  - Database
Creation Date: 2024-05-22T13:37:00
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1
### Question a
```sql
SELECT Fname, Lname, DateJoined
FROM Employee e
JOIN Department d ON e.DeptId = d.DeptNo
JOIN Department_Location dl ON d.Location = dl.DeptLocNo
WHERE dl.DeptLocNo = 1;
```
### Question B
```SQL
SELECT Fname || ' ' || Lname as "Full Name", BasicSalary * ((100+Commission)/100) as "Total Salary"
FROM Employee e
JOIN Assignment a ON e.EmpID = a.EmpID
WHERE e.EmpID = 'S003';
```
### Question C
```SQL
SELECT Fname, Lname, ProjName 
FROM Employee e 
JOIN Department d ON e.EmpID = d.ManagerID
JOIN Project p ON p.DeptID = d.DeptID;
```
### Question D
```SQL
SELECT Fname, Lname
FROM Employee e
WHERE TO_CHAR(DateJoined, 'YYYY') < 2020
AND Address LIKE '%Boston'
ORDER BY DateJoined;
```
### Question E
```SQL
SELECT e.Fname, e.Lname, MONTHS_BETWEEN(SYSDATE, DateJoined)/12, s.Fname, s.Lname
FROM Employee e
JOIN Employee s ON e.SV_ID = s.EmpID
ORDER BY MONTHS_BETWEEN(SYSDATE, DateJoined)/12;
```
## Question 2
### Question A
#### Question I
**Date =** Date
**Ranking** = Number
#### Question II
**Participant**
*Primary Key:*
1. participantNo
*Foreign Key*
2. NONE
**Sport**
*Primary Key*
1. sportID
*Foreign Key*
1. NONE
**Result**
*Primary Key*
1. NONE
*Foreign Key*
1. participantNO
2. sportID 
#### Question III

| Parent                     | Child  |
| -------------------------- | ------ |
| 1. Participant<br>2. Sport | Result |
#### Question IV
The relationship strength between participant and result is strong and the relationship strength between sport and result is strong. 
#### Question IV
Ranking. The ranking of each participant may change with as the competition progresses
### Question B
#### Question I
Multivalued attribute
#### Question II
The multivalued attribute. The solution is to create more attributes to contain each of the values in the original multivalued attribute.
*You can also create a new entity. The new entity will have a one to many relationship with course registration records. The values in the multivalued attributes will be assigned to specific primary keys.*
### Question C
email. Most individual is entitled to one unique phone number. Furthermore, most email services do not allow customers to change their email address, making is less time-dependent compared to email or address.
## Question 3
### Question A
#### Question I

| StuID | studentName | Classroom | BookCode | BookName         | Quantity | StartDate  | EndDate    |
| ----- | ----------- | --------- | -------- | ---------------- | -------- | ---------- | ---------- |
| S001  | Jasmine     | 3 Berlian | BC111    | Sejarah T3       | 12       | 12/06/2022 | 22/06/22   |
| S002  | Michael     | 5 Intan   | BC333    | English T5       | 10       | 01/06/2022 | 11/06/2022 |
| S002  | Michael     | 5 Intan   | BC222    | Matematik T5     | 20       | 09/07/2022 | 19/07/2022 |
| S003  | Brian       | 5 Delima  | BC333    | English T5       | 10       | 15/07/2022 | 25/07/2022 |
| S001  | Jasmine     | 3 Berlian | BC444    | Bahasa Melayu T3 | 15       | 21/07/2022 | 01/08/2022 |
#### Question II
Primary Key = {StuID, BookCode}
#### Question III
![[Past Year Papers/Year 1/Semester 3/Introduction to Database System/Diagrams/september_2022/dependency_diagram||1000]]
### Question B
#### Question I
1. Insertion Anomaly 
	1. Cannot insert any product without its supplier id
	2. Cannot insert any supplier without its product code
2. Deletion Anomaly
	1. Cannot delete any supplier as it would cause loss of information about the product code 
	2. Cannot delete any product as it would cause loss of information about the supplier
3. Modification anomaly
	1. If the supplier name is changed, the entire record for that supplier is changed. 
#### Question II
Supplier

| SupplierID(pk) | SupplierName |
| -------------- | ------------ |
Product

| ProductCode(pk) | ProductName |
| --------------- | ----------- |
Supply

| SupplierID(pk, fk) | ProductCode(pk, fk) | Quantity |
| ------------------ | ------------------- | -------- |


# Section B
## Question 4
### Question A
#### Question I
**Parent entity**: Staff
**Child entity**: Department
**Actions that can be taken**
1. Cascade delete
2. Restrict delete
3. No action 
4. Set null ✅
5. Set default ✅
Set default. When the staff record is deleted, the staffID in the dependent entity is set to a default value. This is because even if a staff is fired, the department will still exist. 
#### Question II
**Parent entity**: Job
**Child entity:** Staff
**Actions that can be taken**
1. Cascade delete ✅
2. Restrict delete
3. No action
4. Set null
5. Set default
Cascade delete. When the job record is deleted, the staff record that has the same jobcode will be deleted as well. This is because when a job is deleted, the staff that does the job will be fired. 
### Question B
Entities
1. Patients
	1. patientID
	2. Name
	3. Age
	4. Sex
	5. Phone number
	6. Address
3. Doctors
	1. docID
	2. Name
	3. Age
	4. Sex
	5. Phone number
4. Appointment
	1. AppID
	2. patientID
	3. docID
	4. type
	5. date
	6. room
6. Consultation
	1. AppID
	2. diagnosis
	3. treatment
7. Bill
	1. billID
	2. patientID
	3. docID
	4. due
	5. Totalpaid
8. Payment
	1. PaymentID
	2. billID
	3. date
	4. Amount
![[clinic_erd|5000]]
## Question 5
### Question A
Customer
1. customerID
2. Name
3. Street_address
4. City
5. Zip
6. State
7. Contact
Product
1. ProductID
2. ProductName
4. Price per UNIT
Invoice
1. InvoiceNo
2. CustomerID
3. ProductID
4. StaffID
5. Date
6. Payment
7. Amount
Salesman
1. staffID
2. Name
3. DateHired
4. Age
5. Gender

![[computer_shop_erd.png]]

### Question B
#### Question 1
![[fan_trap.png]]
#### Question II

![[chasm_trap.png]] 