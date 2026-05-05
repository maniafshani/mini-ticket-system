# Mini-Ticket-System – Java Spring Boot REST API

A small learning project for managing tickets in a project workflow.  
The goal is to practice Java, Spring Boot, SQL/JPA, Maven, REST APIs, Git and basic testing with JUnit.

## Features

- Create, read, update and delete tickets
- Track ticket status: `OPEN`, `IN_PROGRESS`, `DONE`
- Store tickets in an H2 SQL database
- Validate required fields such as title and status
- Basic service-layer unit tests with JUnit and Mockito
- Simple REST endpoints for testing with Postman, curl or IntelliJ HTTP Client

## Technologies

- Java 17
- Spring Boot
- Spring Web
- Spring Data JPA
- Maven
- H2 Database
- JUnit 5
- Mockito

## Project Structure

```text
src/main/java/com/mani/tickets
├── TicketApplication.java
├── controller
│   └── TicketController.java
├── model
│   ├── Ticket.java
│   └── TicketStatus.java
├── repository
│   └── TicketRepository.java
└── service
    └── TicketService.java
```

## How to Run

```bash
mvn spring-boot:run
```

The application starts on:

```text
http://localhost:8080
```

The H2 database console is available at:

```text
http://localhost:8080/h2-console
```

Use these settings:

```text
JDBC URL: jdbc:h2:mem:ticketdb
User Name: sa
Password: password
```

## REST Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/tickets` | Get all tickets |
| GET | `/api/tickets/{id}` | Get one ticket by ID |
| POST | `/api/tickets` | Create a new ticket |
| PUT | `/api/tickets/{id}` | Update an existing ticket |
| DELETE | `/api/tickets/{id}` | Delete a ticket |

## Example Request

```http
POST /api/tickets
Content-Type: application/json

{
  "title": "Fix login validation",
  "description": "Check empty email and password fields",
  "status": "OPEN",
  "assignee": "Mani"
}
```

## Example Response

```json
{
  "id": 1,
  "title": "Fix login validation",
  "description": "Check empty email and password fields",
  "status": "OPEN",
  "assignee": "Mani"
}
```

## Run Tests

```bash
mvn test
```

## What I Practiced

- Building a small REST API with Spring Boot
- Structuring a backend project into controller, service, repository and model layers
- Using SQL persistence through Spring Data JPA
- Writing simple unit tests for business logic
- Documenting endpoints and setup steps
