# CrewConnect with JWT Authentification

A secure, full-featured CrewConect with JWT Authentification System built using **Spring Boot 3**, **Spring Security**, and **JWT**, supporting role-based access for `ADMIN` and `USER`. This application enables authenticated users to manage employee records securely through a RESTful API.



## Features

✅ User Registration & Login  
✅ JWT Authentication & Role-Based Authorization (`ADMIN`, `USER`)  
✅ Secured CRUD operations on Employee records  
✅ Swagger UI with JWT Token Support  
✅ Password Encryption using `BCryptPasswordEncoder`  
✅ Global Exception Handling using `@ControllerAdvice`  
✅ In-memory H2 and optional PostgreSQL DB support  
✅ Dockerized for Easy Deployment  
✅ Clean layered architecture with Spring Data JPA  
✅ Unit & Integration Testing Ready


## Tech Stack

- Java 17  
- Spring Boot 3.x  
- Spring Web  
- Spring Security  
- JWT (jjwt / auth0)  
- Spring Data JPA  
- H2 / PostgreSQL  
- Lombok  
- Swagger (OpenAPI)  
- Docker  
- Maven


## Project Structure

```
├── src
│   ├── main
│   │   ├── java/com/example/ems
│   │   │   ├── controller
│   │   │   ├── model
│   │   │   ├── repository
│   │   │   ├── security
│   │   │   ├── service
│   │   │   └── exception
│   │   └── resources
│   │       ├── application.properties
│   │       └── data.sql


## 🔐 Role-Based Access Control

| Role     | Endpoints                         | Access        |
|----------|-----------------------------------|---------------|
| USER     | `GET /api/employees`             | View only     |
|          | `GET /api/employees/{id}`        | View only     |
| ADMIN    | All CRUD operations               | Full access   |


## 📑 API Endpoints

### 🔐 Auth Controller

| Method | Endpoint             | Description         |
|--------|----------------------|---------------------|
| POST   | `/api/auth/register` | Register new user   |
| POST   | `/api/auth/login`    | Login and receive JWT token |


### 👨‍💼 Employee Controller (JWT Protected)

| Method | Endpoint                     | Role    | Description            |
|--------|------------------------------|---------|---------------------   |
| GET    | `/api/employees`             | ADMIN, USER | Get all employees  |
| GET    | `/api/employees/{id}`        | ADMIN, USER | Get employee by ID |
| POST   | `/api/employees`             | ADMIN   | Create employee        |
| PUT    | `/api/employees/{id}`        | ADMIN   | Update employee        |
| DELETE | `/api/employees/{id}`        | ADMIN   | Delete employee        |



##  JWT Usage

1. Register a user via `/api/auth/register`
2. Login via `/api/auth/login` to receive the JWT token
3. Add the token in the `Authorization` header as:  
   
   Authorization: Bearer <your_token_here>
   
4. Use secured endpoints
## 📘 Swagger API Docs

Visit: `http://localhost:8080/swagger-ui/index.html`  
Use "Authorize" button to enter JWT and test endpoints.



##  Docker Instructions

1. Build the project:
   ```bash
   mvn clean package
   ```
2. Build Docker image:
   ```bash
   docker build -t employee-management-app .
   ```
3. Run the container:
   ```bash
   docker run -p 8080:8080 employee-management-app
   ```



##  Run Locally (Without Docker)

```bash
git clone https://github.com/jodosjodos/employee--management-system.git
cd employee--management-system
mvn clean install
mvn spring-boot:run
```

##  Testing

Add unit/integration tests using:
- JUnit 5
- Spring Boot Test
- MockMvc for controller layer
- Test JWT authorization flows


##  License

This project is licensed under the MIT License.



##  Author
Made by [Prerana Babli]  
