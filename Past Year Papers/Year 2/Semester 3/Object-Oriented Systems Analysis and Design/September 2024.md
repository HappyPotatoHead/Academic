---
aliases:
  - September 2024 - OOSAD
tags:
  - PYQ
  - OOSAD
Date: 2025-05-21
Finished Date: 2025-05-21
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1

### Question A

>[!TIP]- How to Answer?
>It's in the lecture notes

Business Process Automation:
- No changes is made to the fundamental ways in which the business operates
- Focus is on automating business processes
- Activities:
	- Problem analysis
		- Analyst and users work together to find out what is wrong with the current system and how to solve it in the new system
	- Root-cause analysis
		- Analyst and users figure out the root cause without the solution
- This is the least expensive
- This has the least potential business value
- This only focuses on one business process
- This is also the last risky
Business Process Improvement
- Little or moderate changes to business processes
- Focus on making current business process more efficient
- Activities
	- Document Analysis
		- Find out how the current system works
	- Informal benchmarking
		- Analyse how other organisation perform their business processes and how we can do something better
	- Activity-based costing
		- Analyses the costs of major processes
- This has moderate risks
- This has moderate potential business value
- This has moderate costs
- This focuses on one business process
Business Process Reengineering
- This changes the fundamental way in which a business process operates
- Activities:
	- Technology Analysis
		- Analyst and manager creates a list of technology that are interesting and find out which would provide business value
	- Outcome Analysis
		- Focus on understanding the outcome that will provide value to the customer
	- Activity Elimination
		- Analyst and Manager work together to find out how to eliminate each activity in business processes.

### Question B

>[!TIP]- How to Answer?
>Define each of them.
>Provide examples of what they do

Perfective maintenance involves making enhances or refinement to the system while preventive maintenance involves seeking out issues and fixing the issue to prevent problems from happening in the future. Perfective maintenance can involve performance improvements, security improvement, or adding new desirable, additional features based on customer feedback, while preventive maintenance involve regular testing and making necessary changes before any issues can occur.  

### Question c

>[!TIP]- How to Answer
>Draw the network diagram. 

#### Question I

| ID  | TE  |
| --- | --- |
| A   | 18  |
| B   | 15  |
| C   | 13  |
| D   | 30  |
| E   | 15  |
| F   | 10  |
| G   | 8   |
#### Question II

| ID  | Slack Time |
| --- | ---------- |
| A   | 0          |
| B   | 0          |
| C   | 42         |
| D   | 0          |
| E   | 40         |
| F   | 0          |
| G   | 0          |

#### Question III

$A \rightarrow B \rightarrow D \rightarrow F \rightarrow G$

### Question B

1. Post Project Review
	- Review the process with stakeholders for feedback for improvements
2. Close Down Project
	- Complete project documentation
	- Complete finance documents
	- Lay offs 
3. Close Customer Contract
	- Notify stakeholders
	- Keep it black and white 
	- Make sure everyone is clear

### Question C

1. Breath of Information
2. Depth of Information
3. Type of Intormation
4. Integration of Information
5. Cost of technique
6. User involvement
## Question 2

### Question A

![[user_vehicle_class_diagram.png]]

### Question B

*This question talks about OOSAD approaches, specifically architecture centric approach where the focus is on defining the structure that the system would be built upon*

Types of Views
1. Static View
	- Describes the structure of the system in terms of attributes, methods, classes and relationships.
	- This often involves drawing diagrams such as ERD diagrams or class Diagrams.
2. Dynamic View
	- Describes the internal behaviour of the system in terms of messages passed between objects and state changes in objects.
	- This involves drawing diagrams such as behaviour diagrams.
3. Functional View
	- The external behaviours of the system based on customer's views.
	- This refers to what the users can do with the system and how the system behaves in response to the user's interaction.

Other two approaches:
1. Use-case Driven
	- Based on what the users can do with the system
	- How the users can interact with the system
	- The behaviour of the system
2. Iterative and Incremental

### Question C

1. Method:
	- Implementation of the object's behaviour
		- An action that the object can perform
	- Equivalent to a function
2. Message
	- Information that is passed to an object to trigger a method
	- Involves calling a method that is implemented in another class.

Difference:
1. Purpose
	- In OOP, method refers to the behaviours that objects of a class have while messages refers to the act of triggering the method of an object while passing additional information if needed. 
2. Existence
	- For messages to work, the required methods have to be implemented first, meaning, messages can't exist on its own. 

### Question D

