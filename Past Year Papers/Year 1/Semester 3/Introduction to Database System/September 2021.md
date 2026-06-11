---
aliases:
  - September 2021
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
*Calculate the total booking trip to "Morocco" where the departure date happened during the first half of the year 2019*
```sql
SELECT Sum(Total)
FROM Booking b
JOIN Tour t ON b.TNo = t.TNo
WHERE t.TName LIKE '%Morocco' 
AND TO_CHAR(ROUND(DepartDate, 'YEAR')) = '1/01/2019';
```
### Question B
*select all the available tour in December but having maximum participants less than 25 people. arrange the list based on the alphabetical order of the tour name*
```sql
SELECT TName
FROM Tour
WHERE TMaxPart < 25 
AND TO_CHAR(DepartDate, 'MM') = '12'
ORDER BY TName;
```
### Question C
*list all the customer's name with their selected travel agency who had booked the trip to **Tokyo** or **Australia**, however still having outstanding payment with less than RM15000*
```sql
SELECT FName || ' ' || LName, AgentName
FROM Customer c 
JOIN Booking b ON b.CustNo = C.CustNo 
JOIN Tour t ON b.TNo = t.Tno
JOIN Agency a ON t.AgentCode = a.AgentCode
WHERE TName IN ('%Japan%', '%Australia%')
AND BookOutstanding < 15000;
```
### Question D 
*list the agencies that offer a stay trip to cappadocia with the minimum overall travel period of 7 days*
```sql
SELECT AgentName
FROM Agency a
JOIN Tour t ON t.AgentCode = a.AgentCode
JOIN STOP_AREA sa ON sa.TNo = t.TNo
JOIN Hotel h ON sa.HotelID = h.HotelID
WHERE HotelName LIKE '%Cappadocia'
AND ReturnDate - DepartDate >= 7;
```
### Question E
Agency -> Customer->Tour->Booking -> Payment -> Hotel -> Stop_Area
## Question 2
### Question A
#### Question I
CustEmail. The customer may change his email
#### Question II
invLine_Total. The value is derived from invLine_Price and invLine_Quantity.
InvTotal. Derived from invsubtotal and invtax
#### Question III
CustId in table Invoice. CustID references Customer(CustID)
InvLine_No in table Invoice. InvLine_No references Invoice_line(invline_no)
macCode in table Product. MacCode references Manufacturer(MacCode)
### Question B
#### Question I
supervisorNo references Employee(empID)
managerID references Employee(empID)
#### Question II
Employee(empID, LastName, FirstName, position, salary, branchNo, supervisorNo)
Branch(branchNo, street, city, state, zipCode, phoneNum)
Manager(branchNo, empID, date)
### Question C
#### Question I
Loan. Its copyNo attribute references BookCopy relation
#### Question II
entity integrity
- Primary key values should not have null values
- There are no repetition in primary key values in the relation
Referential integryity
- The values of foreign key in a table must be an existing value in another related relation or wholly `null`
## Question 3
### Question A
#### Question I
StaffID and HotelID. By combining these two attributes, we will get a unique value each time. StaffID and HotelID alone have repeating values.
#### Question II
To insert a staff record, we also have to insert the correct hotelID which can result in repeating values
(Cannot insert a staff record without including hotel information)
Cannot delete staff record without deleting information about the related hotel information
Changing the hotel location for a hotelID would require you to make the same change to every same hotelID
### Question B
#### Question I
![[Past Year Papers/Year 1/Semester 3/Introduction to Database System/Diagrams/september_2021/dependency_diagram|dependency_diagram]]
#### Question II

##### 1NF

| Booking No | Booking Date | Visa Card No | Ticket Price | Customer ID | Customer Name | Customer Address | Flight Number | Flight Date | Departure Country | Departure Time | Arrival Country | Arrival Time |     |     |
| ---------- | ------------ | ------------ | ------------ | ----------- | ------------- | ---------------- | ------------- | ----------- | ----------------- | -------------- | --------------- | ------------ | --- | --- |
|            |              |              |              |             |               |                  |               |             |                   |                |                 |              |     |     |
##### 2NF
**Customer**

| Customer ID | Customer Name | Customer Address |
| ----------- | ------------- | ---------------- |

**Flight**

| Flight Number | Flight Date | Departure Country | Departure Time | Arrival Country | Arrival Time |
| ------------- | ----------- | ----------------- | -------------- | --------------- | ------------ |

**CustomerFlight**

| Booking No | Customer ID | Flight Number | Booking Date | Visa Card No | Ticket Price |
| ---------- | ----------- | ------------- | ------------ | ------------ | ------------ |
##### 3NF
**Customer**

| Customer ID | Customer Name | Customer Address |
| ----------- | ------------- | ---------------- |

**Flight**

| Flight Number | Flight Date | Departure Country | Departure Time | Arrival Country | Arrival Time |
| ------------- | ----------- | ----------------- | -------------- | --------------- | ------------ |

**CustomerFlight**

| Booking No | Customer ID | Flight Number |
| ---------- | ----------- | ------------- |
**Booking**

| Booking No | Booking Date | Visa Card No | Ticket Price |
| ---------- | ------------ | ------------ | ------------ |
## Question 4
### Question A
#### Question I & Question II
**Definition**: The model suggests a defined relationship between entities but the relationship between certain entities become ambiguous under specific occurrences 
![[fan_trap|5000]]
### Question B
#### Question I
![[event_erd|event_erd]]
#### Question III
Strong relationship between event and event performer
Weak relationship between staff and event