# Assessment 1 — Login + Token + Authorized API Flow

## Overview
Complete authentication flow testing including login, token storage, and authorized API requests.

## Test Scenarios

### Positive Tests
1. **Login with valid credentials**
   - POST `/auth/login`
   - Email: test@example.com
   - Password: 123456
   - Expected: 201 Created, token returned

2. **Get current user (with token)**
   - GET `/users/me`
   - Authorization: Bearer token
   - Expected: 200 OK, user data returned

3. **Get orders (with token)**
   - GET `/orders`
   - Authorization: Bearer token
   - Expected: 200 OK, orders array returned

### Negative Tests
1. **Login with wrong password**
   - Expected: 401 Unauthorized
   - Verified error message present

## Key Features
- Token generation on successful login
- Token stored in environment variable
- Token automatically used in subsequent requests
- Response time validation (<1000ms)
- Email format validation
- Negative test for invalid credentials

## How to Run
1. Import Assessment1-Auth.postman_collection.json
2. Import Assessment1-ENV.postman_environment.json
3. Select environment from dropdown
4. Run requests in order

## Skills Demonstrated
- Authentication flow testing
- Bearer token management
- Environment variable usage
- Positive and negative testing
- Response validation
- API chaining

## Tools
- Postman v10.x
- Mock Server
- Collection Scripts
- Environment Variables
