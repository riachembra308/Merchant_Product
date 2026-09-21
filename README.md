# Merchant-Product Management System

A Java Hibernate + MySQL console-based application for managing merchants and their products. The project demonstrates CRUD operations, Hibernate/JPA entity relationships, and database interaction using a layered architecture.

Features

* Add and update merchant details
* Find merchants by ID, product ID, and product name
* Add and update products
* Find products by ID and merchant ID
* Find products using merchant name and password
* Establish a One-to-Many relationship between Merchant and Product
* Perform database operations using Hibernate/JPA
* Store and manage data in MySQL

Technologies Used

* Java
* Hibernate / JPA
* MySQL
* Maven
* Eclipse/IDE
* JPQL/HQL

Project Structure

The application follows a simple layered structure:

* DTO – Contains Merchant and Product entity classes
* DAO – Handles database operations using Entity Manager
* Controller – Provides a console-based menu to interact with the application

A merchant can have multiple products, while each product belongs to one merchant.



