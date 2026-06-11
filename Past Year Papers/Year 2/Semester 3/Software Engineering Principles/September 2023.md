---
aliases: 
tags:
  - PYQ
  - SEP
Date: 
Finished Date: 
Completion: true
obsidianUIMode: preview
---
# Section A

## Question 1

### Question A

#### Question I

Plan-driven development. This is because the duration of the project is around two years. Plan-driven development is better when it comes to projects with long duration. Additionally, the team can only move on from one phase to another phase when they are done with the current phase. This coincides with the characteristics of plan-driven approach.

#### Question II

1. Cost and frequency of change
	- Changing requirements can be expensive in this approach as feedback and reviews are only given at the end of each phases. 
	- The frequency of changes are also limited to the end of each phases.
2. The most critical non-functional requirement
	- The most critical non-functional requirement is security which involves rigorous testing over a long period of time. This requirement generally does not require users to be around to provide feedback.
3. Software lifetime and delivery schedule
	- The software created is meant to last a long time. Because of this, formal and detailed documentation is needed to ease maintenance and changes, which is often ignored in extreme programming approach. 
	- The time between development and deliverable is longer in plan-driven approach rather than extreme programming

#### Question II

1. Maintenance
	- The software should be easy to read, optimised, and follow best practices to ease maintainability and software evolution. 
2. Acceptability
	- The user should be able to easily transition from their current system to the newly developed system.
	- The system should be easy to use and does not cause frustration while using it.
3. Dependency and Security
	- The software should not cause malware and harm to both the user and the user's computers
	- It should also be able to defend against malicious users. 
4. Efficiency
	- The software should not use more hardware resources than it should. 

### Question B

1. Biases
	- Since the software engineers are the ones building the software, they may be reluctant to admitting system faults as it would impact their self-confidence.
2. Effort
	- The software engineers have already exerted a lot of effort and time in building the software; the software engineers may be reluctant to keep working on the same software  
3. Over-confidence
	- The software engineers may assume that practicing best practices would guarantee zero system faults, leading them to not actively seek them out. 
4. Lack of fresh perspective
	- There is no additional group of people who did not work on the system that can provide views that were not considered

### Question C

1. Continuous feedback 
	- Incremental development approach works by constantly getting feedback from the users. This makes the approach flexible and changes can be made quickly to fit user's requirements, reducing overall costs
2. Noticeable outcome
	- Incremental development approach provides small, frequent updates to the users. Because of this, the users can view the progress of the development much closely
3. Reduced costs due to changing requirements
	- Since the approach focuses on getting users' feedback, it is meant to be flexible when it comes to requirements. By making changes to the software as soon as possible, the cost of making changes are greatly reduced, especially in comparison to plan-driven approach.

## Question 2

### Question A

1. Customer involvement
	- This requirement describes the need for extensive customer involvement in the development of the system, since certain systems may value customer feedback a lot
2. Lifetime of system
	- Systems that are meant to last a long time are better off being developed with plan-driven development approach rather than agile development approach due to the importance of formal documentation in such systems. 
	- Agile development approach often ignores formal documentation, making maintenance more difficult down the line.
3. Size of system
	- Systems of smaller sizes are better made with agile development approach as less thorough research is generally needed. 

### Question B

1. Daily Scrum
	- Have a daily meeting with the development team to discuss progress and raise any issues or problems
2. Sprint review
	- Showcase the deliverable to the stakeholders at the end of each sprints to get feedback
3. Sprint retrospective
	- Have a post sprint review to get feedback on how the sprint was conducted

### Question C

1. Collective Ownership
	- Pair programming involves a driver - codes - and a navigator - reviewer. Both of them are required to work on the same code, driving them to put the effort in ensuring the best possible outcome. 
2. Test-driven Development
	- The navigator or reviewer would be reviewing the code written by the driver, allowing any errors or bugs to be raised and fixed quickly. This also ensures that the features being developed meet the requirements in the first place.   
3. Refactoring
	- Every time the reviewer views the code, he or she would suggest a more efficient or optimised way to write the code. This ensures that the code is written in the most optimised way most of the time.

### Question D

1. As a customer, I want to be able to search for my desired hotels so that I don't have to scroll through countless number hotels.
2. As a customer, I want to be able to set a filter when searching for hotel that I can find the one most suited to me
3. As a customer, I want to be able to directly purchase the ticket so that I don't have to physically wait in line to purchase a ticket
4. As a customer, I want to receive a reminder before my check-in and check-out so that I can arrive on time and do not overstay as well. 
5. As a customer, I want the system to suggest me hotels nearby my location so that I can easily pinpoint what is available to me.

## Question 3

### Question A

*Architectures*
1. *MVC*
2. ~~*Layered*~~
3. *Microservice*
4. ~~*Client-server*~~
5. ~~*Repository*~~

