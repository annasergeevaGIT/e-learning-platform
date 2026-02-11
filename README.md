# E-Learning Cloud Platform

A reactive, cloud-native, microservices-based backend platform built with Spring Boot, Spring Cloud, Apache Kafka, Redis, PostgreSQL, and Docker.
The system provides scalable, fault-tolerant, and observable services for managing users, courses, enrollments, feedback, and learning interactions in a distributed environment.

This platform delivers the core backend infrastructure for an e-learning system using modern microservice architecture principles, including horizontal scalability, decentralized configuration, service discovery, distributed tracing, resilience, and event-driven communication.

## Microservices Architecture

| Service                                                               | Description                       |
|-----------------------------------------------------------------------|-----------------------------------|
| [Enrollment Service](https://github.com/annasergeevaGIT/enrollment-service-e-learning-platform)   | Manages course enrollments |
| [Course Service](https://github.com/annasergeevaGIT/course-service-e-learning-platform)   | Handles courses and content|
| [Feedback Service](https://github.com/annasergeevaGIT/eedback-service-e-learning-platform) | Manages ratings and feedback |
| [Course Aggregate Service](https://github.com/annasergeevaGIT/aggregate-service-e-learning-platform)| Aggregates course and review data |
| [Gateway Service](https://github.com/annasergeevaGIT/gateway-service-e-learning-platform)| Routing, security, rate limiting |
| [Discovery Service](https://github.com/annasergeevaGIT/discovery-service-e-learning-platform)| Eureka Service registry |
| [Dispatcher Service](https://github.com/annasergeevaGIT/dispatcher-service-e-learning-platform)| Kafka producer/consumer (event streaming) |
| [Docker Deployment](https://github.com/annasergeevaGIT/dispatcher-service-e-learning-platform)| Centralized configuration management |

##  Architecture diagram
![diagram-export-5-15-2025-10_01_38-PM](https://github.com/user-attachments/assets/8f1875cd-ae41-4ca2-8b73-8ba56e5e4ebf)

---

### Core Responsibilities

- User registration, authentication, and role management
- Course management
- Enrollment processing
- Feedback and reviews
- Aggregated course data
- Backend APIs for frontend clients
- Observability, monitoring, and performance analysis
- End-to-end and isolated testing 

---

### Technology Stack

<p align="left">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=java,spring,postgres,hibernate,redis,kafka,docker,github,gradle,postman,grafana,prometheus&theme=light" />
  </a>
</p>

- **Framework:** Spring Boot, Spring Cloud
- **Reactive REST APIs:** WebFlux / Virtual Threads
- **Messaging:** Apache Kafka
- **Configuration Management:** Spring Cloud Config
- **Service Discovery & Routing:** Eureka, Spring Cloud Gateway
- **Resilience & Load Balancing:** Resilience4j, Spring Cloud LoadBalancer
- **Caching:** Redis
- **Tracing & Logging:** Zipkin, Logback
- **Persistence:** PostgreSQL (JPA/Hibernate + R2DBC where required)
- **Metrics:** Prometheus + Grafana
- **Security:** JWT / Keycloak
- **Containerization:** Docker, Docker Compose
- **API Documentation:** OpenAPI (Swagger)

---

### Key Features

Reactive programming with WebFlux, Event-driven architecture via Kafka, JWT-based stateless authentication, Circuit breaker patterns with Resilience4j, Service discovery and dynamic routing, Full containerized deployment, Observability-first design

---

### Running the Project with Docker

   ```bash
   git clone https://github.com/annasergeevaGIT/docker-deployment-e-learning-platform
   cd docker-deployment-e-learning-platform
   docker-compose up -d
   ```

---

### Available Docker Services

- `gateway-service`, `eureka-server`, `config-server`
- `order-service`, `menu-service`, `review-service`
- `notification-service`, `kafka`, `zookeeper`, `redis`, `zipkin`, `postgres`
- `keycloak`, `prometheus`, `grafana`, `loki`, `tempo`, `k6`

---

### 12-Factor App Practices

| Principle                  | Implementation Example |
|---------------------------|------------------------|
| One Codebase              | Each service in a separate module |
| Explicit Dependencies     | Maven for all declared dependencies |
| Config in Environment     | Spring Cloud Config + environment variables |
| Backing Services          | Redis, Kafka, PostgreSQL via external config |
| Build, Release, Run       | Dockerfile + multi-stage builds |
| Stateless Processes       | Services are stateless, with external persistence |
| Port Binding              | Embedded Netty via WebFlux |
| Concurrency               | Horizontal scaling using containers |
| Dev/Prod Parity           | Identical Docker environments |
| Logs as Event Streams     | Logs to stdout (ELK stack planned) |
| Admin Processes           | CLI tools in separate admin modules |

---

### Microservice Design Patterns

- **Service Discovery:** Eureka
- **API Gateway:** Spring Cloud Gateway
- **Externalized Config:** Spring Cloud Config
- **Distributed Tracing:** Sleuth + Zipkin
- **Log Aggregation:** Planned with ELK Stack
- **Circuit Breakers:** Resilience4j
- **Transactional Outbox Pattern:** Kafka + DB coordination

---

### Project Structure

```
e-learning-platform/
├── config-server/
├── discovery-service/
├── gateway-service/
├── course-service/
├── enrollment-service/
├── feedback-service/
├── aggregate-service/
├── dispatcher-service/
├── config-repository/
└── docker-compose.yml
```

---

### Authentication & Authorization

- **Authentication:** Stateless JWT tokens
- **Authorization:** Role-based (CUSTOMER, EMPLOYEE, ADMIN)
- **Security Layer:** Enforced via API Gateway filters

---

### 📄 License

This project is licensed under the [MIT License](LICENSE).
