# Practical 1

```sql 

--- Question 1
conn scott/tiger
UPDATE region 
SET region_name = 'South Africa'
WHERE region_id = 123;

--- Question 3

CREATE TABLE mod_emp (
	last_name VARCHAR2(20),
	salary NUMBER(8,2)
);

-- Allowed
ALTER TABLE mod_emp MODIFY (last_name VARCHAR2(30)); 
-- Not Allowed
ALTER TABLE mod_emp MODIFY (last_name VARCHAR2(10)); 
-- Allowed
ALTER TABLE mod_emp MODIFY (salary NUMBER(10,2)); 
-- Not Allowed
ALTER TABLE mod_emp MODIFY (salary NUMBER(8,2) DEFAULT 50);

-- Question 4
CREATE TABLE my_table (
	id NUMBER(3) NOT NULL,
	name VARCHAR2(50) NOT NULL,
	hobbies VARCHAR2(50) NOT NULL,
	favourite_song VARCHAR(100) NOT NULL,
	favourite_book VARCHAR(100) NOT NULL,
	lucky_number NUMBER DEFAULT 0,
	birthdate DATE NOT NULL,
	
	CONSTRAINT my_table_id_pk PRIMARY KEY (id);
);

CREATE TABLE my_tablecopy1 AS (SELECT * FROM my_table);
CREATE TABLE my_tablecopy2 AS (SELECT id as PID, name as PNAME, hobbies as PHOBBIES FROM my_table);

-- Question 5
ALTER TABLE location
RENAME TO new_location
```

# Practical 2

```sql
-- Question 1 - To create a query that lists the names of all projects and the names of their associated subprojects

SELECT DISTINCT p.project_name as name, pp.project_name as parent_project
FROM project p
JOIN project pp 
ON p.p_id = pp.parent_p_id;

-- Question 2 - Suppose you need to retrieve the first, last names of all students who have the same S_CITY value as student Sarah Miller.

SELECT DISTINCT s_first || ' ' || s_last as name
FROM student
WHERE s_city IN (
	SELECT s_city 
	FROM student 
	WHERE s_first = 'Sarah' 
	AND s_last = 'Miller'
);

-- Question 3 - Suppose you want to retrieve the names of all students who have the same S_CLASS value as Amanda Mobley and have also been enrolled in a course section with her.

SELECT DISTINCT s_first || ' ' || s_last as name
FROM student s
JOIN enrollment e
ON s.s_id = e.s_id
WHERE s_class = (
	SELECT s_class
	FROM student 
	WHERE s_first = 'Amanda' 
	AND s_last = 'Mobley'
)
AND c_sec_id IN (
	SELECT c_sec_id 
	FROM enrollment e
	JOIN student s
	ON s.s_id = e.s_id 
	WHERE s_first = 'Amanda' 
	AND s_last = 'Mobley'
);

-- Question 4 - To create a query to retrieve the names of students who have taken courses with Amanda Mobley in the CR building.

SELECT DISTINCT s_first || ' ' || s_last as name
FROM student s
JOIN enrollment e
ON s.s_id = e.s_id
WHERE e.c_sec_id IN (
	SELECT e.c_sec_id 
	FROM enrollment e
	JOIN course_section cs
	ON e.c_sec_id = cs.c_sec_id
	JOIN location l
	ON cs.loc_id = l.loc_id
	JOIN student s
	ON s.s_id = e.s_id
	WHERE bldg_code = 'CR'
	AND s_first = 'Amanda'
	AND s_last = 'Mobley'
);

-- Question 5 - Create a script named P2Q5.sql that contains the commands for the following queries that retrieve data from the Software Experts database. 

-- i. Display the first and last names of all consultants who have worked on all projects for Morningstar Bank. 

SELECT c_first || ' ' || c_last AS name
FROM consultant c
JOIN project p
ON c.c_id = p.mgr_id
JOIN client cl
ON p.client_id = cl.client_id
WHERE client_name = 'Morningstar Bank';


-- ii. Display the name of each project that consultant Mark Myers has ever worked on and the name of the project’s client.

SELECT project_name as name, client_name as client
FROM project p
JOIN consultant c
ON p.mgr_id = c.c_id
JOIN client cl
ON p.client_id = cl.client_id
WHERE c_first  = 'Mark'
AND c_last = 'Myers'
```

# Practical 4

