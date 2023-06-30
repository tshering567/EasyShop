# EasyShop Backend Project
This is the README file for the EasyShop backend project. This project aims to enhance and fix existing functionalities
of the backend API built with Spring Boot and MySQL.

## Bugs
There are two Bugs that need to be addressed.Manual debugging and unit testing was utilized to identify and fix these bugs 
effectively.

## General Guidelines
* Used GitHub project board to plan and manage your work and time effectively.
* Postman was used to test API endpoints and logic
* A front-end website is also available for testing and demonstrating API usage.

## Getting Started
* Executed the provided MySQL database script 'create_database.sql' using MySQL
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
![](C:\LearnToCode_Capstones\token.png)

## Phase 1 - CategoriesController
The CategoriesController class and the corresponding MySqlCategoriesDao had been created but required implementation.\

Methods implemented on Categories Controller
* getAll() - GET request to retrieve all categories.
* getById(id) - GET request to retrieve a category by ID.
* addCategory(category) - POST request to add a new category (accessible only to administrators).
* updateCategory(id, category) - PUT request to update a category by ID (accessible only to administrators).
* deleteCategory(id) - DELETE request to delete a category by ID (accessible only to administrators).

Methods implemented on MySqlCategoryDao
* getAllCategories() - Retrieves all categories from the database.
* getById(id) - Retrieves a specific category from the database based on its ID.
* create(category) - Creates a new category in the database.
* update(id, category) - Updates an existing category in the database based on its ID.
* delete(id) - Deletes a category from the database based on its ID.


## Phase 2 - Fix Bugs
### Bug 1 : Incorrect Search Results
Product search functionality was returning incorrect results. The query inside the Search method of MYSqlProduct was
updated to fix the issue.
![](C:\LearnToCode_Capstones\Bug1.png)
### Bug 2 : Duplicate Products
The bug caused a new product to be created whenever the admin tried to update a product.The UpdateProduct() method
in the ProductController class was altered to fix this issue.
![](C:\LearnToCode_Capstones\bug2.png)
## Changes Made
* Added required annotations
* Updated method implementation for getAll(),getByCategoryID(),getProductsByCategoryId(),
addCategory(), updateCategory() and deleteCategory().
* Added ResponseEntity<> to have control over the HTTP response, including status codes and headers.
* Added SQL Queries to MySqlCategoryDao
## Postman Tests
![](C:\LearnToCode_Capstones\Postman_tests.png)

## Web Application
![](C:\LearnToCode_Capstones\web.png)