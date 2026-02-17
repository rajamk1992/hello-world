# Postman -- Session Notes

**Topic: API Testing Tool & Its Features**

------------------------------------------------------------------------

# 1. What is Postman?

Postman is a popular API testing tool used by developers, testers, and
project teams to:

-   Send API requests
-   View responses
-   Test backend services
-   Validate integrations

It is widely used in software companies for testing REST APIs without
writing frontend code.

------------------------------------------------------------------------

# 2. Simple Definition for Students

**Postman is a tool used to send requests to APIs and check the
response.**

------------------------------------------------------------------------

# 3. Key Features of Postman

## 1) Send API Requests

-   Supports GET, POST, PUT, DELETE
-   Add headers, query parameters, and request body
-   Supports JSON, form-data, raw, etc.

------------------------------------------------------------------------

## 2) View API Response

-   Status codes (200, 400, 404, 500)
-   JSON / XML response
-   Response time
-   Response size

------------------------------------------------------------------------

## 3) Collections

-   Group related APIs together
-   Share with team
-   Organize project APIs

Example: Collection: E-Commerce APIs - Login API - Product List API -
Order API

------------------------------------------------------------------------

## 4) Environment Variables

Environment variables allow you to store reusable values.

Example Variables: - base_url = https://dev.api.com - token = abc123 -
user_id = 101

Instead of writing full URL every time:

{{base_url}}/login

Benefits: - Easily switch between Dev, Test, Production - No need to
edit every request manually - Secure token management

------------------------------------------------------------------------

## 5) Variable Scopes in Postman

Postman supports different variable scopes:

### 1. Global Variables

-   Available everywhere
-   Used across all collections

### 2. Collection Variables

-   Available only inside a collection

### 3. Environment Variables

-   Available inside selected environment
-   Most commonly used in real projects

### 4. Local Variables

-   Used inside a single request
-   Temporary use

Scope Priority (High to Low): Local → Environment → Collection → Global

------------------------------------------------------------------------

## 6) Runner (Collection Runner)

Runner is used to execute multiple API requests automatically.

It helps in: - Running full API test flow - Repeating requests multiple
times - Running data-driven testing using CSV/JSON files

Example Use Case: - Test login API with 100 different users - Execute
complete regression testing

Steps: 1. Open Collection 2. Click Run 3. Select environment 4. Provide
data file (optional) 5. Execute

------------------------------------------------------------------------

## 7) Automated Testing in Postman

You can write small test scripts in JavaScript.

Example: - Check status code is 200 - Validate response contains
expected value - Validate response time

Used in CI/CD pipelines.

------------------------------------------------------------------------

## 8) Authentication Support

Postman supports: - Bearer Token - Basic Auth - OAuth 2.0 - API Keys

------------------------------------------------------------------------

## 9) History & Debugging

-   Automatically saves request history
-   Helps debug APIs
-   Compare responses easily

------------------------------------------------------------------------

# 10. Real-Time Example for Classroom

Imagine testing a Login API:

POST {{base_url}}/login

Body: { "username": "student1", "password": "1234" }

After login: - Extract token - Store in environment variable - Use token
for next API calls

------------------------------------------------------------------------

# 11. One-Line Summary

**Postman helps test, automate, organize, and manage APIs efficiently
using variables, collections, and runner features.**

------------------------------------------------------------------------

End of Session Notes
