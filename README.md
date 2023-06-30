# EasyShop Backend Project
This is the README file for the EasyShop backend project. This project aims to enhance and fix existing functionalities
of the backend API built with Spring Boot and MySQL.

## Bugs
There are two Bugs that need to be addressed.Manual debugging and unit testing should be utilized to identify and fix these bugs 
effectively.

## General Guidelines
* Use GitHub project board to plan and manage your work and time effectively.
* Postman should be used to test API endpoints and logic
* A front-end website is also available for testing and demonstrating API usage.

## Getting Started
* Execute the provided MySQL database script 'create_database.sql' using MySQL
Workbench to create the 'easyshop' database.
* The database script includes sample products and three sample users: 'user', 'admin' and 'george'. The password for
all demo users is 'password'.

## Application Structure
The EasyShop backend application uses a Spring Boot API project for handling various endpoints and a MySQL database for 
data storage. The existing code includes an 'AuthenticationController' class for user registration and login.

# Register
* URL :'POST http://localhost:8080/register'
* Body: {\
          "username": "admin",\
          "password": "password",\
          "confirmPassword" : "password",\
          "role" : "ADMIN"\
        }

# Login 
* URL : 'POST http://localhost:8080/login'
* Body:{\
"username":"admin",\
"password":"password"\
}
* Successful login response includes a JWT authentication token.

## Phase 1 - CategoriesController
The CategoriesController class and the corresponding MySqglCategoriesDao have been created but require implementation
 Only administrators (users with the ADMIN role) should be allowed to perform CRUD operations on categories.

## Phase 2 - Fix Bugs
### Bug 1 : Incorrect Search Results
Users have reported that the product search functionality is returning incorrect results. You need to test and
fix the search logic
### Bug 2 : Duplicate Products
Some products appear to be duplicated with slight differences, such as the description or price. Investigate and
resolve the issue to ensure the product listings are accurate.
