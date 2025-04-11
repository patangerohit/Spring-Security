🔐 Spring Boot Security Demo
This is a simple Spring Boot application demonstrating the implementation of JWT-based authentication using Spring Security. 
It includes user login with token generation and secured REST endpoints.

🚀 Features
Spring Boot 3.x
Spring Security
JWT Token-based Authentication
REST API login endpoint
Secure and public endpoints
Custom security filters and exception handling


🛠️ Technologies Used
Java 17+
Spring Boot
Spring Security
JWT (io.jsonwebtoken.Jwts)
Maven


📥 Installation
Clone the repository:

bash
Copy
Edit
git clone https://github.com/patangerohit/Spring-Security.git
cd spring-security-demo
Build the project:

bash
Copy
Edit
mvn clean install
Run the application:

bash
Copy
Edit
mvn spring-boot:run

🔑 API Endpoints
🔐 Login (Generate JWT)
POST /api/auth/login

Request Body:
json
Copy
Edit
{
  "username": "your_username",
  "password": "your_password"
}

Response:
json
Copy
Edit
{
  "token": "jwt-token",
  "type": "Bearer"
}
🔓 Public Endpoint
GET /api/greet/public

Accessible without authentication

🔒 Secured Endpoint
GET /api/greet/secure

Requires valid JWT token in Authorization: Bearer <token> header


🔧 Configuration
You can configure JWT properties in application.properties:
properties
Copy
Edit
app.jwtSecret=YourJwtSecretKey
app.jwtExpirationMs=86400000


📦 Key Classes Overview
Class Name	Description
SecurityConfig.java	Configures security filters, URL permissions, and authentication manager.
AuthEntryPointJwt.java	Returns 401 Unauthorized for invalid requests.
AuthTokenFilter.java	Parses and validates JWT from the Authorization header.
JwtUtils.java	Generates and validates JWT tokens.
LoginRequest.java	Model for login payload.
LoginResponse.java	Model for successful login response.
GreetingsController.java	Contains public and secured REST endpoints.
SecuritydemoApplication.java	Entry point of the Spring Boot application.
