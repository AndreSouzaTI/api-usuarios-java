# User Management API

A REST API for user management, built with Java 17 and Spring Boot following a layered architecture and development best practices. It provides CRUD (Create, Read, Update, Delete) operations for users backed by a MySQL database.

## Table of contents

- [Requirements](#requirements)
- [Tech stack](#tech-stack)
- [Project structure](#project-structure)
- [Getting started](#getting-started)
- [Testing the API](#testing-the-api)
- [Errors and exceptions](#errors-and-exceptions)

## Requirements

- Java 17
- Maven (dependency management)
- MySQL (database)
- Postman or cURL (optional, to test the API)

## Tech stack

- **Java 17** – programming language
- **Spring Boot** – framework for web applications and REST APIs
- **Spring Data JPA** – database access
- **Hibernate** – JPA implementation for persistence
- **MySQL** – relational database
- **Lombok** (optional) – reduces boilerplate such as getters and setters
- **Maven** – dependency management

## Project structure

```
src/
└── main/
    ├── java/com/example/APIgerenciamentodeusuarios/
    │   ├── controller/      # Request handlers
    │   ├── model/           # Data models (entities)
    │   ├── repository/      # Repositories (database access)
    │   ├── service/         # Business logic
    │   ├── dto/             # Data transfer objects (DTOs)
    │   └── exception/       # Custom exceptions
    └── resources/
        └── application.properties   # Application configuration
```

## Getting started

Clone the repository:

```bash
git clone https://github.com/AndreSouzaTI/api-usuarios-java.git
```

Configure your MySQL connection in `application.properties`, then run:

```bash
mvn spring-boot:run
```

The application will be available at http://localhost:8080.

## Testing the API

You can use Postman, cURL or any HTTP client. The endpoints are mapped at the application root (`http://localhost:8080/`).

### 1. Create a user (POST)

```http
POST /
Content-Type: application/json

{
  "name": "João Silva",
  "email": "joao.silva@example.com"
}
```

Response:

```json
{
  "id": 1,
  "name": "João Silva",
  "email": "joao.silva@example.com"
}
```

### 2. Get all users (GET)

```http
GET /
```

Response:

```json
[
  {
    "id": 1,
    "name": "João Silva",
    "email": "joao.silva@example.com"
  }
]
```

### 3. Get a user by ID (GET)

```http
GET /1
```

### 4. Update a user by ID (PUT)

```http
PUT /1
Content-Type: application/json

{
  "name": "João Pedro",
  "email": "joao.pedro@example.com"
}
```

Response:

```json
{
  "id": 1,
  "name": "João Pedro",
  "email": "joao.pedro@example.com"
}
```

### 5. Delete a user by ID (DELETE)

```http
DELETE /1
```

## Errors and exceptions

The API returns appropriate error responses, such as:

- **404 Not Found** – the user does not exist
- **400 Bad Request** – the request contains invalid data
- **500 Internal Server Error** – unexpected server errors

Example 404 response:

```json
{
  "timestamp": "2024-10-10T12:34:56",
  "status": 404,
  "error": "Not Found",
  "message": "User not found with id: 1",
  "path": "/1"
}
```
