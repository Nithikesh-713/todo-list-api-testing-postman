# To-Do List API Testing Using Postman

## Project Overview
This project demonstrates REST API testing using Postman and the JSONPlaceholder practice API. It covers GET and POST requests, response validation, negative testing, and response-time checks.

**Base URL:** https://jsonplaceholder.typicode.com

**Tool:** Postman  
**API Type:** REST API  
**Testing Type:** Functional, negative, response validation, and basic performance testing

## Test Cases

| Test Case ID | Test Scenario | Result |
|---|---|---|
| TC01 | Retrieve a To-Do by ID using GET | Previously tested |
| TC02 | Create a To-Do using POST | Passed |
| TC03 | POST request with missing title | Failed — API returned 201 |
| TC04 | POST request with invalid user ID | Failed — API returned 201 |
| TC05 | POST request with missing user ID | Failed — API returned 201 |
| TC06 | POST request with invalid `completed` field type | Failed — API returned 201 |
| TC07 | Verify required response fields | Passed |
| TC08 | Verify response data types | Passed |
| TC09 | Verify response status code | Passed |
| TC10 | Verify response time is below 3000 ms | Passed |

*Results are based on the observed responses during testing. TC01's final result should be confirmed before publishing.*

## Key Findings
- Valid POST requests returned `201 Created`.
- The response was checked for required fields and expected data types.
- The API accepted several invalid payloads and returned `201 Created`.
- The response-time assertion passed for the observed request.
- JSONPlaceholder is a simulated practice API; POST requests do not permanently create records on a real backend.

## Sample Request

**Method:** POST

**Endpoint:** `https://jsonplaceholder.typicode.com/todos`

```json
{
  "userId": 1,
  "title": "Complete API Testing",
  "completed": false
}
```

## Skills Demonstrated
- REST API testing
- Postman requests and test scripts
- HTTP status-code validation
- JSON response validation
- Positive and negative testing
- Data-type validation
- Basic response-time testing
- Test-case documentation

## Disclaimer
This is a learning project using JSONPlaceholder, a simulated REST API. Results reflect the behavior observed during testing and should not be interpreted as evidence of defects in a production API.
