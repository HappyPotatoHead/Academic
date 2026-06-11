---
aliases:
  - Introduction to ADIS
tags:
  - Notes
  - ADIS
Date: 2024-01-30
Completion: true
obsidianUIMode: preview
---
# Introduction 
## Information Systems Analysis and Design
1. Complex organisational process
	- Involves:
		1. Money
		2. Manpower
		3. Technology
		4. Co-operation between client and server
1. Used to develop and maintain computer-based information systems
2. Used by a team of business and systems professionals
	- Use a methodology to develop a system to fulfil the customer's wishes, complete requests on time, and make customers happy.
## Approach to system analysis and design
- [?] Driven by methodologies, techniques and tools
	- [I] Determine the wishes and requirements demanded by the customers
	- [I] Tools
		1. Questionnaires
		2. Interviews
>[!EXAMPLE] Microsoft
>Microsoft gathers data from the customers who uses the operating system to further enhance and fine-tune the system

## Application software
- [?] Computer software designed to support organisational functions or processes.
- [I] Software is used to help with processes. 
## Systems ==Analyst== 
- [?] Organisational role that is most responsible for analysis and design of information system
- [I] Communicate with customers to get their wishes and requirements.
	- Questionnaire 
	- Interviews
# Types of Information Systems and Systems Development
## Transaction Processing Systems (TPS)
- [i] collects how much money has been transacted 
- [i] The method of transaction 
- [i] Processes the transaction of an outlet/business into a system 
## Management Information Systems (MIS)
- [i] Processes the data collected from *TPS* to readable and meaningful data to be analysed. 

>[!EXAMPLE] Business
>The employee behind MIS processes the sales from a mall, analysing which product is making the most profit and the least.
>
## Decision Support Systems (DSS)
- [i] Makes decision from the prediction made from the processed data from *MIS*
- [i] Designed to help decision makers
- [i] Provides interactive environment for decision making. 
	- Uses data and information from other countries
- [i] Involves data warehouses, executive information systems (*EIS*)
	- Experts are required
- [i] Database, model base, user dialogue 
### Predicting the future
*Example: COVID trajectory*
1. Using data from other countries to predict the rise and fall of infections
2. sing ai and help of experts
*Example: Business*
1. Determine whether a product should be expanded or discontinued
# Developing Information Systems
## System Development Methodology 
- [?] A standard process followed by an organisation/ company follows to analyse, maintain, develop or their information system
# System Development Life Cycle, SDLC
- [?] Develop, maintain and replace information system
**Phases->PADIM** 
1. **P**lanning
2. **A**nalysis
3. **D**esign
4. **I**mplementation 
5. **M**aintenance
**The heart of the system**
1. **A**nalysis
2. **D**esign
3. **I**mplementation (Small part of it)
*Example: Are the customers happy?*
Showing **prototype** to the customer. Ask them questions/reviews

**Analysis-Design-Code-Test** loop
*Example: Developing a game*
The developer will run beta/alpha tests to gain the players' feedback and complaints. 
## Planning - Analyse the back-end
- [?] Identifying, analysing, prioritising, and arranging the needs to develop and implement the system
- Determine the manpower, expertise, monetary fund, the profits, the importance, the demand from customers
## Analysis - Analyse the customer
- [?] System requirements for the system
- The **system analyst** conducts interview with customers/target users to determine their requirements/demands about the system.
## Design - Prototype/ Sketch
- [?] A description of the recommended solution is converted into logical and the physical system specifications
### Logical Design
- [?] Designing and sketching the demands and requirements regardless of the computer platform
*Example: Games*
Customers demand 3d avatars. The people behind the system will now try to implement the demands and requirements. **Just sketching/designing**
### Physical Design
- [?] The logical specifications of the system from logical design are converted into technology-specific details from which all programming and system construction can be accomplished
- [?] After **Logical Design**, the developer has to now determine the technology needed/system requirements needed to develop the demands and requirements
	- selecting specific hardware and software components, creating detailed system diagrams and layouts, and defining the specific requirements for each component.
