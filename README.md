# REST API Support & Troubleshooting Toolkit

A hands-on technical portfolio project demonstrating REST API testing, HTTP troubleshooting, authentication fundamentals, and incident documentation using Postman.

## Project Objective

This project simulates common technical support scenarios encountered in SaaS environments.

The goal is to develop practical skills in API troubleshooting, response validation, and structured incident investigation.

## Technologies & Tools

- **Postman** — API requests and automated testing
- **REST APIs** — HTTP methods, endpoints, and responses
- **JavaScript** — Postman test scripts
- **JSON** — API response analysis
- **GitHub** — Version control and technical documentation
- **Ubuntu Linux** — Development environment

## Implemented API Scenarios

| Scenario | HTTP Status | Description |
|---|---|---|
| Retrieve User Details | 200 OK | Validate successful user data retrieval |
| User Not Found | 404 Not Found | Investigate a missing resource |
| Bearer Token Authentication | 200 OK | Validate authentication header handling |
| Missing Authentication | 401 Unauthorized | Reproduce an authentication failure |

## Automated API Tests

The Postman collection includes 12 automated assertions across four API scenarios.

Tests cover:

- HTTP status code validation
- JSON response validation
- User ID verification
- Response field verification
- Bearer Token handling
- Missing authentication scenarios

## Repository Structure

```text
rest-api-support-toolkit/
├── README.md
├── postman/
│   └── REST-API-Support-Toolkit.postman_collection.json
└── incidents/
    ├── API-001-user-not-found.md
    └── API-002-authentication-troubleshooting.md
```

## How to Run the Tests

1. Install Postman.
2. Download the collection JSON file from the `postman` directory.
3. Import the collection into Postman.
4. Open the individual API requests.
5. Configure a demo Bearer Token where required.
6. Click **Send** to execute each request.
7. Review the automated test results.

The project uses publicly available demonstration APIs:

- JSONPlaceholder
- HTTPBin

No production credentials or customer data are required.

## Incident Documentation

### API-001 — HTTP 404 User Not Found

Simulated investigation of an API request targeting a non-existent user.

The incident report documents reproduction steps, response analysis, automated tests, and recommended troubleshooting actions.

### API-002 — HTTP 401 Authentication Failure

Simulated investigation of an API request rejected due to missing authentication credentials.

The report demonstrates Bearer Token configuration and the validation of authenticated and unauthenticated requests.

## Professional Skills Demonstrated

- REST API testing and troubleshooting
- HTTP error investigation
- API authentication fundamentals
- Postman automated testing
- Technical incident documentation
- Structured problem-solving
- GitHub project documentation

## Planned Improvements

- POST, PUT, PATCH, and DELETE requests
- HTTP 400 and 403 troubleshooting scenarios
- API environment variables
- Additional automated validation tests
- API troubleshooting documentation
- Test execution using Newman

## Author

**Oscar Canseco**

Technical portfolio fto build a decent profile on SaaS Technical Support, Application Support, and API Troubleshooting.

---

*This is a learning and demonstration project using public testing APIs. All incidents are simulated.*
