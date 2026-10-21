To-Do List API Testing with Postman
Project Overview
Beginner REST API testing project using Postman and the JSONPlaceholder
simulated API. The collection covers GET/POST requests, response
assertions, negative scenarios, response fields and data types, status
codes, and response-time checks.
Tools and API
- Tool: Postman
- Base URL: https://jsonplaceholder.typicode.com
- Resource: /todos
- API type: Simulated / placeholder REST API
Test Summary
  Metric                           Result
  Total test cases                     10
  Passed test cases (reported)          6
  Failed test cases (reported)          4
  Passed assertions reported           18
The uploaded JSON is a Postman collection containing requests and test
scripts, not a saved execution report. Outcomes below are based on
results reported earlier in the conversation.

Test Cases
  ID             Scenario       Method         Expected       Reported
                                                              result
  TC01           Retrieve To-Do GET /todos/1 200; title     Passed --- 4
                 by ID                         string; ID 1;  assertions
                                               completed
                                               Boolean        

  TC02           Create valid   POST /todos  201 and        Passed --- 4
                 To-Do                         response       assertions
                                               fields
                                               validated      

  TC03           Missing title  POST /todos  400 or 422     Failed --- API
                                                              returned 201

  TC04           Invalid userId POST /todos  400, 404 or    Failed --- API
                 (-1)                          422            returned 201

  TC05           Missing userId Intended POST  400 or 422     Failed --- API
                                /todos                      returned 201
                                                              (reported);
                                                              method needs
                                                              correction

  TC06           Invalid        POST /todos  400 or 422     Failed --- API
                 completed type                               returned 201
                                                              (reported);
                                                              body key needs
                                                              correction

  TC07           Required       POST /todos  userId, id,    Passed --- 4
                 response                      title,         assertions
                 fields                        completed
                                               present        

  TC08           Response data  POST /todos  Numeric IDs,   Passed --- 4
                 types                         string title,  assertions
                                               Boolean
                                               completed      

  TC09           Status code    POST /todos  201 Created    Passed --- 1
                                                              assertion

  TC10           Response time  POST /todos  Below 3000 ms  Passed --- 1
                                                              assertion;
                                                              exact time not
                                                          supplied
Collection Review --- Fix Before Rerunning
1. TC05: The uploaded collection configures this request as GET,
   but the intended missing-userId validation test should use POST.
2. TC06: The body uses completd instead of completed. Correct
   the key and set it to the string "false" to test the wrong data
   type.
3. TC01: The request body contains tile rather than title; a
   GET request does not need a request body.
4. Review minor test-name typos in TC02.
Key Findings
- Positive scenarios reportedly passed for GET retrieval and
  successful POST response checks.
- TC03--TC06 reportedly returned 201 Created, so the expected
  negative-validation assertions failed.
- JSONPlaceholder is a demo API. These results do not prove a
  production API defect; POST-created records are not permanently
  persisted.
Skills Demonstrated
Postman, REST API testing, GET/POST requests, JavaScript assertions,
status-code validation, JSON field and data-type validation, negative
testing, response-time checks, test documentation.
Project Files
- To-Do List API Testing.postman_collection.json --- Postman
  collection
- ToDo_API_Test_Cases.xlsx --- test case and execution report
- ToDo_API_Test_Execution_Report.pdf --- summary report
- README.md --- project README information
