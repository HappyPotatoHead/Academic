# Managing Customer's Order Across Channels

This is the combined function of **counter sales**, **kiosk sales**, **delivery orders**, **pick-up orders**.

The reason of the combination is as follows:

1. **More Concise and High-level**
   - Since across the different channels, the order ultimately looks the same. This lets us focus on the overarching function of "taking orders" regardless of the channel.
2. **Avoids Redundancy**
   - The core actions within counter, delivery, and pickup are similar.

## Description

Encompasses the system's ability to efficiently take and manage customer orders across all sales channels:

- **Counter Orders:** For in-person ordering at the cashier counter.
- **Kiosk Orders:** For self-service ordering via kiosk machines.
- **Delivery Orders:** For online orders placed for delivery to customer addresses.
- **Pickup Orders:** For orders placed online or in-restaurant for customer pickup

## Entities

## Manage Menu Items and Pricing

### Description

This function covers the items sold under _The Foodie brand_. We need this function to control what is sold each day and the price of these items.

The items themselves can be the food, drinks, sides, or merchandise. The prices of the items may change due to demand, inflation, or supply chain issues.

Since items can be divided into **Food**, **Drinks**, **Dessert**, **Sides**, and #maybe **Merchandise**, we can create subclasses for this.

## Entities

# Payments Processing

## Description

This is needed to keep track of the `transaction` that takes place. During any transaction, the customer is given 3 options:

1. Cash
2. E-wallet
3. Card

This functionality should also keep track of the discount that is applied.

## Entities

# Generate Sales Receipts

## Description

This is for customer records and accounting. The sales receipts will be generated for every mode of ordering and every mode of transaction.

## Entities

# Manage Discounts and Promotions

## Description

This function is to keep track of the discounts or offers that we give to our customer.

## Entities

# Track Order Status in Real Time

## Description

This is to monitor the status of the order in real time regardless of whether the order is created via counter sales, delivery sales, or pick up sales.

## Entities

# Staff Role Management

## Description

Ensures that every employee in the restaurant only does what is within their rights or clearly define what they are supposed to do.

## Entities

# Inventory Level Monitory Linked to Sales

## Description

This function is needed to ensure that the change in stock tallies with the ingredients used in each other. This is important to ensure that the restaurant has sufficient stocks of ingredients.

## Entities

# App Membership Records

## Description

## Entities

# User Loyalty Rewards

## Description

## Entities

