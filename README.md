# ContactService

ContactService is a reactive RESTful service designed to handle the creation and retrieval of contact messages. This service is used in conjunction with the PowerLog application to manage user contacts efficiently.

## Features

- Save new contacts
- Fetch all contacts
- Fetch contacts created after a specified date and time
- Produce contact messages to Apache Kafka for real-time processing

## Technologies Used

- Spring Boot
- Spring Reactive
- R2DBC
- MySQL
- Flyway for data migration tool
- Spring Security
- Gradle for build automation
- Apache Kafka
- OpenAPI
- Lombok

## Getting Started

### Prerequisites

- Java 17 or higher
- Gradle
- MySQL (or any other SQL database)
- Apache Kafka

### Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/hyuseinlesho/contact-service.git
    ```

2. Set environment variables for your database username and password:
    ```sh
    DB_USERNAME=your_username
    DB_PASSWORD=your_password
    ```

3. Create contact_service database
    ```sql
    create schema contact_service;
    ```

5. Install and run Apache Kafka server.

6. Run the application.

### API Documentation

This project uses springdoc-openapi to generate API documentation.

You can access the Swagger UI to explore and interact with the API by running the application and navigating to the following URL in your web browser:
    ```
    http://localhost:8081/swagger-ui.html
    ```

### Apache Kafka

- **Kafka Server Requirement:**
  - Ensure Apache Kafka is installed and running to test it locally.

- Produces messages to the Kafka topic `contact-topic` when a new contact is created.
- Configured bootstrap servers, key and value serializers in `application.yaml` file.

### Reactive Service

- **Reactive Programming**: Utilizes Spring Reactive to handle asynchronous data streams.
- **Controller and Service**: Manages contact creation and retrieval using reactive endpoints.
- **R2DBC**: Reactive relational database connectivity.
- **Non-Blocking**: All operations are non-blocking, providing better scalability and performance.

### Flyway for Data Migration

- **Database Migrations**: Uses Flyway to handle database schema migrations.
- **Initial Migration**: Schema defined in `resources/db/migration/V1__init.sql`:

![contacts-schema](https://github.com/user-attachments/assets/798516da-5308-46cf-9a55-2da2a805272a)

This setup allows the ContactService to handle real-time notifications and efficient management of user contacts.
