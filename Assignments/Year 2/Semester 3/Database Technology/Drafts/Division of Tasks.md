# Task

Total:
Queries: 12
Stored Procedures: 8
Functions: 8

1. Queries
   - Retrieve all items available on the menu, including item name, description, category, and price based on branches.
   - Display receipt with transaction details
   - Display real-time order status to determine if it's being prepared, completed, or delivered.
2. Stored Procedures
   - Add or remove items in a specific branch
   - Identify members eligibility for rewards
3. Functions
   - Determine if an item is available in specific branches
   - Calculate the loyal points gained from the order

4. Queries - Filter item based on category type. - Identify all orders that require delivery based on order type. - Identify out-of-stock items.
   2. Stored Procedures - Record order details after customer places order - Update order status
5. Functions
   - Calculate applicable promotion discount
   - Determine if the provided payment information is valid.

6. Queries
   - Search item based on item name and description.
   - Retrieve details of a member’s loyalty points and membership tier.
   - Retrieve total sales for specific periods.
7. Stored Procedures
   - Record customer payment details
   - Update prices of items
8. Functions
   - Calculate applied voucher
   - Determine if the customer is a valid user in the system.

9. Queries
   - Retrieve customers’ order history.
   - Display the history in which points are used
   - Identify best-selling items
10. Stored Procedures
    - Update the order status after confirmed or failed delivery
    - Update status of promotional or voucher discounts that are no longer valid.
11. Functions
    - Verify if voucher applied by user is valid
    - Calculate average order value within specified date range. 

# Overall

## 1. Menu-Board

### a. Queries

1.  Retrieve all items available on the menu, including item name, description, category, and price based on branches.
2.  Filter item based on category type.
3.  Search item based on item name and description.

### b. Stored Procedures

1.  Add or remove items in a specific branch.

### c. Functions

1.  Determine if an item is available in specific branches.

## 2. Order Processing

### a. Queries

1.  Retrieve customers’ order history.

### b. Stored Procedures

1.  Record order details after customer places order.

### c. Functions

1.  Calculate applicable promotion discount.
2.  Calculate applied voucher.
3.  Verify if voucher applied by user is valid.
4.  Calculate the loyal points gained from the order.

## 3. Payment Processing

### a. Queries

1.  Display receipt with transaction details.

### b. Stored Procedures

1.  Record customer payment details.

### c. Functions

1.  Determine if the provided payment information is valid.

## 4. Delivery Processing

### a. Queries

1.  Identify all orders that require delivery based on order type.

### b. Stored Procedures

1.  Update the order status after confirmed or failed delivery.

### c. Functions

1.  Determine if the customer is a valid user in the system.

## 5. Membership Points

### a. Queries

1.  Retrieve details of a member’s loyalty points and membership tier.
2.  Display the history in which points are used.

### b. Stored Procedures

1.  Identify members eligibility for rewards.

### c. Functions

## 6. Order Progress

### a. Queries

1.  Display real-time order status to determine if it's being prepared, completed, or delivered.

### b. Stored Procedures

1.  Update order status.

### c. Functions

## 7. Items Modification

### a. Queries

1.  Identify out-of-stock items.

### b. Stored Procedures

1.  Update prices of items.

### c. Functions

## 8. Sales Management

### a. Queries

1.  Retrieve total sales for specific periods.
2.  Identify best-selling items.

### b. Stored Procedure

1.  Update status of promotional or voucher discounts that are no longer valid.

### c. Functions

1.  Calculate average order value within specified date range.
