# Introduction

> With its latest business venture into fast-food restaurant, The Foodie, which specialize in burgers and fried chickens. A new computerized system needs to be in place for the restaurant overall operations including inventory management, point of sales, event management, scheduling, etc.

[[UCCD2303-database-technology.pdf#page=1&selection=53,0,89,4|UCCD2303-database-technology, page 1]]

The area of operations:

1. Inventory Management
2. Point of Sales
3. Event management
4. Scheduling
5. etc

We only have to pick one from these. **We can also pick one of our own**. From these chosen area, we have to come up with 10 main functionalities. _To put it in other words, we're specialists._

> [!ATTENTION]
>
> 1.  The database system must be designed to last
>     - It has to keep track of every record
> 2.  Identify the abstraction of classification, aggregation, identification, specialisation, or generalisation.
> 3.  Specify the cardinality constraints
> 4.  List details or any assumptions that will affect the conceptual design.

# Area of Operation

_If you were a fast-food restaurant owner, what would you do?_

> [!NOTE] The order
> The order may not dictate the complexity of the area. The complexity of each area depends on how many functions we're going to implement.

## Inventory Management

> [!DEFINITION] Inventory Management
> The process of ordering, storing, using, and selling a company's inventory. This includes raw materials, components, and finished products, as well as the warehousing and processing of these items.[^1]
>
> _Basically managing supplies_

The entities that can be involved:

1. **Products**
2. **Suppliers**
3. **Inventory**
4. **Purchase**
5. **Orders**
6. **Shipments**
7. **Warehouse**
8. **Employees**

The functionalities:

1. **Track ingredient stock levels**
2. **Manage supplier information**
3. **Low-stock alerts for ingredients**
4. **Expiring stock alerts for ingredients**
5. **Record inventory receiving from suppliers**
6. **Manage ingredient categories**
7. **Calculate ingredient usage based on menu items sold**
8. **Manage waste tracking**
9. **Record and manage inventory adjustments**
10. **Generate reports on inventory levels and usage**

## Point of Sales

> [!DEFINITION] POS
> A point of sale (POS) system includes the hardware and software to process payments and complete purchases.[^2]
>
> _Basically, it's how the restaurant makes money_

The entities that can be involved:

1. **Customer**
2. **Staff**
   - Can be divided further
3. **Delivery personnel**
4. **Product**
5. **Orders**
6. **Discount**
7. **Transaction**

The functionalities:

1. **Counter sales**
2. **Kiosk sales**
3. **Delivery orders**
4. **Pick up orders**
5. **Menu Items & Pricing**
6. **Process payments**
7. **Generate sales receipts**
8. **Discounts**
9. **User role management**
10. **Tracking order**

## Event Management

The entities that can be involved:

1. **Event Types**:
   - Birthday Party
   - Team Building
   - School Visit
   - Workshop
2. **Event Packages**:
   - Basic Birthday Package
   - Deluxe Team Building Package
   - _Like McD_
3. **Events**
4. **Customers**
   - Event Organizers
5. **Staff**
   - Employees assigned to manage or support the event.
6. **Resources**:
   - Specific room/area
   - Decorations
   - Equipment
   - Special menu items
7. **Bookings**
8. **Schedules**
   - Timelines and agendas for events.
9. **Event Menus**
   - Special menu items or packages offered for events.
10. **Payments**
    - Transactions related to event bookings and charge

The functionalities:

1. **Manage Event Types**
2. **Create and Manage Event Packages**: Design pre-set packages for different event types, including menu items, duration, activities, and pricing.
3. **Handle Event Bookings**
   - Allow customers to:
     1. Inquire and book events
     2. Capture event details like:
        - Date
        - Time
        - Number of attendees
        - Event type
        - Customer information
4. **Schedule Events**
   - Event calendar and schedule events
   - Preventing overlaps and conflicts
   - Assigning time slots.
5. **Allocate Resources for Events**
   - Staff
   - Specific areas/rooms
   - Decorations
   - Special equipment.
6. **Customize Event Menus**
7. **Manage Event Details**
   - Special requests
   - Themes
   - Specific needs.
8. **Process Event Payments**
   - Deposits
   - Final payments.
9. **Generate Event Schedules and Agendas**
   - Create detailed schedules or agendas for events to guide staff and inform event organizers.
   - _Like generating a report_
10. **Report on Event Bookings and Revenue**
    - Auditing
    - Analysis

## Employee Scheduling & Management

> [!DEFINITION] Employee Scheduling & Management
> The act of organizing, optimizing, and managing employee schedules so that projects and company goals are met on time.

The entities that can be involved:

1. Employees
2. Roles
3. Shifts
4. Schedules
5. Availability
6. Time Off Requests
7. Departments
8. Labor Cost Rates
9. Absence Records

The functionalities:

1. Manage employee Information
2. Define employee roles
3. Create and manage shifts
4. Employee availability
5. Employee schedules
6. Manage time off requests
7. Track employee working hours

[^1]: https://www.investopedia.com/terms/i/inventory-management.asp

[^2]: https://www.investopedia.com/terms/p/point-of-sale.asp
