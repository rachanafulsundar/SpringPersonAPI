# Person API Project

This project is a simple **Spring Boot** application for managing person entities. It provides a RESTful API to perform basic CRUD (Create, Read, Update, Delete) operations on a person database.

---

## Features

- **Add a new person**: Create and store information about a person.
- **Retrieve all persons**: Fetch the list of all stored persons.
- **Retrieve a person by their unique ID**: Access specific details of a person.
- **Update an existing person**: Modify details of an existing person.
- **Delete a person by their unique ID**: Remove a person from the database.

---

## Tech Stack

- **Java**: Primary programming language.
- **Spring Boot**: Framework for building the application.
- **RESTful API**: Enables communication between the client and server.
- **Maven**: Dependency and build management.
- **H2 Database**: In-memory storage for testing purposes.

---

## Setup Instructions

### Prerequisites

1. **Java Development Kit (JDK)**: Ensure JDK 11 or higher is installed.
2. **Maven**: Install Maven for dependency management.
3. **IDE**: Use an IDE like IntelliJ IDEA, Eclipse, or VS Code.

### Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/person-api.git
   cd person-api
   ```

2. Build the project using Maven:
   ```bash
   mvn clean install
   ```

3. Run the application:
   ```bash
   mvn spring-boot:run
   ```

4. Access the application at:
   ```
   http://localhost:8080/api/v1/person
   ```

---

## API Endpoints

### Base URL
`http://localhost:8080/api/v1/person`

### Endpoints

| Method   | Endpoint          | Description                    |
|----------|-------------------|--------------------------------|
| `POST`   | `/`               | Add a new person.             |
| `GET`    | `/`               | Retrieve all persons.          |
| `GET`    | `/{id}`           | Retrieve a person by ID.       |
| `PUT`    | `/{id}`           | Update a person by ID.         |
| `DELETE` | `/{id}`           | Delete a person by ID.         |

### Example Requests

#### Add a New Person
```bash
POST /api/v1/person
Content-Type: application/json

{
    "name": "John Doe"
}
```

#### Get All Persons
```bash
GET /api/v1/person
```

#### Get a Person by ID
```bash
GET /api/v1/person/{id}
```

#### Update a Person
```bash
PUT /api/v1/person/{id}
Content-Type: application/json

{
    "name": "Jane Doe"
}
```

#### Delete a Person
```bash
DELETE /api/v1/person/{id}
```

---

## Project Structure

```plaintext
src/main/java/com/example/demo
|-- DemoApplication.java
|-- api
|   |-- PersonController.java
|-- dao
|   |-- FakePersonDataAccessService.java
|   |-- PersonDao.java
|-- model
|   |-- Person.java
|-- service
    |-- PersonService.java
```

### Overview

- **DemoApplication.java**: Entry point of the application.
- **api/PersonController.java**: Handles incoming API requests and routes them to services.
- **dao**: Data Access Layer for CRUD operations.
  - `FakePersonDataAccessService`: An in-memory database simulation.
  - `PersonDao`: Interface for defining database operations.
- **model/Person.java**: Defines the structure of the `Person` entity.
- **service/PersonService.java**: Implements the business logic for managing person data.

---

## Future Improvements

- **Persistent Database**: Replace the in-memory database with a persistent database like MySQL or PostgreSQL.
- **Validation**: Add validation for API inputs.
- **Authentication and Authorization**: Secure the API with user authentication and role-based access control.
- **Testing**: Add unit and integration tests for better reliability.
