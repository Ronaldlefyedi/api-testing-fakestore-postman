  API Testing Project – Fake Store API (Postman)
 Role:
 QA Engineer (Training / Portfolio Project)

 Project Overview

This project demonstrates end-to-end API testing using Postman against the public Fake Store API.

The objective was to validate:

HTTP status codes

Response time performance

JSON response structure

Field-level validation

Positive, negative, and boundary scenarios

API contract consistency

 Base URL
https://fakestoreapi.com
 Tools Used

Postman

Manual API Testing

Postman Test Scripts (JavaScript Assertions)

Excel (Test Execution Report)

JIRA-style defect documentation

 Project Structure
02_api-testing-fakestore/

     01_Test_Plan/
     02_Postman_Collection/
        Fake_Store_API_QA_Collection.postman_collection.json
        Fake_Store_API_Env.postman_environment.json

     03_Test_Cases/
       API_Test_Execution_Report.xlsx

     04_Bug_Reports/
       API_JIRA_Bug_Report.docx

     05_Test_Summary_Report/
       API_Test_Summary_Report.pdf
  Test Coverage
  GET Endpoints Tested

Get All Products

Get Single Product (Valid ID)

Boundary ID (0)

Negative ID (-1)

Very Large ID (9999)

Get Products by Category (Valid & Invalid)

  POST Endpoints Tested

Login (Valid Credentials)

Login (Invalid Password)

Login (Missing Fields)

Create Cart (Valid Payload)

Create Cart (Negative Payload)

 Testing Techniques Applied

Functional Testing

Boundary Testing

Negative Testing

Response Time Validation

JSON Structure Validation

API Contract Validation

  Test Execution Summary
Metric	Result
Total Tests Executed	23
Passed	17
Failed	6
Defects Identified	1 Minor
Observations Logged	5
  Key Findings
  Minor Defect

Login endpoint returned 201 Created instead of expected 200 OK for successful authentication.

  Observations

Invalid product IDs returned 200 instead of 404.

Invalid category returned 200 with empty array.

Response time exceeded preferred SLA threshold (2923ms > 2000ms).

  Sample Test Script Example
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response time under 4000ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(4000);
});
  How to Run the Project

Import the Postman Collection

Import the Environment file

Select the environment

Run the collection using Collection Runner

Review Test Results and Logs

  Skills Demonstrated

API validation using Postman

Writing automated test assertions

Handling API contract inconsistencies

Performance threshold validation

Defect documentation

Structured QA reporting

  Conclusion

The API was found to be functionally stable with minor contract inconsistencies and performance fluctuations.
All findings were documented with structured test execution reports and formal defect logging.
