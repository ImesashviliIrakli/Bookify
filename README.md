# Bookify 📚🏠  

Bookify is a .NET 8-based application designed for booking apartments. It follows best practices like **Clean Architecture**, **Domain-Driven Design (DDD)**, **CQRS**, and **Outbox Patterns** for domain events.
Bookify ensures efficient error handling using **Result patterns**, avoiding exceptions for control flow.  

The project is containerized using **Docker**, providing seamless setup for dependencies such as PostgreSQL, Redis, Keycloack for authentication and Seq for logging.  

---

## 📁 Project Structure

The application is organized into the following layers to maintain separation of concerns:  

1. **Domain Layer**  
   - Contains core business logic, entities, value objects, and domain events.
   - The heart of the application with no dependencies on other layers.

2. **Application Layer**  
   - Includes use cases, commands, queries, and services.
   - Implements **CQRS** for segregating read and write operations.
   - Handles mapping between DTOs and domain models.

3. **Infrastructure Layer**  
   - Provides implementations for database access, external APIs, and logging.
   - Uses PostgreSQL as the primary data store and Redis for caching.
   - Implements the **Outbox pattern** to ensure reliability for domain event propagation.

4. **API Layer**  
   - Exposes RESTful endpoints for external communication.
   - Built with ASP.NET Core Minimal APIs.
   - Configures dependency injection and middleware for validation, logging, and authentication.

---

## 🚀 Features  

- **Clean Architecture**: Decouples core business logic from implementation details.  
- **Domain-Driven Design (DDD)**: Focused on modeling the domain with rich, expressive domain entities and events.  
- **CQRS**: Separates commands and queries for performance and maintainability.  
- **Outbox Pattern**: Ensures reliable event propagation across the system.  
- **Result Patterns**: Handles errors gracefully without exceptions, improving performance and readability.  
- **Containerized Setup**: Dockerized environment for PostgreSQL, Redis, Seq, and the API.  

---

## 🛠️ Prerequisites  

Before running the application, ensure you have the following installed:  

- **Docker** (for containerized setup)  
- **.NET 8 SDK**  
- **PostgreSQL** (used internally, but Dockerized)  

---

## 🐳 Running the Application  

### 1. Clone the Repository  

```bash  
git clone https://github.com/yourusername/bookify.git  
cd bookify  
```
### 2. Start the Docker Environment  

Run the following command to start the Docker containers:  

```bash
docker-compose up -d
```
The migrations are already in place and update will execute once you run the app.

### 3. Open docker desktop

After you created the containers, you can open docker desktop and see the ports for each container.

## 📊 Logging
Seq is used for centralized logging and can be accessed at http://localhost:5341.
- Logs include structured information about requests, domain events, and errors.

## ⚡ Technologies
- Framework: .NET 8
- Authentication: KeyCloack
- Database: PostgreSQL (via EF Core)
- Caching: Redis
- Logging: Seq
- Containerization: Docker & Docker Compose

## 🔧 Configuration
The app is entirely designed for local use, so all the necessary configs is in appsettings.Development.json

## 🤝 Contributing
Contributions are welcome! Feel free to:
- Fork the repository.
- Create a feature branch.
- Submit a pull request.
