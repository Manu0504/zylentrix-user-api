# User Management REST API

## 🚀 Overview
This is a **Spring Boot REST API** for managing users, providing **CRUD operations** (Create, Read, Update, Delete).  
The API stores user details including **name, email, and age** in a MySQL database.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 📂 Project Structure

UserManagementAPI/
│── src/
│   ├── main/
│   │   ├── java/com/example/
│   │   │   ├── controller/
│   │   │   │   ├── UserController.java
│   │   │   ├── model/
│   │   │   │   ├── User.java
│   │   │   ├── repository/
│   │   │   │   ├── UserRepository.java
│   │   │   ├── service/
│   │   │   │   ├── UserService.java      # Interface
│   │   │   ├── serviceimpl/
│   │   │   │   ├── UserServiceImpl.java  # Implementation
│   │   │   ├── Application.java
│   │   ├── resources/
│   │   │   ├── application.properties
│   ├── test/
│── pom.xml
│── README.md

✅ Folder Breakdown
Folder	                                                  Purpose
controller :                              Contains UserController.java, which handles API requests.
entity	   :                              Holds User.java, the entity representing a User.
repository :                            	Contains UserRepository.java for database operations.
service    :                            	Defines UserService.java (interface for user services).
serviceimpl:                            	Implements UserServiceImpl.java (actual service logic).
resources  :                            	Contains application.properties for database configs.

test/	For unit testing (optional for now).
pom.xml	Maven dependencies.
README.md	Project documentation.

---------------------------------------------------------------------------------------------------------------------------------------------------------------

## ⚙️ Setup Instructions

### **1️⃣ Prerequisites**
- **Java 17+** (JDK)
- **Maven** (Ensure it's installed)
- **MySQL Database**
- **Postman** (For API testing)

Configure Database (MySQL)

Open application.properties (src/main/resources/application.properties)
Update the MySQL configurations:

spring.datasource.url=jdbc:mysql://localhost:3306/userdb
spring.datasource.username=root
spring.datasource.password=yourpassword

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

Create a database in MySQL:

CREATE DATABASE userdb;

----------------------------------------------------------------------------------------------------------------------------------------------------------------

📌 API Endpoints Documentation

1️⃣ Create a User
     URL: POST /api/users
     Body (JSON): 
        {
           "name": "John Doe",
           "email": "john@example.com",
           "age": 25
        }
        
  Response:
    {
       "id": 1,
       "name": "John Doe",
       "email": "john@example.com",
       "age": 25
   }
   
2️⃣ Get All Users
URL: GET /api/users

Response:
 [ {
    "id": 1,
    "name": "Manu Kumar",
    "email": "prince.bok0504@gmail.com",
    "age": 22
  } ]

3️⃣ Get User by ID
URL: GET /api/users/{id}

Response :
{
     "id": 1,
    "name": "Manu Kumar",
    "email": "prince.bok0504@gmail.com",
    "age": 22
}

If User Not Found (404):
{
  "error": "User not found"
}

4️⃣ Update a User
URL: PUT /api/users/{id}

Body (JSON):
{
    "name": "Manu Gupta",
    "email": "prince.bok0504@gmail.com",
    "age": 22
}

Response:
{
    "id": 1,
    "name": "Manu Gupta",
    "email": "prince.bok0504@gmail.com",
    "age": 22
}

5️⃣ Delete a User
URL: DELETE /api/users/{id}

Response (200 OK): No body

If User Not Found (404):
{
  "error": "User not found"
}


🛠️ Error Handling

Error	                                 HTTP Code	                                          Response
Invalid Input	                       400 Bad Request	                          { "error": "Invalid input data" }
User Not Found	                     404 Not Found	                            { "error": "User not found" }
Internal Server Error	               500 Server Error	                          { "error": "Something went wrong" }

------------------------------------------------------------------------------------------------------------------------------------------------------------------

📸 Test Screenshots

![image](https://github.com/user-attachments/assets/b440c5fd-e3de-4d6e-9188-ac27d1dd84f4)

![image](https://github.com/user-attachments/assets/fb396a8b-3c36-487c-95c8-ccb94cf26b0d)

![image](https://github.com/user-attachments/assets/347e0deb-cb9b-4624-908a-9b05da9d3b89)

![image](https://github.com/user-attachments/assets/0107455c-ab77-4c48-b736-aef2abb048bc)

![image](https://github.com/user-attachments/assets/393d2a72-8847-4117-86e7-7aef04fb7279)

-----------------------------------------------------------------------------------------------------------------------------------------------------------------

📜 License
This project is open-source and free to use.