1. Coupling
	- The degree of closeness of a relationship between classes
	- There is method coupling and inheritance coupling
	- Method coupling
		- Refers to when one object uses method of another object
		- Law of Demeter
			- For an object to call on object's methods, the object must first be an attribute.
	- Inheritance coupling
		- When classes inherit from a superclass
		- The superclass should only have generic methods that can be used on all of the subclasses
2. Cohesion
	- Refers to the degree in which attributes and methods of a class supports a single object
	- Method cohesion
		- Does the method follow the one function one purpose rule
	- Class cohesion
		- Only relevant methods and attributes are defined in the class
	- Generalisation/Specialisation cohesion
		- The hierarchical relationship between classes should be a "kind-of" relationship, not association relationships
3. Connascence 
	- Degree of interdependency between objects
	- It's better to have lower connascence
		- Change in one class does not necessitate change in another class
		- subclasses should not be able to access hidden methods or attributes of superclass.

## Question 3

### Question A

![[train_context_level|700]]

### Question B
![[Past Year Papers/Year 2/Semester 3/Object-Oriented Systems Analysis and Design/Diagrams/september_2024/activity_diagram|700]]

### Question C
1. Condition Stub
2. Action Stub
3. Indifferent conditions
4. Rules

# Section B

## Question 4

### Question A

Conditions:
```run-python
if item_type == "household_product":
	print("Redeem points with additional cash")
elif item_type == "well-known brand items":
	print("Redeem item purely with points")
else:
	print("Don't redeem")
```


| Condition Stub | -   | Condition/Actions           | Rules | <   | <   | <   |
| -------------- | --- | --------------------------- | ----- | --- | --- | --- |
| ^              | -   | Well-known brand            | -     | -   | Yes | Yes |
| ^              | -   | Household product           | -     | Yes | -   | Yes |
| Action Stub    | -   |                             | <     | <   | <   | <   |
| ^              | -   | Redeem only with points     | -     | -   | X   | -   |
| ^              | -   | Redeem with additional cash | -     | -   | -   | X   |
| ^              | -   | No redemption               | X     | X   | -   | -   |
### Question B
1. Software Component
	- Data storage 
	- Data access logic
	- Presentation logic
	- Application Logic
2. Hardware Component
	- Client
	- Server
	- Network

### Question C

1. Factoring
	- Create models that account for differences and similarities between units of interests
	- Create new classes
		- Generalisation
		- Aggregation
2. Partitioning
	- Dividing the system into smaller, more manageable subsystems
	- Determine which classes should work together
3. Layering
	- Divide the system into several independent layers that provides services and functions
	- Each layer can be replaced, given that the interfaces remain the same. 
	- If the services and interfaces changes, only adjacent layers are affected. 

### Question D
1. Node
	- A piece of hardware
2. Artifact
	- A piece of information generated from software development process or deploying and operating a system
3. Communication Path
	- The link between the nodes

## Question 5

### Question A

*There are six principles of user interface design*
1. Layout
	- Information should be evenly spaced
		- Padding
		- Margin
	- Information should be easily discernible. 
	- Add navigation
2. Content Awareness
	- Only include relevant information
3. Aesthetic
	- Avoid colours that blend in together
	- <mark style="background: #FF5582A6;">Bold important information to catch the attention of the user</mark>
	- <mark style="background: #FF5582A6;">Use different colours to highlight important information or data</mark>
		- *These are more towards content awareness*
4. User Experience
	- Ease of use
		- Easier for new users to pick up
		- The focus for applications with wide user base
	- Ease of learning
		- Meant for applications used by experts
	- There is a need to strike a balance between ease of use and ease of learning
5. Consistency
	- Predictable and the user only has to learn from one portion of the system and apply it to another portion of the system
6. Minimal user effort
	- Three click rule

Differences:
1. Layout refers to the structure in which the designer should place the information while aesthetics focuses on making the information or data more visually appealing and minimal user effort refers to allowing users to perform a certain actions with minimal efforts. 

### Question B
1. Database Normalisation
2. Remove redundant attributes or remove null values
3. Indexing
4. Estimating data storage size

### Question C

![[window_navigation_diagram|700]]

### Question D

1. Analysis model
	- Functional requirements of the system
	- Diagrams involved:
		- DFD
		- Use Case 
		- Activity
2. Design model
	- Non-functional requirements of the system
		1. Performance
		2. Security
		3. Cultural and political
		4. Operational 
	- Diagrams involved:
		- Sequence diagram
		- Timing diagram
		- Communication diagram
		- Behavioural state machine
		- Protocol state machine
		- Interaction overview diagram
### Question E
1. Repeating groups
2. Partial functional dependency
3. Transitive dependency

# Next Paper

[[Past Year Papers/Year 2/Semester 3/Object-Oriented Systems Analysis and Design/May 2024|May 2024]]