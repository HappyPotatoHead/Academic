# Question 1 - Requirement Analysis and Design Principles

## How would design principles such as modularity, scalability, maintainability, and security guide your architectural solution?

https://daily.dev/blog/what-is-modular-programming
https://medium.com/@ozlembasabakar/exploring-design-principles-with-solid-modularization-benefits-with-kotlin-examples-43a0054b67be

### What is Modularity

_What is modularity?_

> [!DEFINITION] Modular programming
> It is a technique that simplifies complex software development by breaking it down into smaller, manageable pieces called modules. Each module performs a specific task and can be used independently or combined with other modules to build larger systems.

The modules focus on doing a specific job and hide how they do it from the rest of the program. This is known as abstraction. This also means that a module can be used without knowing the details of how it works.

- [I] Modularity approach is related to the SOLID principles
  - SRP
  - OCP
  - LSP
  - ISP
  - DIP

### Core Principles of Modular Programming

1. High cohesion
   - Everything inside a module is closely related and works towards the same goal/function.
2. Loose coupling
   - Modules connect with each other only through their outer layers, so they don't need to know much about each other to work.
   - This essentially means creating a _general_ function that can work in multiple use-cases
3. Abstraction
   - Modules hide their inner workings, showing only what's needed for them to be used.
4. Self-containment
   - Modules aren't that reliant on outside parts.

### Why

This approach allows for:

1. Easier code maintenance
2. Update simplicity
3. Reusability of code across

# Question 2 - Pattern Selection and Justification

# Question 3 - Component and Architecture Design

# Question 4 - Reflection on Design Choices

**What are the design-patterns**

1. Creational design pattern
   - Focus on object creation mechanisms
   - Types:
     1. Singleton
     2. Factory Method
     3. Abstract Factory
2. Behavioural design pattern
   - Focus on communication between objects; how they interact, delegate responsibilities, and manage workflows efficiently
   - Types:
     1. Observer
     2. Mediator
3. Structural Design Pattern
   - Focus on composing objects and classes to form larger structures while keeping them flexible and efficient
   - Types:
     1. Adapter
     2. Composite

![[User Management Module-User Management Module V1.drawio.png]]
According to my model, there are multiple design patterns that can be used. The design patterns are:

1. Modular pattern
   - The architectural design involves multiple, smaller, and single-responsibility components that are combined to create the large user account management module.
   - By separating these components, implementing the module
2. Abstract pattern
   - Although there are multiple different payment methods, each of them still shares similar characteristics.
     - For example the payment method component branches into 3 smaller components. These three represent different families of related objects needed to manage each payment type.
   - With abstract factory, I can not only ensure consistency, but also make it easier for me to add new payment methods in the future.
3. State pattern
4. Data Access Object pattern

I learnt that most software are written based on multiple design patterns. There is not just one design-pattern being used at a time; multiple are used so that the weakness of one design pattern is complemented by the strengths of another. Additionally, using design patterns lead to a more structured and organised codebase, making it easier for developers to understand and maintain the system. One such example is the user account management system where it's broken down into several smaller components. Using patterns also introduce loose coupling, where components can be used in different places for different purposes.

# Question 3

In the account subsystem, the user will first login or register an account. In login interface, the user has to provide the correct username and password. If the details is incorrect, the user will not be able to log in. The **Register Interface** component will let the user create an account and insert the user into the user database.

Once the user has logged into the system, the user can start ordering their food. Before the user can start viewing restaurants, the system will first get the user's location, either from GPS or from the default location that the user has set. After that, based on the user's current location, the system will list the restaurants from the database in an intuitive interface for the user to easily follow. This is done with the **Restaurant Listing** component.

When the user selects a restaurant, the menu from that restaurant will be fetched and shown to the user via the **Menu Listing Interface** component. The user can then start ordering the item that they want. The **Cart system** component will keep track of what the user is ordering.

Once the user is finished ordering their food, the total amount to be paid will be calculated by the **Calculation and Tax Inclusion System**. The component will first receive the original sum of the prices of all the items from the **Cart System**. Once the new total is calculated, the new total and the list of items will be passed into **Order Checkout System** component to show to the customer.

When the customer confirms their order, **Payment System** subsystem will becalled. In this subsystem, the **Payment Encryption and Selection System** will be called to ensure that the user's payment information is encrypted and prevented from exposure from outsiders.

After that, the payment will be proceeded with the **Payment Gateway** component to verify payment credentials. After that, the **Payment Fulfilment System** will be called to ensure that the payment goes through and confirm the order.Once the order has been confirmed, the order will be sent to the chosen restaurant to be prepared.

The system now moves to the **Order and Delivery Fulfilment System** in which tracks the status of the order. The **Order Decision System** component requires the restaurant staff to confirm, reject, or call the customer to modify the order. If the order is confirmed, **Delivery Request Listing** component will requests surrounding available delivery staff to pick up the delivery request. If there is a willing delivery staff, **Delivery Staff Status Update System** component will push an update - information of the delivery staff - to the **Customer Order Delivery Status Update**. At the same time, the location of the delivery staff will be tracked with **Delivery Staff Tracking System**. The **Customer Order Delivery Status Update** component's role is to manage the updates before showing the user.
The **User Order Status and Delivery Interface** component will control how the customer gets the status of the order itself.

Finally, when the user's order has been delivered, **Delivery and Order Feedback System** component is called to request user to provide feedback on their order.

