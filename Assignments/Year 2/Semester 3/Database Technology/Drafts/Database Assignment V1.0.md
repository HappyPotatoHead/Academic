> [!INFO] HOW ERD AND EER DICTATE OUR WORKFLOW
>
> 1.  The tables, scripts, and records are created based on the ERD
>     - Essentially, the number of tables in script is the number of entities in erd
> 2.  To apply the created EER - specialisation & generalisation - constraint is added.

# Current Development

1. Developed an ERD
2. Developed an EER
3. Wrote the data dictionary
4. Wrote dummy values

## ERD

![[ERD.png]]

### Description

#### Entities

**Strong Entities**

1. Staffs
2. Roles
3. Payments
4. Members
5. Promotions
6. Vouchers
7. Branches
8. Item Categories

**Weak Entities**

1. Customers
2. Items

**Junction Tables**

1. Staff Roles
2. Items in Branches

The entities here are general entities. The entities that can be expanded are:

1. Orders
   1. Delivery
   2. Non delivery
2. Items
   1. _Expand to each type of food_

**To determine the entity that can be/should be expanded, see if null values exist and can be eliminated**

## EER

![[EER.png]]

### Description

The current specialisation created:

1. Items
   1. Division into each type of item

The specialisation that can be created is orders into:

1. Delivery
2. Non-delivery

## Functionalities

### Menu-Board

This function allows users to see what's on the menu.

It involves:

- Items
- Item Categories
- Item in Branches

#### Functions

**User Perspective**

1. Retrieving all the items from `Item in Branches`

**Staff Perspective**

1. Retrieving all the items from `Item in Branches`
2. Can modify the prices of the items from `Item in Branches`
3. Can modify the items sold at dedicated branches in `Item in Branches` from `Items`. (_This means we have to connect staff to Branch_)

### Order Processing

This function allows users to order the food that they want and apply promotions (if any) or vouchers (if any)

It involves:

- Items
- Promotions
- Vouchers
- Item in Branches
- Members
- Customers

#### Functions

**User Perspective**

1. User puts in the food that they want to order
2. _Promotions are applied automatically along with the order_
3. Any existing vouchers that the user has can be applied too.

### Payment Processing

This function allows users to pay with the mode of their choice. This same function also prints out the receipt for the user to see.

It involves:

1. Payments
2. Order
3. Order Details

#### Functions

\*\*User Perspective

1. The user pay an amount in the mode that they chose
2. The user receive a receipt from the cashier/machine

**Staff Perspective**

1. The staff calculates the balance between the final amount and the total amount paid by the customer
2. The staff then prints out the receipt with the order details

### Delivery Processing

**The user has to be a member before ordering food online for delivery. (Constraint)**

This allows user to order food from their homes.

It involves:

1. Members
2. Items in Branches
3. Order

### Membership Points

**This is only limited to users who are members (Constraint)**

This function allows users to collect points from their orders.

It involves:

1. Customers
2. Members
3. Orders

**User Perspective**

1. The user has to log in as a member before making an order to collect points
2. The user makes the order

### Order Progress

**Depending on the mode of order, the value can be extended to _picked up_, _on the way_, _delivered_**

This functions is to keep track of the order that has been made.

It involves

1. Orders
2. Order Details

### Items Price modification

**This is primarily for staffs**

This function will allow the staff (manager or people in charge) to change the price on the menu

It involves:

1. Branches
2. Items in Branch
3. Items

### Sales Management

**This is primarily for staffs**

This function is analytical

It involves:

1. _Pretty much every entity in the system_
   - It depends on what kind of information you want
