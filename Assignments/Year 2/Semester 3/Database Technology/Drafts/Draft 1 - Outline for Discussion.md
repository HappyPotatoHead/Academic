Since we're a fast food restaurant, we can take inspiration from the largest fast-food chain in the world, McDonald's.

Since we're focusing on Point of Sales (I'll call it POS from this onwards), we should focus on where it makes _The Foodie_ money.

# Functionalities

## Counter Sales

This is the core function of any restaurant. In any fast food restaurant, despite the existence of kiosk system, the counter must still exist.

_However, let's pretend the kiosk system does not exist for a moment._

The interaction between a `customer` and the `cashier` will be as such:

1. `Customer` walks up to the counter
2. `Customer` says what they want
3. `Cashier` records the `order`
4. `Cashier` shows the `total price`
5. `Customer` makes the `transaction `
   - Cash
   - Credit
   - E-Wallet
   - ~~Robbery~~
6. The `order` is sent to the `kitchen`

**Entities needed:** Order, OrderItem, MenuItem, Payment, Customer, Cashier

## Kiosk sales

The use of kiosk machines is also becoming ubiquitous.

The interaction between a customer and a kiosk machine:

1. `Customer` walks up to the kiosk machine
2. `Customer` is given the option to log into the restaurant's official app
3. `Customer` chooses the food that they want
4. `Customer` confirms their `order`
5. `Customer` chooses the mode of `transaction`
   - Cash
   - Credit
   - E-Wallet
6. `Customer` makes the `transaction`
7. The `order` is sent to the `kitchen`

**Entities needed:** Order, OrderItem, MenuItem, Payment, Customer, Kiosk

## Delivery Orders

Since people don't leave their homes anymore, delivery is a must for us to survive.

A typical person in their mother's basement would do this:

1. `Customer` opens:
   - The official app
   - A food delivery app
     - FoodPanda
     - GrabFood
     - etc
2. If the `Customer` opens the official app:
   - _The same thing, I don't want to write it again_
   - [?] The `Customer` can enter a voucher to get discount
3. If the `Customer` opens a food delivery app:
   - _The same thing, I don't want to write it again_
   - The `Customer` can enter a voucher to get discount

**Entities needed:** Order, OrderItem, MenuItem, Payment, Customer, DeliveryDriver, Platform, Discount

## Pick up orders

The pick up orders can happen in two venues:

1. The `Customer` `orders` in the restaurant for takeaway
2. The `Customer` `orders` at home and picks it up at the restaurant

_The process of ordering is a combination of delivery orders, counter sales, and kiosk sales; I don't want to write it again_

**Entities needed:** Order, OrderItem, MenuItem, Payment, Customer, OrderingPlatform

## Items & Pricing

This function covers the items sold under _The Foodie brand_. We need this function to control what is sold each day and the price of these items.

The items themselves can be the food, drinks, sides, or merchandise. The prices of the items may change due to demand, inflation, or supply chain issues.

**Entities needed:** MenuItem, PriceHistory

## Process Payments

In [[Draft 1 - Outline for Discussion#Counter Sales|counter sales]],[[Draft 1 - Outline for Discussion#Kiosk sales|kiosk sales]], [[Draft 1 - Outline for Discussion#Delivery Orders|delivery orders]], and [[Draft 1 - Outline for Discussion#Pick up orders|pick up orders]], `transaction` takes place. We need this function to know which mode or method used to make the `transaction`, the discount applied (if any), and the time the transaction is made.

**Entities needed:** Payment, Order, Discount

## Generate sales receipts

This is for customer records and accounting.

_It's like those receipts you get when you purchase anything from any shop_

**Entities needed:** Receipt, Order, Payment

## Discounts

This function is needed to keep track of the discount we've been giving our customer.

The discount can originate from:

1. Our official shop
2. Food delivery apps

**Entities needed:** Discount, OrderDiscount (junction table)

## Tracking order

This is to monitor the status of the order in real time.

_It's that board that you see that fast-food restaurants that show which order is being prepared_

**Entities needed:** OrderStatus, Order

## Staff Role Management

This is important to ensure the `staff` only does what is within their rights.

**Entities needed:** Staff, Role

# Entities

1. Customer
   - General term describing individual who purchases an item at _The Foodie_
2. Staff
   - General term describing people who are employed at _The Foodie_
3. Delivery Personnel
   - People who does door-to-door deliveries
4. Platform
   - Indicates where the order is made
5. Kiosk
   - **Attribute**
     1. KioskID
     2. Location
6. Product
   - General term describing all the items sold under _The Foodie_ franchise
   - [?] We can divide them into:
     1. Food
     2. Sides
     3. Drinks
     4. Merchandise
        - Plushies
        - Toys
        - Accessories
   - **Attributes**
     1. ItemID
     2. ItemName
     3. Price
     4. etc
7. PriceHistory
   - Record price changes
8. Order
   - Represents a record of a customer's request for goods or services
   - **Attributes**
     1. OrderID
     2. OrderDate
     3. OrderTime
     4. OrderSource
     5. etc
9. OrderItem (Junction Table)
   - **Attributes**
     1. OrderID
     2. ItemID
     3. Quantity
10. Discount
    - Represents a reduction in the price of a product or order
11. Transaction
    - Records the financial exchanges associated with orders, payments, or other financial activities within the system

# Discussion

We can combine [[Draft 1 - Outline for Discussion#Counter Sales|counter sales]],[[Draft 1 - Outline for Discussion#Kiosk sales|kiosk sales]], [[Draft 1 - Outline for Discussion#Delivery Orders|delivery orders]], and [[Draft 1 - Outline for Discussion#Pick up orders|pick up orders]] into **order management**, but we would have to come up with other functions.

**Suggestions**

1. Inventory Management
2. **Customer Management**
3. **Sales Reporting and Analytics**

