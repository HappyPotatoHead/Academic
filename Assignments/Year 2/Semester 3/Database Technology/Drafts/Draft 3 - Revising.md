> [!DONE] Changes Made
> [[Draft 3 - Revising#Tasks and Entities]]

# Notes

**Main functions** and **functionalities** are a vague, and if mixed, makes it confusing.

So,

1. **Main functionalities** = Processes
2. **functionalities** = Task

Task will be indicated with \[\*]

# Reiteration

> [!DEFINITION] Point of Sale
> The place where a customer executes the payment for goods and services and where sales taxes may become payable.

Based on the definition, the focus on the **main function** should be placed on places where customer makes transactions, especially since we're a fast-food restaurant.

# Processes

_For simplicity sake, we imagine the restaurant as the first of its franchise and it has its own independent delivery/pick-up services._

In a **modern** fast-food restaurant, the places where customers make transaction are:

1. Counter
2. Kiosk
3. Delivery/Pick-up (Online Ordering)
4. Drive Thru

## Counter

This is where `customer` makes an order in the presence of a cashier (`staff`).

This is what usually happens:

1. At a counter, the `customer` will be shown a **menu-board** (static or dynamic) \[\*].
2. At the counter, if any, the `customer` can choose to customise their `order`. \[\*] (Like how McDonald lets user choose what's for the drinks, dessert, etc).
3. The `customer` then redeem their choice of `voucher/discount` (if any) \[\*].
4. The customer chooses how they want to pay (method of payment) \[\*]
   - Cash
   - Card
   - E-wallet
5. Receipt will be generated

## Kiosk

This is where `customer` makes an order and pay for orders themselves.

The difference between this and [[Draft 3 - Revising#Counter|counter]] is the presence of membership.

This is what usually happens:

1. The `customer` is given a choice to _login_ or proceed as is
2. The `customer` will be shown a **menu-board** \[\*].
   - The menu navigation and display has to be intuitive and user-friendly
3. The `customer` can choose to redeem food based on the `membership points` that they have
4. The `customer` can choose to customise their `order`. \[\*] (Like how McDonald lets user choose what's for the drinks, dessert, etc).
5. The `customer` then redeem their choice of `voucher/discount` (if any) \[\*].
6. The customer chooses how they want to pay (method of payment) \[\*]
   - Cash
   - Card
   - E-wallet
7. Receipt will be generated

## Online/Mobile Ordering

This is where `customer` makes an order and pay for orders themselves **online**.

This is what usually happens:

1. The `customer` is given a choice to _login_ into the official application
2. The `customer` will be shown a **menu-board** \[\*]. _simplicity sake_
   - The menu navigation and display has to be intuitive and user-friendly
3. The `customer` can choose to redeem food based on the `membership points` that they have
4. The `customer` can choose to customise their `order`. \[\*] (Like how McDonald lets user choose what's for the drinks, dessert, etc).
5. The `customer` then redeem their choice of `voucher/discount` (if any) \[\*].
6. The customer chooses how they want to pay (method of online payment) \[\*]
7. There is also a delivery fee calculation (if delivery is opted)

## Drive Thru (#maybe)

# Tasks and Entities

## Entities

Based on the processes and some freedom, we can identify some entities:

1. `Items`
   - This is for the products details themselves
   - **Attribute**
     1. ItemID
     2. ItemType
     3. ItemName
     4. ItemDesc
     5. ItemCalories
2. `ItemCategories`
   - This is for the different categories in `Items`
   - **Attribute**
     1. ItemType
     2. TypeDesc
3. `RestItems`
   - This is for how the items are sold in the restaurant
   - **Attribute**
     1. RestID
     2. ItemID
     3. ItemPrice
     4. _ItemAvailability_
     5. _ItemQuantity_
   - **Side Note**
     - If we do Inventory Management, ItemAvailability and ItemQuantity has to be changed
4. `Customers`
   - **Attributes**
     1. CustomerID
     2. CustomerType
5. `MemberDetails`
   - **Attributes**
     1. CustomerID
     2. MembershipID
     3. FName
     4. LName
     5. Email
     6. Address
     7. DOB
     8. Point
6. `Memberships`
   - **Attributes**
     1. MembershipID
     2. MembershipTier
7. `Orders`
   - The orders that the customers made
   - **Attributes**
     1. OrderID
     2. OrderDate
     3. OrderTime
     4. OrderStatus
     5. OrderTable
     6. OrderType
        - This is to keep track of Delivery, Pick-up or Dine-In
     7. CustID
        - This is an arbitrary value used to keep track of the number of customers that enters the restaurant
     8. #maybe Discount
8. `OrderDetails`
9. `Transactions`
   - Details of the transaction made
   - **Attributes**
     - TransactID
     - OrderID
     - Paid
     - Balance
     - PaymentMode
10. `Discounts` #maybe

## Tasks

Based on the 4 processes, we can garner some tasks

1. Menu-board
   - **Description**
     - The user can see what are the food available in the restaurant
   - **What does it involve**
     - `Items`
     - `ItemsCategory`
     - `RestItems`
2. Orders/Orders customisation
   - **Description**
     - The user can choose what to include or exclude in their order
   - **What does it involve**
     - `Customers`
     - `MemberDetails`
     - `Membership`
     - `Orders`
     - `OrderDetails`
3. Payment Processing
   - **Description**
     - The user can choose to pay with the mode of their choice
   - **What does it involve**
     - `Transaction`
4. Discount processing
   - **Description**
     - For discounts or vouchers
   - **What does it involve**
     - `Discount`
     - `Orders`
5. Receipt processing
   - **Description**
     - Generate a receipt for an order
   - **What does it involve**
     - `Transaction`
6. Delivery/Pickup Processing
   - **Description**
     - Let's the user make an order online
   - **What does it involve**
     - `Customers`
     - `MemberDetails`
     - `Membership`
     - `Orders`
     - `OrderDetails`
7. Redeeming membership points
   - **Description**
     - Gives customer the choice to redeem their points on kiosk, delivery, or pickup
   - **What does it involve**
     - `Customers`
     - `MemberDetails`
     - `Membership`
     - `Orders`
     - `OrderDetails`
8. Tracking order progress
   - **Description**
     - Track whether the order is ready for table-service, pick-up, on-delivery, in progress, or cancelled
   - **What does it involve**
     - `Orders`
     - `OrderDetails`
9. Inventory Management
   - This is only the basic integration

