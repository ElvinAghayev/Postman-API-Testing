# Assessment 4 — Bug Hunt: Status Code & Error Structure

## Overview
Negative testing to identify incorrect status codes and inconsistent error structures.

## Bugs Found

### BUG-001: Login Returns 200 Instead of 400
**Severity:** High

**Issue:** Login with missing password returns 200 OK, should return 400 Bad Request

**Impact:**
- Frontend interprets 200 as success
- User sees success message despite failed login

### BUG-002: Inconsistent Error Structure
**Severity:** Medium

**Issue:** Different endpoints use different error field names
- /auth/login uses: success, reason
- /users uses: errorMessage, details, code

**Impact:**
- Frontend must handle multiple error formats
- Increased code complexity

## Test Scenarios

### 1. Login Missing Password
```json
POST /auth/login
{
    "email": "test@example.com"
}
```
Expected: 400 | Actual: 200 (BUG)

### 2. Invalid Email
```json
POST /users
{
    "name": "Test",
    "email": "not-an-email"
}
```
Expected: 422 with standard fields | Actual: 422 but inconsistent fields (BUG)

## How to Run
1. Import collection and environment
2. Run 01 - Login Missing Password
3. Run 02 - Create User Invalid Email
4. Check Bug Reports folder for detailed documentation

## Files
- collection.json
- environment.json
- screenshots/ (test results)
- bug-reports/ (detailed bug documentation)

## Skills Demonstrated
- Negative testing
- Bug identification
- Detailed bug reporting
- Status code validation
- Console debugging

## Tools
- Postman Console
- Pre-request Scripts
- Test Assertions
