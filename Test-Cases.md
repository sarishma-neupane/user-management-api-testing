# API Test Cases – User Management

**Project:** User Management API Testing  
**Tool:** Postman  
**Base URL:** `https://dummyjson.com`

## Test Case Summary

| Test Case ID | Scenario | Method | Expected Status | Actual Status | Result |
|---|---|---|---|---|---|
| TC_001 | Retrieve all users | GET | 200 | 200 | PASS |
| TC_002 | Retrieve a single user | GET | 200 | 200 | PASS |
| TC_003 | Retrieve a non-existing user | GET | 404 | 404 | PASS |
| TC_004 | Create a new user | POST | 201 | 201 | PASS |
| TC_005 | Verify simulated created user | GET | 400 | 400 | PASS |
| TC_006 | Update user using PUT | PUT | 200 | 200 | PASS |
| TC_007 | Update selected field using PATCH | PATCH | 200 | 200 | PASS |
| TC_008 | Delete a user | DELETE | 200 | 200 | PASS |

## Detailed Test Cases

### TC_001: Retrieve All Users
- **Endpoint:** `/users`
- **Precondition:** API is accessible.
- **Test Steps:**
  1. Send a GET request to `/users`.
  2. Verify the response status code.
  3. Validate the users array and first user's details.
- **Expected Result:** Status 200 and valid user data.
- **Actual Result:** Status 200; users array returned.
- **Result:** PASS

### TC_002: Retrieve a Single User
- **Endpoint:** `/users/1`
- **Test Steps:**
  1. Send a GET request to `/users/1`.
  2. Verify user ID, name, and email.
- **Expected Result:** Status 200 with correct user details.
- **Actual Result:** Status 200; user details matched.
- **Result:** PASS

### TC_003: Retrieve a Non-Existing User
- **Endpoint:** `/users/9999`
- **Test Steps:**
  1. Send a GET request to `/users/9999`.
  2. Verify the error status and message.
- **Expected Result:** Status 404 with an error message.
- **Actual Result:** Status 404 with an error message.
- **Result:** PASS

### TC_004: Create a New User
- **Endpoint:** `/users/add`
- **Test Steps:**
  1. Send a POST request with user details.
  2. Validate the generated ID, name, and age.
- **Expected Result:** Status 201 and created-user response.
- **Actual Result:** Status 201; response fields matched.
- **Result:** PASS

### TC_005: Verify Simulated Created User
- **Endpoint:** `/users/209`
- **Test Steps:**
  1. Send a GET request using the generated user ID.
  2. Verify the response message.
- **Expected Result:** The simulated created user is not permanently stored.
- **Actual Result:** Status 400 with a user-not-found message.
- **Result:** PASS

### TC_006: Update User Using PUT
- **Endpoint:** `/users/1`
- **Test Steps:**
  1. Send a PUT request with updated user details.
  2. Validate the returned fields.
- **Expected Result:** Status 200 with updated user information.
- **Actual Result:** Status 200; updated fields were returned.
- **Result:** PASS

### TC_007: Update Selected Field Using PATCH
- **Endpoint:** `/users/1`
- **Test Steps:**
  1. Send a PATCH request with the age field.
  2. Validate the updated age.
  3. Check that other user fields remain unchanged in the response.
- **Expected Result:** Status 200 with age updated to 24.
- **Actual Result:** Status 200; age changed to 24.
- **Result:** PASS

### TC_008: Delete a User
- **Endpoint:** `/users/1`
- **Test Steps:**
  1. Send a DELETE request.
  2. Validate the deletion status and timestamp.
- **Expected Result:** Status 200 with `isDeleted: true` and a deletion timestamp.
- **Actual Result:** Status 200; deletion fields were returned.
- **Result:** PASS

## Execution Summary

- Total test cases documented: 8
- Passed: 8
- Failed: 0
- Testing tool: Postman
- API: DummyJSON

**Note:** DummyJSON is a practice API. Write operations are simulated and do not guarantee permanent database changes. The test results reflect the responses observed during execution.
