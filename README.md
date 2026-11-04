# User Management API Testing with Postman

A hands-on REST API testing project using Postman and DummyJSON.

This project focuses on testing user management API endpoints through CRUD operations, positive and negative test scenarios, response validation, and automated test execution.

## Tools & Technologies

- **Postman:** API requests and automated testing
- **JavaScript:** Writing test assertions
- **DummyJSON:** Practice REST API
- **Git & GitHub:** Project version control and documentation

  ## API Operations Tested

| HTTP Method | Endpoint | Purpose |
|---|---|---|
| GET | `/users` | Retrieve all users |
| GET | `/users/1` | Retrieve a single user |
| GET | `/users/9999` | Test a non-existing user |
| POST | `/users/add` | Create a new user |
| PUT | `/users/1` | Update user information |
| PATCH | `/users/1` | Update selected user fields |
| DELETE | `/users/1` | Simulate user deletion |

## Testing Scenarios

- Verify successful retrieval of all users.
- Verify retrieval of a user by ID.
- Verify appropriate error response for a non-existing user.
- Verify successful user creation.
- Verify required fields in the creation response.
- Verify user information updates using PUT.
- Verify partial updates using PATCH.
- Verify simulated user deletion using DELETE.
- Validate HTTP status codes and response body fields.
- Execute automated assertions using Postman.

  ## Test Execution Results

- **Total assertions:** 19
- **Passed:** 19
- **Failed:** 0
- **Execution type:** Functional
- **Iterations:** 1
- **Tool:** Postman Collection Runner

  ## API Limitations and Observations

- DummyJSON is a practice API that simulates data operations.
- POST, PUT, PATCH, and DELETE responses do not guarantee permanent database changes.
- A successful creation response (201) does not necessarily mean the new user can be retrieved later.
- The API returned a not-found message when checking the simulated newly created user.
- API responses were validated using Postman test scripts.
