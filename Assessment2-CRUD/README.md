# Assessment 2 — Create User Then Verify With GET

## Overview
CRUD operations testing with user creation, retrieval, deletion, and verification.

## Test Flow
```
Create User > Get User > Delete User > Verify Deleted (404)
```

## Test Scenarios

### 1. Create User
- POST /users
- Generates unique email using timestamp
- Stores user ID
- Validates: 201 status, valid ID, email format

### 2. Get User By ID
- GET /users/:id
- Uses stored ID
- Validates: ID matches, email contains @

### 3. Delete User
- DELETE /users/:id
- Validates: 204 No Content, empty body

### 4. Get Deleted User
- GET /users/:id
- Validates: 404 Not Found

## Key Features
- Unique email generation (timestamp-based)
- ID persistence across requests
- Full CRUD workflow
- Status code validation (201, 200, 204, 404)
- Email format validation (regex)

## How to Run
1. Import collection and environment
2. Select environment
3. Run requests IN SEQUENCE (order matters)

## Skills Demonstrated
- Full CRUD testing
- Request chaining
- Variable management
- Status code testing
- Negative testing
- Email validation

## Tools
- Collection Variables
- Pre-request Scripts
- Test Assertions
