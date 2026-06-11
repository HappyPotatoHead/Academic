> [!INFO] Question
> Analyse requirements study (briefly explain the requirements/ office / business rules in the system).
> PLEASE INCLUDE ANY ASSUMPTIONS THAT YOU MAKE.

# Requirements

The system aims to facilitate efficient order taking, payment processing, and transaction management at the counter, kiosks, and online order. The system can also integrate with potential future modules like inventory management.

# Business Rules

1. One staff can have multiple roles and one role can be played by multiple staffs.
2. Each staff can manage zero or many orders.
3. Each customer makes one or many orders.
4. Each customer can only have one membership account.
5. Customers may not be members.
6. Each member can have none or a lot of vouchers.
7. Each voucher can be owned by none or a lot of members.
8. Each voucher can be used in a lot of orders, but each order can only have one voucher redemption.
9. Each order can have none or one promotional discount.
10. Each promotional discount can be applied in multiple orders.
11. Each branch is managed by one staff.
12. Each branch has one or many items.
13. Different branches may have different items.

# Assumption

1. Assume all of the branches are situated in Malaysia and transactions are done in Malaysian Ringgit.
2. Only members can make online orders.
3. The restaurant has a defined menu with fixed items and prices, albeit customisations are possible.
4. Delivery is done in-house.
5. The employees are allowed to modify the availability of the items in the branch.
6. The employees are allowed to either accept or cancel the customers’ orders depend on the availability of the inventory.
7. The prices for menu items are centrally managed and updated by an authorised personnel.
8. The system has a mechanism to define and manage various types of discounts.
9. The user interface is assumed to be intuitive and simple to allow staff to use with speed and accuracy in order taking.
10. Each order has to be confirmed by a staff prior to preparing the order.

