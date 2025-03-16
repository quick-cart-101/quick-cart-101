# Quick Cart 🛒

## Overview
**Quick Cart** is an e-commerce platform built using a **microservices architecture** with **Spring Boot**. Each microservice handles a specific functionality, ensuring scalability and modularity. The platform includes services for user authentication, order management, payment processing, and product management, all connected through an API Gateway.

---

## Microservices

### 1. AuthService
- **Description**: Handles user authentication and authorization using **Spring Security**. It manages user registration, login, and JWT token generation and validation. The service uses **MySQL** as the database for storing user credentials and related data.
- **GitHub URL**: [AuthService](https://github.com/quick-cart-101/AuthService)

---

### 2. PaymentService
- **Description**: Manages payment processing using **Razorpay**. It allows users to create payments, handle payment status, and process refunds.
- **GitHub URL**: [PaymentService](https://github.com/quick-cart-101/PaymentService.git)

---

### 3. OrderService
- **Description**: Manages customer orders. It handles order creation, tracking, and status updates.
- **GitHub URL**: [OrderService](https://github.com/quick-cart-101/OrderService.git)

---

### 4. ProductService
- **Description**: Handles product catalog management, including adding, updating, and deleting products.
- **GitHub URL**: [ProductService](https://github.com/quick-cart-101/ProductService.git)

---

### 5. API Gateway
- **Description**: Serves as a single entry point for all microservices. It routes requests to the appropriate services and handles cross-cutting concerns like authentication and rate limiting.
- **GitHub URL**: [API Gateway](https://github.com/quick-cart-101/api-gateway.git)

---

### 6. Eureka Server
- **Description**: Service discovery server that allows all microservices to register and discover each other.
- **GitHub URL**: [Eureka Server](https://github.com/quick-cart-101/eureka-server.git)

---

## Architecture Diagram
```text
                       +----------------------+
                       |      API Gateway      |
                       +----------------------+
                                  |
       ------------------------------------------------------
      |                |                   |                |
+------------+   +------------+    +-------------+   +------------+
| AuthService |   | OrderService |    | PaymentService |   | ProductService |
+------------+   +------------+    +-------------+   +------------+
                                  |
                           +----------------+
                           |  Eureka Server  |
                           +----------------+
