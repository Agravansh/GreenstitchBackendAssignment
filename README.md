# GreenStitch Backend Assignment
# Login and Signup Backend API with Spring Security and JWT Tokens

This project is a backend implementation of a login and signup REST API with security and JWT tokens. It is built using Java, and Spring Boot, and utilizes the H2 database for data storage. The API endpoints provided below demonstrate the functionality of the application.

## Installation and Setup

```
### Prerequisites
- Java Development Kit (JDK) 8 or later
- Maven
- Postman (for testing the API)
```

### 1. Clone the Repository

```
git clone https://github.com/Agravansh/GreenstitchBackendAssignment.git
```

### 2. Go the Project

```
cd GreenStitchBackendAssignments/GreenStitch_Assignment

```

### 3. Run the Application
- For GitBash
```
./mvnw spring-boot:run

```
**The application will start running on [http://localhost:8888](http://localhost:8888)**



### User Login

- Method: GET
- Path: `http://localhost:8888/app/sign-in`
- Description: Authenticate a user and retrieve their details and JWT token.
- Authentication: Basic Authentication (Username and Password)
    - Username: [kapilagrawal341997@gmail.com](mailto:kapilagrawal341997@gmail.com)
    - Password: Kapil@123
- Response:

```
{
    "id": 1,
    "fullName": "Kapil Agrawal",
    "password": "$2a$10$pEHKFpepKVzhA7RXLgqumnZKFy3bT2X8wdJMW3tYH2yqUJcpHNmio",
    "email": "kapilagrawal341997@gmail.com",
    "role": "ROLE_USER"
}

```

### Welcome Endpoint (Requires Authentication)

- Method: GET
- Path: `http://localhost:8888/app/logged-in/user`
- Description: A protected endpoint that requires authentication to access.
- Authentication: Bearer Token
- Request Header:
    - Authorization: Bearer <token>
- Response: A welcome message string.
- Example:
    - Bearer Token: eyJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJTaGltYmh1Iiwic3ViIjoiSldUIFRva2VuIiwidXNlcm5hbWUiOiJza0BnbWFpbC5jb20iLCJyb2xlIjoiUk9MRV9VU0VSIiwiaWF0IjoxNjg1Njc3Mzg3LCJleHAiOjE2ODU3MDczODd9.VwM2IGD1fABjEcnNoMb4uIyBnYe3_BmZGx33dElaD-E
    - Response: Hello from GreenStitch


### Validation Rules

The following validation rules are applied to the user entity:

- Full Name:
    - Minimum length: 3 characters
    - Maximum length: 50 characters
- Password:
    - At least 8 characters
    - Contains at least one digit
    - Contains at least one lowercase letter
    - Contains at least one uppercase letter
    - Contains at least one special character
- Email:
    - Valid email format


## H2 Database Configuration

The project uses the H2 in-memory database by default.

The application is configured to use the H2 database. The configuration can be found in the `application.properties` file:

```
# Server Port Configuration
server.port=8888

# H2 Database Configuration
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.h2.console.enabled=true
spring.h2.console.path=/h2-console

```

## **Contributors**

- **[Kapil Agrawal](https://github.com/Agravansh)**
 
