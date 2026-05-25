# AI-Powered Fitness Application (Microservices Architecture)

Welcome to the **AI-Powered Fitness Application**, a production-ready, full-stack enterprise platform built using a modern decoupled microservices architecture. This project showcases how to design, secure, scale, and orchestrate multiple independent services that communicate seamlessly to deliver intelligent fitness insights.

---

## 🚀 Key Highlights
* **Decoupled Microservices Architecture:** Independent services handling distinct business capabilities.
* **AI-Driven Personalization:** Seamless integration with GenAI to provide intelligent fitness, workout, and nutritional tracking.
* **Production-Grade Security & Messaging:** Secure token-based authentication and reliable asynchronous event-driven communication.

---

## 🛠️ Tech Stack & Ecosystem

### **Frontend**
* **React:** Component-based UI for a dynamic, smooth, and responsive user experience.

### **Backend Frameworks & Tools**
* **Spring Boot:** Core framework used to rapidly build resilient, standalone microservices.
* **Java 23:** Leveraging modern Java compilation and language features for high performance.
* **Maven:** Project management and comprehensive dependency automation.

### **Spring Cloud & Service Orchestration**
* **Spring Cloud Config Server:** Centralized external configuration management across all environments (Development, QA, Production).
* **Eureka Server (Spring Cloud Netflix):** Dynamic service registration and service discovery, allowing microservices to locate and talk to each other without hardcoded URLs.
* **Spring Cloud Gateway:** A single, unified entry point for routing client requests to backend services, handling cross-cutting concerns like global logging, rate limiting, and security filters.

### **Security & Identity Management**
* **Keycloak:** Centralized OpenID Connect (OIDC) and OAuth2 identity provider handling user registration, authentication, and Role-Based Access Control (RBAC) securely.

### **Data & Messaging Layer**
* **RabbitMQ (Spring AMQP):** Message broker managing asynchronous, event-driven communication between services to guarantee loose coupling and high reliability.
* **PostgreSQL / MySQL:** Robust relational databases handling relational persistence per microservice (Database-per-Service pattern).

### **Artificial Intelligence**
* **Google Gemini API:** Powering the core intelligent engine of the app, generating tailored workout plans, tracking progress patterns, and providing instant AI fitness coaching.

---

## 📂 Microservices Directory
* `configserver` — Manages centralized external properties.
* `eureka` — Coordinates service registry and active lookup tables.
* `gateway` — Acts as the reverse proxy, security firewall, and request router.
* `userservice` — Manages user profiles, credentials, and onboarding data.
* `activityservice` — Tracks workouts, daily metrics, and fitness logs.
* `aiservice` — Connects with Google Gemini API to analyze metrics and deliver personalized suggestions.
* `fitness-app-frontend` — The client-side React user interface.

---

## ⚙️ Recommended Startup Sequence
To run this distributed architecture locally, start the services in the following order to honor dependencies:
1. **Infrastructure Backbones:** Spin up **Keycloak**, **RabbitMQ**, and your relational databases.
2. **Central Configuration:** Start the `configserver` and ensure configurations load smoothly.
3. **Service Directory:** Run the `eureka` server (`http://localhost:8761`).
4. **API Routing Gateway:** Run the `gateway` microservice.
5. **Business Services:** Boot up `userservice`, `activityservice`, and `aiservice` in any order. They will auto-register with Eureka.
6. **User Interface:** Run the React `fitness-app-frontend`.
