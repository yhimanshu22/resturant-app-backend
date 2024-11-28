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

Get User Information
```
curl -X GET http://localhost:5000/api/v1/user \
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY3NDg3NmE0ZjE2ZjZjOWVlOTcxZGRkNCIsImlhdCI6MTczMjgwMjIxMywiZXhwIjoxNzMyODg4NjEzfQ.lryjNKsO4JVRGwZaH7j7dJz1IzSBt_7DlC_yxyJjfMs" \
-H "Content-Type: application/json" \
-d '{
  "id": "<user_id>"
}'

```

upadate  user info
```
curl -X PUT http://localhost:5000/api/v1/user \
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY3NDg3NmE0ZjE2ZjZjOWVlOTcxZGRkNCIsImlhdCI6MTczMjgwMjIxMywiZXhwIjoxNzMyODg4NjEzfQ.lryjNKsO4JVRGwZaH7j7dJz1IzSBt_7DlC_yxyJjfMs" \
-H "Content-Type: application/json" \
-d '{
  "id": "<user_id>",
  "userName": "updatedUserName",
  "address": "456 Updated St",
  "phone": "0987654321"
}'
```

update user password 
```
curl -X PUT http://localhost:5000/api/v1/user/password \
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY3NDg3NmE0ZjE2ZjZjOWVlOTcxZGRkNCIsImlhdCI6MTczMjgwMjIxMywiZXhwIjoxNzMyODg4NjEzfQ.lryjNKsO4JVRGwZaH7j7dJz1IzSBt_7DlC_yxyJjfMs" \
-H "Content-Type: application/json" \
-d '{
  "id": "<user_id>",
  "oldPassword": "oldPassword123",
  "newPassword": "newPassword123"
}'
```

reset user password
```
curl -X POST http://localhost:5000/api/v1/user/reset-password \
-H "Content-Type: application/json" \
-d '{
  "email": "test@example.com",
  "newPassword": "newPassword123",
  "answer": "Test answer"
}'
```

delete user password
```
curl -X DELETE http://localhost:5000/api/v1/user/<user_id> \
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY3NDg3NmE0ZjE2ZjZjOWVlOTcxZGRkNCIsImlhdCI6MTczMjgwMjIxMywiZXhwIjoxNzMyODg4NjEzfQ.lryjNKsO4JVRGwZaH7j7dJz1IzSBt_7DlC_yxyJjfMs"
```

delete user profile
```
curl -X DELETE http://localhost:5000/api/v1/user/<user_id> \
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY3NDg3NmE0ZjE2ZjZjOWVlOTcxZGRkNCIsImlhdCI6MTczMjgwMjIxMywiZXhwIjoxNzMyODg4NjEzfQ.lryjNKsO4JVRGwZaH7j7dJz1IzSBt_7DlC_yxyJjfMs"
```

admin user register
```
curl -X POST http://localhost:5000/api/v1/auth/register \
-H "Content-Type: application/json" \
-d '{
  "userName": "adminUser",
  "email": "admin@example.com",
  "password": "adminPassword123",
  "phone": "1234567890",
  "address": ["123 Admin St"],
  "answer": "Admin answer",
  "usertype": "admin"
}'
```

admin login
```
curl -X POST http://localhost:5000/api/v1/auth/login \
-H "Content-Type: application/json" \
-d '{
  "email": "admin@example.com",
  "password": "adminPassword123"
}'
```
get user
```
curl -X GET http://localhost:5000/api/v1/user/getUser \
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY3NDg3YTVkZjE2ZjZjOWVlOTcxZGRkOCIsImlhdCI6MTczMjgwMzIxOCwiZXhwIjoxNzMyODg5NjE4fQ.g-IfGKooswRfweeyJ4G1fzKuWL-1oKLH8VFWdFrf1j8" \
-H "Content-Type: application/json" \
-d '{
  "id": "67487a5df16f6c9ee971ddd8"
}'
```

upadate user
```
curl -X PUT http://localhost:5000/api/v1/user/updateUser \
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY3NDg3YTVkZjE2ZjZjOWVlOTcxZGRkOCIsImlhdCI6MTczMjgwMzIxOCwiZXhwIjoxNzMyODg5NjE4fQ.g-IfGKooswRfweeyJ4G1fzKuWL-1oKLH8VFWdFrf1j8" \
-H "Content-Type: application/json" \
-d '{
  "id": "67487a5df16f6c9ee971ddd8",
  "userName": "updatedAdminUser",
  "address": ["456 Updated St"],
  "phone": "0987654321"
}'

```

update user password
```
curl -X POST http://localhost:5000/api/v1/user/updatePassword \
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY3NDg3YTVkZjE2ZjZjOWVlOTcxZGRkOCIsImlhdCI6MTczMjgwMzIxOCwiZXhwIjoxNzMyODg5NjE4fQ.g-IfGKooswRfweeyJ4G1fzKuWL-1oKLH8VFWdFrf1j8" \
-H "Content-Type: application/json" \
-d '{
  "id": "67487a5df16f6c9ee971ddd8",
  "oldPassword": "adminPassword123",
  "newPassword": "newAdminPassword123"
}'
```
reset user password 
```
curl -X POST http://localhost:5000/api/v1/user/resetPassword \
-H "Content-Type: application/json" \
-d '{
  "email": "admin@example.com",
  "newPassword": "newPassword123",
  "answer": "Admin answer"
}'
```

delete user profile
```
curl -X POST http://localhost:5000/api/v1/user/resetPassword \
-H "Content-Type: application/json" \
-d '{
  "email": "admin@example.com",
  "newPassword": "newPassword123",
  "answer": "Admin answer"
}'
```






   