- The developers now transform the logical design into a concrete physical system
*Example: Games*
A strong GPU is needed
## Implementation - Programming
- [?] The information system is coded, tested, installed, and supported in the organisation
## Maintenance - Preserve
- [?] Improving and repairing/debugging the system
*Example: Games*
Providing customer support/manual to answer the customers' questions
## Traditional Waterfall SDLC
Used when the project is small-scale, little budget, short. 
**See:** [[Chapter 1 - Introduction of Information System Analysis and Design#System Development Life Cycle, SDLC|SDLC]]
![[traditional_sdlc.png]]*Waterfall SDLC does not allow any back tracking, it's just to complete the project ASAP* 
There is little involvement from customers except from in **analysis** and **implementation**
## Problem with Waterfall SDLC
1. System requirements cannot no longer be changed after being determined by the customers or developer. *LOCKED IN*
2. Limited user involvement
3. Too much focus on milestone deadlines of SDLC phases to the detriment of sound development practices
	- Ignores recommended practices or procedures for the sake of finishing the project or system
# Different Approaches to Improving Development
**CARES**
1. Computer-Aided Software Engineering, *CASE*
	- Applications used to draw diagrams/*illustration*
2. Rapid Application Development, *RAD* (Type of methodology)
3. Service Oriented Architecture, *SOA*
	- Used in banking system
4. Agile Methodologies
	- Used in big companies
5. eXtreme Programming
	- Used in Gaming application/software
## Computer-Aided Software Engineering Tools
**Types of CASE tools**
- **Analysis tools**
	- Checks for: (in diagrams, forms, and reports)
		1. Consistency
		2. Completeness 
		3. Correctness
	- Compares ERD and SQL 
- **Central repository (main storage)**
	- Enables integrated storage of: 
		1. Diagrams
		2. Reports 
		3. Project management specifications
- **Code generators**
	- Automatic generation of:
		1. Programs and database code **from**
			1. Design
			2. Documents
			3. Diagrams
			4. Forms
			5. Reports
	- Construct SQL codes from ERD diagrams
## Rapid Application Development, RAD
Fast development of the system. It radically decrease design and implementation time
This methodologies involves:
1. **Extensive user involvement**
2. **Prototyping**
	1. Changes based on feedback
3. **Joint Application Design, *JAD* session**
	1. Intensive requirements collection
		2. The individuals behind the project will group and interview with the customers
	2. Prototyping begins immediately in the session until customer is satisfied
	3. Once completed, implementation is completed
	4. Can go on for minimum of 4 hours and a maximum of 10 days
5. **integrated CASE tools, iCASE**
6. **Code generators**
**PHASES**
![[rad.png]]
**Requirement planning and user design**
1. Focuses on system function, user interface, and performance issue
	1. What can the system do?
	2. How will the user interface be?
	3. Minimum system requirements
2. Emphasises on doing different tasks in parallel with each other and uses prototyping extensively (*until the customer is satisfied*)
	1. Less emphasis on the sequence and structure of processes (*ignores the steps*)
	2. Much of end user involves from the beginning of the development process, go through prototyping process until a satisfactory prototype is agreed upon.
3. Construction
	1. Generate code using *CASE* or any IDE(*VSCODE, Visual Studio*)
4. Cutover
	1. Delivery of the system to the end user
	2. The end users tests the systems
	3. Train the users on how to use it
	4. Deal with organisation changes
	5. Running the old and new system in parallel until business process is stable
		1. A good example will be windows version where older version are still supported for a period of time when a new version is released.
**Differences**
SDLC follows the steps but RAD just *flies through it* - focuses on the design part and implementation part. RAD also involves end users a lot more. This is for a faster development
## Service-Oriented Architecture, SOA
>[!IMPORTANT] 
>This is not a methodology

Mainly for service purposes. This methodology adds new services into an existing system. Thus, a system that has a lot of services is known as *Service-Oriented Architecture* (*This can be found in the banking system, credit card, or debit card*).
![[soa.png]]
## Agile Methodologies/ Open
Commonly used in Tech companies: Apple.
Used in mobile applications, software applications
Critical systems such as self-driving cars do not use this
The company does not put much emphasis on the roles, position, or ranking. Everyone is free to propose their ideas 
**Has 3 principles**
1. Focus on adaptive rather than predictive methodologies
	1. Opposite of waterfall SDLC
	2. This methodology welcomes changes
2. Focus on people rather than roles
	1. Anyone and contribute an idea
3. Focus on self-adaptive process
	1. As a software is developed, the process should be refined and improved
## eXtreme Programming 
Used in games development
Uses two person programming teams, one will code with the other testing it
**Design specifications**
1. Planning, analysis, design, and construction are all fused into a single phase of activity
	1. Coding
	2. Testing
2. Unique way of capturing and presenting system requirements and design specifications