```sql
/*
Question 1
Write program commands to declare a numeric variable named my_counter and a variable-length character string variable named my_string. 
Assign the value 1000 to my_counter, and the text "Hello world" to my_string, and display the values for my_counter and my_string.

Output 1: 
	My string is Hello world 
	My counter is 1000 
Output 2: 
	My string is Hello world and my counter is 1000.
*/

SET SERVEROUTPUT ON

DECLARE 
	my_counter NUMBER := 1000;
	my_string VARCHAR2(25) := 'Hello World';
BEGIN
	DBMS_OUTPUT.PUT_LINE('My string is ' || my_string);
	DBMS_OUTPUT.PUT_LINE('My counter is ' || my_counter);
	
	DBMS_OUTPUT.PUT_LINE('My string is ' || my_string || ' and my counter is ' || my_counter);
END;
/

/*
Question 2
Create an anonymous block. Add a declarative section to this PL/SQL block. In the declarative section declare the following variables: 

1. Variable today of type DATE. Initialize today with SYSDATE. 
2. Variable tomorrow of type today. Use variable.
*/

DECLARE
	today Date := SYSDATE;
	tomorrow today%TYPE;
BEGIN
	DBMS_OUTPUT.PUT_LINE(today);
	DBMS_OUTPUT.PUT_LINE(tomorrow);
END;
/

/*
Question 3
In the executable section initialize the variable tomorrow with an expression which calculates tomorrow’s date (add one to the value in today). Print the value of today and tomorrow after printing ‘Hello World’.
*/

DECLARE
	today Date := SYSDATE;
	tomorrow today%TYPE;
BEGIN
	tomorrow := today + 1;
	DBMS_OUTPUT.PUT_LINE('Hellow World');
	DBMS_OUTPUT.PUT_LINE(today);
	DBMS_OUTPUT.PUT_LINE(tomorrow);
END;
/

/*
Question 4
Write commands to declare character variables named faculty_last_name, faculty_first_name, and faculty_phone. 
Assign the value ‘O’BRIEN’ to faculty_last_name, ‘SALLY’ to faculty_first_name, and 7155551234 to faculty_phone. 
Write program commands so that the programs displays the output exactly as follows: Sally O’Brien’s phone number is (715) 555-1234.
*/

DECLARE 
	faculty_last_name VARCHAR2(50) := 'O''BRIEN';
	faculty_first_name VARCHAR2(50) := 'SALLY';
	faculty_phone VARCHAR2(50) := '7155551234';
BEGIN
	DBMS_OUTPUT.PUT_LINE(faculty_first_name || ' ' || faculty_last_name || '''s phone number is (' || SUBSTR(faculty_phone, 1, 3) || ') ' || SUBSTR(faculty_phone, 4, 3) || '-' || SUBSTR(faculty_phone, 8, LENGTH(faculty_phone)) );
END;
/
```

# Question 5

```sql
DECLARE 
	current_date DATE := SYSDATE;
	v_month VARCHAR2(10);
	v_day NUMBER(2);
BEGIN
	DBMS_OUTPUT.PUT_LINE(TO_CHAR(current_date, 'YYYY Month DD'));
END;
/
```
# Set 16

```sql
SELECT employee_id AS "Employee#", last_name AS "Last Name", j.job_title AS "Job", hire_date AS "Hire Date"
FROM employees e
JOIN jobs j
ON e.job_id = j.job_id;

SELECT d.department_name, MAX(salary) 
FROM employees e 
RIGHT JOIN departments d
ON e.department_id = d.department_id
GROUP BY (d.department_name);

SELECT first_name || ' ' || last_name as name
FROM employees 
WHERE salary NOT BETWEEN 2000 AND 20000;

SELECT COUNT(*) 
FROM employees 
WHERE commission_pct IS NULL;
```

```sql
SELECT INITCAP(last_name), LENGTH(last_name)
FROM employees
WHERE first_name LIKE 'J%'
OR first_name LIKE 'A%'
OR first_name LIKE 'M%';

SELECT last_name, salary, commission_pct
FROM employees
WHERE commission_pct IS NOT NULL
ORDER BY salary DESC, commission_pct DESC; 

SELECT first_name || ' ' || last_name as name, department_name
FROM employees e
JOIN departments d
ON e.department_id = d.department_id
WHERE e.department_id IN (
	SELECT department_id
	FROM departments
	WHERE manager_id IS NULL
);

SELECT department_name 
FROM departments 
WHERE manager_id IS NULL;

CREATE OR REPLACE FUNCTION convert_salary(
	p_salary Is NUMBER
)
RETURN VARCHAR2
IS 
	v_salary VARCHAR2(7);
BEGIN
	v_salary := TO_CHAR(p_salary, '$99,999.99');
	RETURN v_salary;
END;
/

DECLARE
	v_commission NUMBER(2);
BEGIN
	SELECT commission
	INTO v_commission
	FROM employees
	WHERE employee_id = 101;
	
	DBMS_OUTPUT.PUT_LINE(v_monthly_salary * 12);
END;
/

SELECT first_name || ' ' || last_name as name, (IF )

DECLARE
	v_monthly_salary NUMBER(5);
BEGIN
	SELECT salary
	INTO v_monthly_salary
	FROM employees
	WHERE employee_id = 101;
	
	DBMS_OUTPUT.PUT_LINE(v_monthly_salary * 12);
END;
/
```

