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
*You want the project to be completed quickly*

Agile development approach is the best one.

1. Customer involvement is extensive.
	- Marcus is able to develop prototypes for the users to test and get feedback as soon as possible. 
	- This is able to reduce the cost and time from changing requirements. 
	- Marcus is also able to produce a product that is closer to the user's expectations and requirements due to the continuous feedback that the users give. 
2. Has less emphasis on following step by step procedures but rather focuses more on trying to execute multiple tasks as much as possible. 
	- This allows the development of the application to be much quicker compared to a plan-driven approach such as waterfall methodology, where the developers can only proceed to the next phase once they are done with the current phase.
	-  This approach also allows Marcus to show a more obvious result to the user, inadvertently strengthens the relationship with the customers

#### Question II

1. Lack of documentation
	- Since agile methodology focuses on quick and flexible development, there is not much emphasis on creating a formal documentation.
	- This can be problematic when attempting to maintain the system or when handing over the system to a new development team
2. Customer involvement
	- The benefit of agile methodology is also it's disadvantage. 
	- Since agile methodology hinges on users' constant feedback and testing, the users have to always be present and available. If not, the developer is not able to get the most out of agile development. 

### Question B

#### Question I

10 months = 40 weeks 
Total weeks = 43 weeks

#### Question I

$$\frac{43}{8} = 5.375 \text{ weeks per cycle}$$

#### Question II

No. Each sprint usually lasts 2 to 4 weeks. 5.375 weeks exceed that period by 1 week.

#### Question III

Yes, all sprint cycles will strictly follow the 3-week duration. By setting a fixed sprint cycle duration, the product owner and the scrum master is able to easily devise a plan. This allows the scrum and sprint to be predictable and easily managed, which is important in this agile framework as quickly delivering deliverables is the main goal. 

#### Question IV

1. Report the progress that has been made
2. Work together and solve problems that has been brought up by any of the team members

## Question 2

### Question A

*Architectural patterns*
1. ~~*MVC*~~
2. ~~*Layered*~~
3. *Microservice*
4. ~~*Client-Server*~~
5. ~~*Repository*~~

Micro-service architecture is the most appropriate one. 

1. Modularity and reusability
	- Each microservice can be replaced or reused in another system.
	- This is because there is a clear separation of concern between each of the micro-services
2. Durability
	- When one microservice is down, other microservices are not affected. The entire system does not shut down either. 
3. Technologically agnostic
	- Each micro-service can be written using a different language or tools while being able to communicate with each other via a gateway.

### Question B

1. As a passenger, I want to search for routes, so that I can find the route that I want without scrolling through other countless routes
2. As a passenger, I want to book and purchase tickets in the application itself, so that I don't have to wait in line for hours to pay for my ticket
3. As a passenger, I want to select my seat, so that I get seats that is able to accommodate me and other people with me if I am travelling in a group.
4. As a passenger, I want to track where the bus is, so that I can plan my travel properly and not be late
5. As a passenger, I want to be able to choose the payment method so that I can pay with the method I am familiar with the most. 

### Question C

#### Question I

1. Interface incompatibilities between Processes online payments and validates transactions.
2. Interface incompatibilities between Provides real-time buss location and manages schedule changes.

I would resolve them using an object adapter. This technique is when an adapter class have an instance of the adaptee. The adapter class will translate the target's interface into the adaptee's interface, allowing the usage of the unit without making changes to the unit themselves.

#### Question II

1. Using message broker
	- This allows asynchronous communication between the components
2. Save the data in local cache
	- Store additional data in cache
	- This allows the application to keep working until network connection becomes stable

## Question 3

### Question A

#### Question I

1. Interface incompatibilities between stores and manages patient medical histories and maintains prescription records
	- The interface incompatibilities can happen when data is passed from updating prescription records to updating the patient's medical history
		- Due to different format used
2. Interface incompatibilities between generates patient invoices and manages payment records
	- This may happen updating patient record from the patients' invoices. 

I would resolve them using an object adapter. This technique is when an adapter class have an instance of the adaptee. The adapter class will translate the target's interface into the adaptee's interface, allowing the usage of the unit without making changes to the unit themselves.

#### Question II

1. Does it fulfill the system's requirements
	- The component should be able to process insurance claims, generate patient invoices, manages payment records.
	- The functions that the component should also work under normal circumstances and should not break
2. Does the component comply with the hospital's standards and policy
	- The component should not violate any code or policy 
	- The component should be safe to use for both the users and the staffs
3. Component's quality check
	- Has the component been validated and tested before? 
		- It should not contain malware or anything that can harm the patient's finances 
	- The component should not break under normal usage
	- The component should be optimised and only does what it's supposed to do. 

### Question B

#### Question I

#### Question II