#### Question I

Model-View-Controller architecture, or MVC. This is because the reporting system involves creating multiple types of visualisations for different purposes which is what MVC architecture excels at. MVC allows multiple views to be applied on the same models or multiple models on the same views. This provides flexibility to the development of the system as well as saving time. 

#### Question II

1. Model
	- Handles system data and the operations associated with it
2. View
	- Handles how system data is presented to the user
3. Controller
	- Handles user interaction and passes information to the views and models

#### Question III

1. Modularity and re-usability 
	- The clear separation of concern allows the models to be reusable in the same systems or in different systems
2. Durability
	- The clear separation of concern also provides independence amongst the components. This means that when one of the component malfunctions, the system can still function. 

### Question B

1. **D**ocumented
	- The components are clearly documented
	- The functionality, interfaces and behaviour of the component should be clearly written so that they can be reused easily.
2. **I**ndependent
	- The components should be able to be able to function as a independent entity and does not depend on the services of other components
	- However, if dependencies exist, it should be stated clearly
3. **S**tandardised
	- The components should conform to a set of standards
	- The interfaces, metadata, and the documentation.
4. **C**omposable
	- A composable component should have a publicly defined interface in which all external interaction takes place. 
	- The component should also provide an access point to its information such as attributes 
5. **D**eployable
	- The component should be deployable as a standalone entity on a component platform that demonstrates the component's ability

### Question V

Factory method. This creational design pattern allows objects to be created without specifying the specific classes, but rather allows the subclasses to decide the specific class to instantiate. UX framework consists of a multitude of elements, each with their own classes. Factory method allows the creation of these elements, while maintaining the flexibility of change, which is crucial in the context of UI UX design. For example, creating a button first before deciding whether it should be a navigation button, confirmation button, or a reset button. 

*Abstract factory works too. \<describe>, \<say why the description works>, \<give an example (buttons can become navigation button, reset button, etc..)>*

# Section B

## Question 4

### Question A

1. Vendor
	- I am not in control what the vendor does with the reusable component. The vendor may decide to stop development and there is nothing much that I can do about it. Additionally, the vendor may have a poor reputation in the industry
2. Product
	- The component may not be able to fulfill my requirements, forcing me to reevaluate and compromise on my requirements. 
3. Process
	- The reusable components may have incompatible interface which makes it difficult to integrate with my existing system or into my workflow. 

### Question B

Valid test case:

The numbers inserted must be integers
The number of allowed inputs of numbers must be only two

Invalid test cases

The numbers inserted are numbers with floating points
More than two inputs are inserted into the system
Texts, files, or images are inserted into the text fields

### Question C

1. Error correction
	- Fix errors found by users after the software has been released
2. Performance improvement
	- Optimisation of the system to allow a wider array of users to use the software, especially those on older hardwares
3. Changing requirements
	- User's requirements may change as users test the prototypes provided to them

### Question D

Codeline refers to the sequence of versions of the software, with each representing minor updates to the software while baseline refers to a major version of the software, often more stable and may break on the user's computer.

## Question 5

### Question A

System testing refers to testing the system as a whole, while component testing refers to testing whether the different components in the system is able to interact with one another without error. In system testing, a separate team would be the one testing the system while in component testing, the same development team will be the one testing the system. This is because system testing is done once the system is completed and is waiting for deployment while component testing is done while the system is still being developed.

### Question B

1. *Source code translation*
	1. Using a tool to translate COBOL language to a more modern and widely documented language such as C or C#.
2. *Reverse engineering*
	- Analyse the source code to gather information regarding the system. This is necessary as the stock management system may not have the complete documentation which can be used. 
3. *Program modularisation*
	- Grouping parts of the systems that are related to one another together to reduce redundancy. 
	- This can inadvertently improve performance.
4. *Program structure improvement*
	- Changing the control structure of the system to make it more optmised and readable to fix the performance issue. 
5. *Data re-engineering*
	- Redefine database schema as well as how the data is processed by the system. May require changing the database used as well. Since the data may be duplicated and noisy, it has to be cleaned as well to fit today's modern standard.

### Question C

1. Consistency text boxes behaviour
	- Both text boxes should allow users to input and edit their inputs
2. Clear feedback in text boxes
	- The text boxes should indicate the users whether the inputs are valid or invalid
3. Error notification and correction in text boxes
	- If the input are invalid, it should show the suggest correction to the user. 

### Question D

Risk management is about managing risks that may occur in the lifetime of the development of the system. Risks refer to anything that can hinder the progress of development of the system. For example, Technology risks, tools risks, and people risks. 

# Next Paper

[[Past Year Papers/Year 2/Semester 3/Software Engineering Principles/May 2023|May 2023]]