# Set A

![[practical_test_2.jpg]]

```sql
ALTER SESSION SET '_oracle_script' = true;
SET SERVEROUTPUT ON;

CREATE ROLE Josh
IDENTIFIED BY "default123";

GRANT CREATE SESSION
TO Josh
WITH ADMIN OPTION

GRANT CREATE TABLE 
TO Josh
WITH ADMIN OPTION

CREATE OR REPLACE VIEW staff_view
AS 
SELECT first_name || ' ' || last_name AS "Employee's Name", d.department_name AS "Department Name",
FROM employees e
JOIN departments d
ON e.department_id = d.department_id
WHERE d.manager_id IS NOT NULL;

SELECT COUNT(employee_id) AS "Total Employee"
FROM employees
WHERE commission_pct IS NULL 
AND SALARY > 10000;

SELECT DISTINCT mgr.first_name || ' ' || mgr.last_name AS "Manager's name", d.department_name, l.city
FROM employees e
JOIN employees mgr
ON e.manager_id = mgr.employee_id
JOIN departments d
ON e.department_id = d.department_id
JOIN locations l
ON d.location_id = l.location_id
ORDER BY city DESC;

SELECT SUM(salary)
FROM employees e
JOIN jobs j
ON e.job_id = j.job_id
WHERE LOWER(job_title) = 'programmer';

SELECT first_name || ' ' || last_name AS "Employee's Name"
FROM employees
WHERE LOWER(SUBSTR(last_name, 3, 1)) = 'o'
OR LOWER(SUBSTR(last_name, 3, 1)) = 'u';

SELECT COUNT(department_id)
FROM deparments d
JOIN locations l
ON d.location_id = l.location_id
WHERE city = 'London';

CREATE SEQUENCE DeptSeq
INCREMENT BY 5
START WITH 300
MAXVALUE 500
NOCYCLE

INSERT INTO Departments (department_id, department_name) 
VALUES (DeptSeq.NEXTVAL, 'Dummy Department');

DECLARE
	v_first_name VARCHAR2(20);
	v_last_name VARCHAR2(25);
	v_employee_id NUMBER(5) := 100;
BEGIN
	SELECT first_name, last_name 
	INTO v_first_name, v_last_name
	FROM employees
	WHERE employee_id = 100;

	DBMS_OUTPUT.PUT_LINE('ID :' || v_employee_id);
	DBMS_OUTPUT.PUT_LINE('First Name: ' || v_first_name);
	DBMS_OUTPUT.PUT_LINE('Last Name: ' || v_last_name); 
END;
/

DECLARE
	v_employee_id NUMBER(5) := 100;
	v_salary NUMBER(8, 2);
	v_annual_salary NUMBER(10,2);
BEGIN
	SELECT salary 
	INTO v_salary
	FROM employees
	WHERE employee_id = v_employee_id;

	v_annual_salary := v_salary * 12;

	DBMS_OUTPUT.PUT_LINE('Annual Salary:' || TO_CHAR(v_annual_salary, '$999,999,999.99'));
END;
/
```

# Set B

![[set_b.jpg]]

