# Assessment 3 — Pagination + Validating List Content

## Overview
Testing paginated API responses with data validation and consistency checks.

## Test Scenarios

### Page 1
```
GET /products?page=1&limit=10
```

Validations:
- items is an array
- items.length <= 10
- All products have valid id (number, >0)
- All products have valid price (number, >=0)
- Pagination fields correct (page=1, limit=10, total=45)

### Page 2
```
GET /products?page=2&limit=10
```

Validations:
- Page number = 2
- Different products than page 1
- Total remains 45 (consistent)

## Key Features
- Collection-level scripts (shared tests)
- forEach loops for array validation
- Boundary testing
- Data consistency checks

## Pagination Logic
```
Total: 45 items
Limit: 10 per page
Pages: 5 (45 ? 10 = 4.5 > 5)

Page 5 has only 5 items (45 - 40 = 5)
```

## How to Run
1. Import collection and environment
2. Run Page 1 (stores hasNextPage flag)
3. Run Page 2 (checks increment)

## Skills Demonstrated
- Pagination testing
- Array validation (forEach)
- Collection scripts (DRY)
- Query parameters
- Data type validation
- Business logic (price >= 0)

## Tools
- Collection Scripts
- Query Parameters
- Console logging
