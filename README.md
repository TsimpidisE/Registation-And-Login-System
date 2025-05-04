# Registration and Login System

A Spring Boot application that provides secure user registration, authentication, and authorization using JWT. Demonstrates key Spring Boot features including Spring Security, Spring Data JPA, validation, and exception handling.

## Table of Contents
- [Features](#features)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

## Features
- User registration with form validation
- Secure login with JWT-based authentication
- Role-based authorization (e.g., USER, ADMIN)
- Password hashing with BCrypt
- Global exception handling and meaningful error responses

## Project Structure

```
Registration-And-Login-System/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/tsimpidise/rls/
│   │   │       ├── config/           # Security and Swagger configuration
│   │   │       ├── controller/       # REST controllers (AuthController, UserController)
│   │   │       ├── dto/              # Data Transfer Objects for requests/responses
│   │   │       ├── exception/        # Custom exceptions and global exception handlers
│   │   │       ├── model/            # JPA entities (User, Role)
│   │   │       ├── repository/       # Spring Data JPA repositories
│   │   │       ├── security/         # JWT utilities and filters
│   │   │       └── service/          # Business logic and user management
│   │   └── resources/
│   │       ├── application.properties  # DB configs, JWT secret, app settings
│   │       └── data.sql                # Sample seed data (roles, test users)
│   └── test/
│       └── java/
│           └── com/tsimpidise/rls/      # Unit and integration tests
├── mvnw                                  # Maven wrapper
├── pom.xml                               # Maven build and dependencies
└── README.md                             # Project documentation
```

## Prerequisites
- Java 8 or higher
- Maven 3.6+
- (Optional) MySQL database if switching from default H2

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/TsimpidisE/Registation-And-Login-System.git
   cd Registation-And-Login-System
   ```
2. Build the project:
   ```bash
   ./mvnw clean install
   ```

## Configuration
Update `src/main/resources/application.properties` for database and JWT:
```properties
spring.datasource.url=jdbc:h2:mem:rls_db
spring.datasource.username=sa
spring.datasource.password=
# JWT config
auth.jwt.secret=<your-secret-key>
auth.jwt.expirationMs=3600000
``` 

## Usage
Run the application:
```bash
./mvnw spring-boot:run
```
The API is available at `http://localhost:8080/api`.

## API Endpoints
| Method | Endpoint                | Description                         |
| ------ | ----------------------- | ----------------------------------- |
| POST   | /api/auth/signup        | Register a new user                 |
| POST   | /api/auth/signin        | Authenticate user and get JWT       |
| GET    | /api/users/me           | Get current user profile (secured)  |
| GET    | /api/users              | List all users (ADMIN only)         |

## Contributing
Contributions are welcome! Fork the repo, create a feature branch, and submit a pull request.

## License
This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Author
Efthymios Tsimpidis  
GitHub: https://github.com/TsimpidisE