```sql
ALTER SESSION SET "_oracle_script" = true;
SET SERVEROUTPUT ON;

CREATE ROLE Peter 
IDENTIFIED BY user123;

GRANT CREATE VIEW
TO Peter
WITH ADMIN OPTION;

GRANT CREATE TABLE 
To Peter 
WITH ADMIN OPTIONS;

CREATE OR REPLACE VIEW newstaff_view
AS 
SELECT employee_id AS "Employee ID" , first_name || ' ' || last_name AS "Name",  job_title AS "Job Title"
FROM employees e
JOIN jobs j
ON e.job_id = j.job_id
WHERE e.salary >= 10000;

SELECT COUNT(employee_id) AS "Total Employee"
FROM employees
WHERE commission_pct IS NULL
AND salary > 10000;

SELECT d.department_name, l.street_address, l.city, c.country_name
FROM departments d
JOIN locations l
ON d.location_id = l.location_id
JOIN countries c
ON l.country_id = c.country_id
ORDER BY country_name DESC;

SELECT SUM(salary)
FROM employees e
JOIN jobs j
ON e.job_id = j.job_id
WHERE LOWER(job_title) = 'stock manager' 
OR LOWER(job_title) = 'sales manager';

SELECT employee_id AS "Employee ID" , first_name || ' ' || last_name AS "Employee's Name"
FROM employees 
WHERE LOWER(last_name) LIKE '%an'
OR LOWER(last_name) LIKE '%pp';

SELECT COUNT(department_id)
FROM departments d
JOIN locations l
ON d.location_id = l.location_id
JOIN countries c
ON l.country_id = c.country_id
WHERE c.country_id = 'UK';

CREATE SEQUENCE LocationSeq
INCREMENT BY 10
START WTIH 4000
MAXVALUE 8000
NOCYCLE

INSERT INTO locations(location_id, street_address, postal_code, city, state_province, country_id)
VALUES(LocationSeq.NEXTVAL, "123 Krusty Krab", "32000", "United Kingdom", "Bikini Bottom", "UK");

DECLARE
	v_job_title VARCHAR2(35);
	v_max_salary NUMBER(6);
	v_job_id VARCHAR2(10) := 'ac_mgr';
BEGIN
	SELECT job_title, max_salary
	INTO v_job_title, v_max_salary
	FROM jobs
	WHERE LOWER(job_id) = v_job_id;
	
	DBMS_OUTPUT.PUT_LINE('Job title: ' || v_job_title);
	DBMS_OUTPUT.PUT_LINE('Maximum Salary: ' || v_max_salary); 
END;
/

DECLARE
	v_commission_earned NUMBER(10, 2);
	v_commission_percentage NUMBER(2,2);
	v_salary NUMBER(8,2);
	v_employee_id NUMBER(6) := 176;
BEGIN
	SELECT salary, commission_pct
	INTO v_salary, v_commission_percentage
	FROM employees
	WHERE employee_id = v_employee_id;
	
	v_commission_earned := v_salary * v_commission_percentage;
	
	DBMS_OUTPUT.PUT_LINE('ID: 176');
	DBMS_OUTPUT.PUT_LINE('Salary: ' || v_salary);
	DBMS_OUTPUT.PUT_LINE('Commission Percentage: ' || v_commission_percentage);
	DBMS_OUTPUT.PUT_LINE('Commission Earned: ' || v_commission_earned);
END;
/
```

# Set F

![[set F.jpg]]

```sql
CREATE ROLE Peter
IDENTIFIED BY user123;

GRANT CREATE VIEW
TO Peter 
WITH ADMIN OPTION;

GRANT CREATE TABLE
TO Peter
WITH ADMIN OPTION;

CREATE OR REPLACE VIEW newstaff_view
AS 
SELECT employee_id AS "Employee ID", first_name || ' ' || last_name AS "Name", job_title AS "Job Title"
FROM employees e
JOIN jobs j
ON e.job_id = j.job_id
WHERE min_salary > 10000;

SELECT COUNT(employee_id) AS "Total Employee"
FROM EMPLOYEES
WHERE commission_pct IS NULL
AND salary > 10000;

SELECT d.department_name, l.street_address, l.city, c.country_name
FROM departments d
JOIN locations l
ON d.location_id = l.location_id
JOIN countries c
ON l.country_id = c.country_id
ORDER BY country_name DESC

SELECT AVG(e.salary)
FROM employees e
JOIN jobs j
ON e.job_id = j.job_id
WHERE LOWER(job_title) IN ('shipping clerk', 'stock clerk');

SELECT first_name || ' ' || last_name AS "Employee's Name"
FROM employees
WHERE last_name LIKE '%as' 
OR last_name LIKE '%oo';

SELECT COUNT(department_id)
FROM departments d
JOIN locations l
ON d.location_id = l.location_id
JOIN countries c
ON l.country_id = c.country_id
WHERE c.country_id = 'UK';

CREATE SEQUENCE LocationSeq
INCREMENT BY 10
START WITH 4000
MAXVALUE 8000
NOCYCLE;

INSERT INTO locations(location_id, city)
VALUES(LocationSeq.NextVal, 'UK');

DECLARE
	v_job_title VARCHAR2(35);
	v_max_salary NUMBER(6);
	v_job_id VARCHAR2(10) := 'ac_mgr';
BEGIN
	SELECT job_title, max_salary
	INTO v_job_title, v_max_salary
	FROM jobs
	WHERE LOWER(job_id) = v_job_id;

	DBMS_OUTPUT.PUT_LINE('Job title: ' || v_job_title);
	DBMS_OUTPUT.PUT_LINE('Max salary: ' || v_max_salary);
END;
/

DECLARE
	v_salary NUMBER(8,2);
	v_commission_pct NUMBER(2,2);
	v_commission NUMBER(10,2);
	v_employee_id NUMBER(6) := 176;
BEGIN
	SELECT salary, commission_pct
	INTO v_salary, v_commission_pct
	FROM employees
	WHERE employee_id = v_employee_id;
	
	v_commission := v_salary * v_commission_pct;	

	DBMS_OUTPUT.PUT_LINE('Salary: ' || v_salary);
	DBMS_OUTPUT.PUT_LINE('Comission .pct: ' || v_commission_pct);
	DBMS_OUTPUT.PUT_LINE('Commission earned: ' || v_commission);
END;
/
```