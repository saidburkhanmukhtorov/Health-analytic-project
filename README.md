## Health Analytics Service with API Gateway

This project implements a microservice-based health analytics system with an API gateway. It provides functionalities for managing various health data types, including:

* **Genetic Data:** Storing and retrieving genetic information.
* **Health Recommendations:** Managing personalized health recommendations.
* **Lifestyle Data:** Tracking lifestyle data such as sleep, diet, and exercise.
* **Medical Records:** Storing and accessing medical history and records.
* **Wearable Data:** Integrating data from wearable devices like smartwatches and fitness trackers.

The system also includes a health monitoring service that provides daily and weekly summaries of user health data.

### Architecture

The project follows a microservice architecture with the following components:

* **API Gateway (api-gateway-health-analytics):** Acts as a single entry point for clients, handling authentication, authorization, request routing, and aggregation of responses from different services.
* **Health Analytics Service (health-analytics-service):** Provides the core business logic for managing health data. It consists of separate services for each data type and the health monitoring service.
* **Authentication Service (auth-for-health-analytics):** Handles user authentication and authorization.
* **Kafka:** Used for asynchronous communication between the API gateway and the health analytics services.
* **MongoDB:** Used as the primary database for storing health data.
* **Redis:** Used for caching and session management in the authentication service.

### Technologies Used

* **Go:** The primary programming language for all services.
* **gRPC:** Used for communication between the API gateway and the health analytics services.
* **Protocol Buffers:** Used for defining data structures and service interfaces.
* **Gin:** Used as the web framework for the API gateway.
* **Swagger:** Used for API documentation.
* **Kafka:** Used as the message broker for asynchronous communication.
* **MongoDB:** Used as the NoSQL database for storing health data.
* **Redis:** Used as the in-memory data store for caching and session management.
* **Docker:** Used for containerizing the services.
* **Docker Compose:** Used for orchestrating the services locally.

### How to Run

1. **Prerequisites:**
   * Docker and Docker Compose installed.
   * A running Kafka instance.
   * A running MongoDB instance.
   * A running Redis instance.

2. **Clone the Repository:**
   ```bash
   git clone git@github.com:saidburkhanmukhtorov/Health-analytic-project.git
   ```
  or 
  ```
  git clone https://github.com/saidburkhanmukhtorov/Health-analytic-project.git
  ```
  or 
  ```
  gh repo clone saidburkhanmukhtorov/Health-analytic-project
  ```
```
  cd Health-analytic-project
  git submodule update --remote --recursive

  # Stop all existing containers
  sudo docker compose down

  # Start orchestre container
  sudo docker compose up -d --build

  # Build and start Analytics Service
  cd health-analytics-service
  sudo docker compose down
  sudo docker compose up -d --build
  cd ..

  # Build and start API Gateway service
  cd api-gateway-health-analytics
  sudo docker compose down
  sudo docker compose up -d --build
  cd ..

  # Build and start Auth Service
  cd auth-for-health-analytics
  sudo docker compose down
  sudo docker compose up -d --build
  cd ..

  echo "Deployment complete."```
