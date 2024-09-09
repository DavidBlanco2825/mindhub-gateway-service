# Gateway Service

**Author:** [David Fernando Blanco](https://github.com/DavidBlanco2825)

## Overview

**Gateway Service** serves as the entry point for the **NoteList** application. It routes incoming HTTP requests to the appropriate microservices (such as **User Service** and **Task Service**) based on predefined routes. By using **Spring Cloud Gateway**, the service provides load balancing, request routing, and filtering, making it essential for managing and securing API traffic.

### Key Features

- **API Gateway**: Serves as a single entry point for all external clients, routing requests to the appropriate microservices.
- **Load Balancing**: Distributes incoming traffic across multiple instances of the microservices.
- **Path-based Routing**: Routes requests based on the URL path to ensure they reach the correct microservice.
- **Global Filters**: Handles cross-cutting concerns like authentication, rate limiting, and security through filters.
- **Service Discovery**: Integrates with **Eureka Server** to dynamically route requests to available services.

As the central gateway, this service ensures that traffic is routed efficiently to the microservices, providing a secure and reliable entry point for the **NoteList** application.

## Technologies Used

- **Spring Boot**: Provides the foundational framework for developing the Gateway Service.
- **Spring Cloud Gateway**: Facilitates dynamic routing and filtering for incoming API requests.
- **Spring Security**: Adds security features such as JWT-based authentication to protect the APIs.
- **Spring Cloud Netflix Eureka**: Allows integration with Eureka for dynamic service discovery and load balancing.
- **JUnit & Mockito**: For testing and verifying the gateway routing and security mechanisms.

## Getting Started

### Prerequisites

- **Java 17** or later
- **Maven 3.6** or later
- **Git** (for version control)

### Installation

1. **Clone the repository**:
    ```bash
    git clone https://github.com/DavidBlanco2825/mindhub-gateway-service.git
    cd mindhub-gateway-service
    ```

2. **Build the project**:
    ```bash
    mvn clean install
    ```

3. **Run the application**:
    ```bash
    mvn spring-boot:run
    ```

4. **Access the application**:
   - The Gateway Service will be accessible at `http://localhost:8080`. All requests to **User Service** and **Task Service** will be routed through this gateway.

## Routing

The **Gateway Service** uses path-based routing to direct requests to the correct microservices. The following routes are configured:

- **/api/users/**: Routes to the **User Service**.
- **/api/tasks/**: Routes to the **Task Service**.

## Security and Filtering

**Spring Security** and JWT-based authentication are integrated into the Gateway Service to protect endpoints from unauthorized access. You can configure custom filters to add functionality such as:

- **Authentication**: JWT-based authentication for securing APIs.
