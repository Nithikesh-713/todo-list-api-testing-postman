# To-Do List API Testing Using Postman

## Project Overview
This project demonstrates REST API testing using Postman and the JSONPlaceholder practice API. It covers GET and POST requests, response validation, negative testing, and response-time checks.

**Base URL:** https://jsonplaceholder.typicode.com

**Tool:** Postman  
**API Type:** REST API  
**Testing Types:** Functional testing, negative testing, response validation, and basic performance testing

## Test Cases and Results

| Test Case ID | Test Scenario | Result |
|---|---|---|
| TC01 | Retrieve a To-Do by ID using GET | Passed — 4 assertions |
| TC02 | Create a To-Do using POST | Passed — 4 assertions |
| TC03 | POST request with missing title | Failed — API returned 201 |
| TC04 | POST request with invalid user ID | Failed — API returned 201 |
| TC05 | POST request with missing user ID | Failed — API returned 201 |
| TC06 | POST request with invalid `completed` field type | Failed — API returned 201 |
| TC07 | Verify required response fields | Passed — 4 assertions |
| TC08 | Verify response data types | Passed — 4 assertions |
| TC09 | Verify response status code | Passed — 1 assertion |
| TC10 | Verify response time is below 3000 ms | Passed — 1 assertion |

## Key Findings
- The GET request successfully retrieved To-Do ID 1 and returned `200 OK`.
- Valid POST requests returned `201 Created`.
- The response was validated for required fields and expected data types.
- The API accepted several invalid payloads and returned `201 Created`.
- The response-time assertion passed for the observed request.

## Sample GET Request

**Method:** GET

**Endpoint:** `https://jsonplaceholder.typicode.com/todos/1`

### Validations
- Status code is `200 OK`.
- Response contains a task title.
- Task ID equals `1`.
- The `completed` field is a Boolean.

## Sample POST Request

**Method:** POST

**Endpoint:** `https://jsonplaceholder.typicode.com/todos`

### Request Body

```json
{
  "userId": 1,
  "title": "Complete API Testing",
  "completed": false
}
```

## Skills Demonstrated
- REST API testing
- Postman request configuration
- JavaScript test scripts in Postman
- HTTP status-code validation
- JSON response validation
- Positive and negative testing
- Data-type validation
- Basic response-time testing
- Test-case documentation

## Tools and Technologies
- Postman
- JSONPlaceholder REST API
- JavaScript
- JSON
- GitHub

## Disclaimer
This is a learning project using JSONPlaceholder, a simulated REST API. POST requests simulate creation and do not permanently create records on a real backend. The failed validation assertions reflect the observed behavior of this practice API and do not, by themselves, establish defects in a production system.

