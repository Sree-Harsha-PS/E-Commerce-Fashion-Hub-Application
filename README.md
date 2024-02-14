# Welcome to Ecommerce Fashion Hub

## Project Overview
Welcome to Ecommerce Fashion Hub, a cutting-edge project developed in understanding of Database Management Systems (DBMS). 
This project encompasses both theoretical concepts and practical implementations in SQL, offering a comprehensive understanding of database management in the realm of fashion ecommerce. If you find this project useful, show your support by starring it!

## Prerequisites
To run this project, ensure you have MariaDB installed.

## Table of Contents
- [Project Description](#1-project-description)
- [Requirements](#2-requirements)
    - [Functional Requirements](#21-functional-requirements)
- [Relational Database Schema](#3-relational-database-schema---e-commerce)
    - [Entities and their Attributes](#4-entities-and-their-attributes)
- [Entities and Relations](#5-entities-and-relations)
- [ER-Diagram](#6-er-diagram)
- [Queries](#7-queries-on-the-above-relational-schema)


## 1. Project Description
In today's digital age, the fashion industry is embracing online platforms for exponential growth. Ecommerce Fashion Hub aims to facilitate this transition by providing a robust database system tailored for fashion ecommerce. Our project focuses on enabling small-scale fashion sellers to efficiently sell their products online.

**Key Objectives**:
- Facilitating viewing and placing orders
- Updating the database seamlessly
- Providing a platform for reviewing products
- Ensuring data consistency across all tables

## 2. Requirements
### 2.1 Functional Requirements
- Customers can view and update their account details.
- Customers can search for products by category.
- Customers can add items to their wishlist and cart, viewing the total amount.
- Customers can update their cart and choose a mode of payment.
- Customers can track their order status and review purchased products.
- Sellers can update product stock availability and track total sales.
- Sellers can monitor sales trends on specific days, months, or years.
- 
## 3. Relational Database Schema - E-commerce
Check the Relational Schema Diagram for a clearer view.
![image](https://github.com/Sree-Harsha-PS/E-Commerce-Fashion-Hub-Application/assets/95706697/d4e32601-4fa1-41ae-b29b-255a6442007c)


### 4. Entities and their Attributes

| ENTITIES |  ATTRIBUTES                                                                       |    ATTRIBUTE TYPE                                                 |Entity Type|
| ---------|:-------------:                                                                    |   -----:                                                          |-------    |
| Customer |Customer_CustomerId<br>Name<br>Email<br>DateOfBirth<br>Phone<br>Age                |Simple<br>Composite<br>Simple<br>Simple<br>Multivalued<br>Derived  | Strong    |
| Order    |OrderId<br>ShippingDate<br>OrderDate<br>OrderAmount<br>Cart_CartID                 |Simple<br>Simple<br>Simple<br>Simple<br>Simple                     | Strong    |
| OrderItem|Order_OrderId (PK)<br>Product_ProductId(FK)<br>MRP<br>Quantity                     |Simple<br>Simple<br>Simple<br>Simple                               |  Weak     | 
| Product  |productId (PK)<br>ProductName<br>sellerId<br>MRP<br>CategoryID<br>Stock<br>Brand   |Simple<br>Simple<br>Simple<br>Simple<br>Simple<br>Simple<br>Simple |Strong     | 
| Review   |ReviewId(PK)<br>Description<br>Ratings<br>Product_ProductId<br>Customer_CustomerID |Simple<br>Simple<br>Simple<br>Simple                               |Strong     |
| Cart     |cartId (PK)<br>Customer_customerId(FK)<br>GrandTotal<br>ItemsTotal                 | Simple<br>Simple<br>Derived<br>Derived                            |Strong     | 
| Category |CategoryID(PK)<br>CategoryName<br>DESCRIPTION                                      | Simple<br>Simple<br>Simple                                        |Strong     |
| seller   |sellerId (PK)<br>Name<br>Phone<br>Total_Sales                                      | Simple<br>Simple<br>Multivalued<br>Derived                        |Strong     |
| Payment     |payment_id<br>Order_OrderId<br>PaymentMode<br>Customer_CustomerId<br>PaymentDate   | Simple<br>Simple<br>Simple<br>Simple<br>Simple                    |Strong     |

### 5. Entities and Relations 
Explore the relationships between entities, their cardinality, and participation types in the repository.

| ENTITIES |RELATION |   CARDINALITY                                          | TYPE OF PARTICIPATION|
| ---------|:-------------:                                                                    |   -----:                                                          |-------    |
|Customer<BR>Address| Stays At| OneToOne |    Total<BR>Partial  |
|Customer<BR>Cart|Shops| OneToOne|Partial<BR>Total  |
|Customer<br>Order|Places| OneToMany| Partial<BR>Total |
|Customer <BR>Payment| Makes| OneToMany|Partial<br>Total |
|Customer<BR>Review| Write| OneToMany|Partial<br>Total  |
|Seller<br>Product| Sells|ManyToMany| Partial<br>Total |
|Category<br>Product|Categorizes|OneToMany|Partial<br>Total  |
|Cart<br>Product|Contains|ManyToMany| Partial<br>Partial |
|Product<br>Orderltem| Includes|OneToMany|Partial<br>Total|
|Order<br>Orderltem| Includes|OneToOne|Partial<br>Total|
|Payment<br>Order| For|OneToOne|Total<br>Total|


## 6. ER-Diagram
View the ER-Diagram image for a visual representation.

## 7. Queries on the Above Relational Schema
1. Stored procedure for retrieving customer details.
2. View for obtaining sales by product category.
3. Utilizing triggers to update product quantities upon payment.
4. Trigger to update the total amount whenever a user adds items to the payment table.
5. Stored procedure for accessing order history.
6. Processing orders efficiently.

For detailed implementation of the above queries and more, feel free to reach out via email: [sreeharshapolepalli@gmail.com](mailto:sreeharshapolepalli@gmail.com).

---
