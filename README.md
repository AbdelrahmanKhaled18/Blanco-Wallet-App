# Blanco Microservices Project

## Overview
The **Blanco Microservices Project** is a distributed system built using **Spring Boot** and **Docker**. It consists of multiple microservices that work together to manage budgets, expenses, analytics, notifications, and user authentication. The project is containerized using Docker and orchestrated with Docker Compose.

## Architecture
The project follows a microservices architecture, where each service is responsible for a specific domain. The services communicate with each other over a shared network.

### Services
1. **Blanco-MySQL**: A MySQL database for persistent storage.
2. **Blanco-Redis**: A Redis instance for caching and session management.
3. **Blanco-Database-Service**: A service that interacts with the MySQL database to manage data.
4. **Blanco-Authentication-Service**: Handles user authentication and authorization.
5. **Blanco-MoneyManagementService**: Manages budgets and financial data.
6. **Blanco-AnalyticsService**: Provides analytics and insights based on user data.
7. **Blanco-NotificationService**: Sends notifications to users.
8. **Blanco-APIManagerService**: Acts as the entry point for the system, aggregating data from other services and serving it to the client.

## Features
- **Budget Management**: Create, update, delete, and retrieve budgets.
- **Expense Tracking**: Manage and track user expenses.
- **Analytics**: Generate insights and reports based on financial data.
- **Notifications**: Notify users about important events or updates.
- **Authentication**: Secure user login and session management.

## Technologies Used
- **Java**: Programming language for all services.
- **Spring Boot**: Framework for building microservices.
- **MySQL**: Relational database for persistent storage.
- **Redis**: In-memory data store for caching.
- **Docker**: Containerization of services.
- **Docker Compose**: Orchestration of containers.
- **Thymeleaf**: Template engine for rendering views in the `APIManagerService`.

## Prerequisites
- **Docker** and **Docker Compose** installed on your system.
- **Java 17** or higher.
- **Maven** for building the project.

## Setup and Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/AbdelrahmanKhaled18/Blanco-Microservices.git
   cd Blanco-Microservices
   ```

2. Build the Docker images:
   ```bash
   docker-compose build
   ```

3. Start the services:
   ```bash
   docker-compose up
   ```

4. Access the services:
    - **API Manager Service**: [http://localhost:8080](http://localhost:8080)
    - Other services are accessible via their respective ports.

## Project Structure
```
Blanco-Microservices/
├── APIManagerService/
├── AuthenticationService/
├── MoneyManagementService/
├── DatabaseService/
├── AnalyticsService/
├── NotificationService/
├── compose.yaml
└── README.md
```

### Key Files
- `compose.yaml`: Defines the Docker Compose configuration for all services.
- `src/main/java`: Contains the source code for each service.

## Endpoints
### API Manager Service
- **GET** `/home`: Displays the home page with budgets and expenses.

### Money Management Service
- **GET** `/budgets/user/{userId}`: Retrieves all budgets for a user.
- **POST** `/budgets`: Creates a new budget.
- **PUT** `/budgets/{id}`: Updates an existing budget.
- **DELETE** `/budgets/{id}`: Deletes a budget.

## Environment Variables
- `MYSQL_DATABASE`: Name of the MySQL database.
- `MYSQL_USER`: MySQL username.
- `MYSQL_PASSWORD`: MySQL password.


## Contributing
1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Submit a pull request with a detailed description of your changes.

