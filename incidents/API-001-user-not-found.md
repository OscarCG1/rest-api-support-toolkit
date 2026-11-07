# API-001 — User Not Found (HTTP 404)

## 1. Incident Overview

**Incident ID:** API-001  
**Category:** REST API Troubleshooting  
**Severity:** Low (simulated incident)  
**Status:** Resolved — Test scenario  
**Tool:** Postman  
**API:** JSONPlaceholder  

## 2. Problem Description

A simulated customer reports being unable to retrieve user information through a REST API.

The API returns HTTP 404 Not Found when requesting a specific user ID.

The objective of this investigation is to reproduce the error, validate the API response, and identify the likely cause.

## 3. Steps to Reproduce

1. Open Postman.
2. Create a GET request.
3. Enter the following endpoint:

   `https://jsonplaceholder.typicode.com/users/99999`

4. Send the request.
5. Inspect the HTTP status code and response body.

## 4. Actual Results

**HTTP Status:** 404 Not Found

**Response Body:**

```json
{}
```

The API does not return a user record for the requested ID.

## 5. Automated Tests

Three automated Postman tests were executed:

| Test | Result |
|---|---|
| HTTP status equals 404 | PASSED |
| Response is valid JSON | PASSED |
| Response body is an empty object | PASSED |

**Total: 3/3 tests passed.**

## 6. Root Cause Analysis

The requested user ID (99999) does not correspond to an available user record in the test API.

The endpoint responds with HTTP 404, indicating that the requested resource was not found.

This is expected behavior for the simulated scenario rather than evidence of a server malfunction.

## 7. Resolution

The following actions are recommended:

1. Verify that the requested user ID is correct.
2. Confirm that the user exists in the system.
3. Validate the API endpoint.
4. Retry the request using a known valid user ID.
5. Escalate the issue if a valid, accessible user continues to return an unexpected 404 response.

## 8. Conclusion

The investigation successfully reproduced and validated an HTTP 404 response using Postman.

Automated tests confirmed that the API returned the expected status code and response structure for a non-existent user.

**Skills demonstrated:**
- REST API troubleshooting
- HTTP status code analysis
- Postman API testing
- JSON response validation
- Technical incident documentation
