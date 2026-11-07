# API-002 — REST API Authentication Troubleshooting

## 1. Incident Overview

**Incident ID:** API-002  
**Category:** API Authentication  
**Severity:** Low (simulated incident)  
**Status:** Resolved — Test Scenario  
**Tool:** Postman  
**API:** HTTPBin  

## 2. Problem Description

A simulated SaaS customer reports being unable to access an API endpoint.

The API returns HTTP 401 Unauthorized when the request does not include authentication credentials.

The objective is to reproduce the authentication failure, investigate the cause, and verify the expected behavior after adding a Bearer Token.

## 3. Steps to Reproduce

1. Open Postman.
2. Create a GET request.
3. Enter the endpoint:

   `https://httpbin.org/bearer`

4. Select **No Auth** under Authorization.
5. Send the request.

**Observed Result:** HTTP 401 Unauthorized.

## 4. Investigation

The request was repeated using Bearer Token authentication.

**Authentication Type:** Bearer Token  
**Test Token:** demo-support-token-123

The API returned:

**HTTP 200 OK**

Example response:

```json
{
  "authenticated": true,
  "token": "demo-support-token-123"
}
```

HTTPBin accepts any non-empty Bearer Token for this demonstration. It does not validate token expiration, identity, or permissions.

## 5. Automated Testing

Six automated tests were implemented in Postman.

### Scenario A — Missing Authentication

| Test | Result |
|---|---|
| HTTP status is 401 Unauthorized | PASSED |
| Authentication request is rejected | PASSED |
| Response does not contain authenticated user data | PASSED |

### Scenario B — Bearer Token Provided

| Test | Result |
|---|---|
| HTTP status is 200 OK | PASSED |
| Authentication is successful | PASSED |
| Bearer token is correctly received | PASSED |

**Total: 6/6 tests passed.**

## 6. Root Cause Analysis

In the simulated scenario, the HTTP 401 response was caused by the absence of the required Authorization header.

The API endpoint expects the following authentication format:

`Authorization: Bearer <token>`

Without this header, the request is rejected.

## 7. Resolution

The issue was resolved in the test scenario by configuring Bearer Token authentication in Postman.

For a production SaaS environment, additional troubleshooting would include:

1. Verifying that the token is present.
2. Checking token expiration.
3. Confirming that the token was issued by the correct authentication provider.
4. Reviewing API permissions and scopes.
5. Checking application logs and authentication configuration.

## 8. Conclusion

The investigation successfully reproduced an HTTP 401 authentication failure and demonstrated how adding a Bearer Token changes the response to HTTP 200.

Automated Postman tests validated both scenarios.

### Skills Demonstrated

- REST API troubleshooting
- HTTP 401 error analysis
- Bearer Token authentication
- Postman automated testing
- JSON response validation
- Technical incident documentation

**Note:** This is a simulated technical support scenario using a public testing API.