1. Single purpose
	- The component should only do single purpose that is general enough that it can be used in other system.
	- This prevents the component from being too tightly coupled with other components in the current system.
	- By keeping the component single purpose it can easily be modified and reused in other systems without hassle
2. Clear documentation
	- The should be a clear and detailed documentation for the component.
	- This allows other developers to understand what the component does, what it uses, and how it functions
	- This prevents them from modifying it without understanding the component. 

# Section B

## Question 4

### Question A

#### Question I

1. Development testing
	- This form of testing revolves around testing the system for defects and bugs
	- For example, the testing team components and units written such as recording temperature, humidity, and wind speed in a predictable and controlled environment to ensure that the recorded values are accurate and the units or components are working seamlessly
2. Release testing
	- This level of testing is testing the system to ensure that the entire system works under normal usage before letting real users use them
	- For example, testing the system using artificial data thoroughly to ensure that each feature is working and does not interfere one another.  
3. User testing
	- The user tests the system in their own environment using their own data.
	- For example, the company can provide beta tests to a select few stations for them to use the system for a period of time for their feedback and observations

#### Question II

Parameter incompatibility
- Happens when operations have the same name, but different parameters
- This can be testing by passing data between components and validating the output provided by each component. 
Operation incompatibility
- Happens when the operations are the same, but with different names.
Operation incompleteness
- When one component does not provide all of the crucial services that is needed for another component to work
- This can be tested by testing the communication between two components and observe if there are any missing services in the latter component. If there is, it would indicate that the former component may not be providing the services or data needed. 

### Question B

#### Question I

Valid test cases:

Valid number of stations: \[4,5,6,7,8,9,10]
Valid temperature values: \[-50, 45, 30, -20]
Valid values: \[-50, 45, 30, -20]

Invalid test cases

Valid number of stations: \[1, 2, 3, 11, 15]
Valid temperature values: \[-70, -80, -100, 100]
Valid values: \[-50.1, 45.7, 30.5, -20.0]

#### Question II

1. The team responsible in testing
	- Release testing has another separate team testing the system while system testing has the development team testing the system. 
	- This is to prevent biases when testing the system and also allowing a third party who has little knowledge of the system to use it, mimicking real world usage. 
2. Area of focus
	- Release testing focuses on the system as a whole, which involves all of the units and components
	- Component testing focuses on testing the component interfaces; it tests whether the units are able to communicate with one another

## Question 5

### Question A

#### Question I

1. Unit testing
	- This level tests each individual unit to determine if the unit is able to work error and bug-free
	- For example, testing if the login unit is able to function without error.
2. Integration testing
	- This level tests if the different units are able to communicate and interact with one another seamlessly. In this level, components are created from composing objects 
	- For example, submitting student login details should work well with validating student login details.
3. Component testing
	- This involves testing interactions between components 
	- For example, testing if registering student component can interact with updating student count in course component without error.

#### Question II

Valid test cases:

Valid number of concurrent student registrations: \[5,100,150,200]
Valid number of courses a student can register: \[1,2,3,4,5,6]

Invalid test cases

Invalid number of concurrent students registrations: \[300, 400, 500]
Invalid number of courses a student can register: \[7, 8, 9, 10]

### Question B

#### Question I

1. System hardware
	- The legacy system may have been written for a hardware that is no longer in use
2. Software support
	- It may have depended on software that is no longer mantained
3. Application system
	- The application system may be made out of multiple application modules. Updating the modules may be costly and time-consuming due to the use of different languages and possibly outdated tools.
4. Application data
	- Refers to the data managed by the application system. It can be outdated, duplicated, or stored in a different database. Updating it would also be difficult as it may require the data models to be changed or changing the data storage mechanism
5. Business processes
	- Refers to the processes that business do to fulfill certain business objective. 
	- The issue is when the business process revolves around the legacy system, so the processes are limited to the functionality that the legacy system provides. 
6. Business policies and rules
	- Describes how processes are to be carried out.
	- Issue arises when the rules and policies are tightly integrated

#### Question II

The legacy system has high business value and low quality. The best thing to do is to re-engineer the system. This is because a Student Information System is a crucial system in a university setting, so the value that it provides is high. Additionally, since it has been operating for 10 years, the source code of the system has likely to follow outdated practices or use older tools and technology. This would make the quality of the software low. 

### Question C

#### Question I

1. Failure to find the right people with the right set of skills
	1. High probability
	2. Catastrophic effect
2. Project has budget cuts
	1. Low
	2. Catastrophic
3. The technology used to develop is no longer maintained
	1. Moderate
	2. Serious
4. The technology used has low familiarity
	1. low
	2. Tolerable 

#### Question II

The technology used has low familiarity. Select technologies that the developers are familiar with. 

# Next Paper
[[Past Year Papers/Year 2/Semester 3/Software Engineering Principles/September 2024|September 2024]]