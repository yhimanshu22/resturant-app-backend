# Food Server App API

Welcome to the Food Server App API! This API allows users to register and log in to the application. Below are the details on how to use the authentication endpoints.

## Table of Contents
- [Installation](#installation)
- [API Endpoints](#api-endpoints)
  - [Register a New User](#register-a-new-user)
  - [Login an Existing User](#login-an-existing-user)

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```

2. Navigate to the project directory:
   ```bash
   cd <project-directory>
   ```

3. Install the required dependencies:
   ```bash
   npm install
   ```

4. Set up your environment variables in a `.env` file:
   ```
   JWT_SECRET=<your_jwt_secret>
   PORT=5000
   ```

5. Start the server:
   ```bash
   npm start
   ```

## API Endpoints

### Register a New User

To register a new user, send a POST request to the `/api/v1/auth/register` endpoint with the following JSON body:
   ```
   curl -X POST http://localhost:5000/api/v1/auth/register \
-H "Content-Type: application/json" \
-d '{
"userName": "testUser",
"email": "test@example.com",
"password": "password123",
"phone": "1234567890",
"address": "123 Test St",
"answer": "Test answer"
}'
   ```

### Login an Existing User

To log in an existing user, send a POST request to the `/api/v1/auth/login` endpoint with the following JSON body:

```bash
curl -X POST http://localhost:5000/api/v1/auth/login \
-H "Content-Type: application/json" \
-d '{
  "email": "test@example.com",
  "password": "password123"
}'
```

   
