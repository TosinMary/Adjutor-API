# Lendsqr Adjutor API Testing Project

## Project Overview

This repository contains the API testing assessment carried out on the Lendsqr Adjutor APIs using Postman, Newman, and Chai assertions.

The project covers:

* API discovery and endpoint validation
* Automated API testing
* HTTP status code validation
* Response message validation
* Performance observation
* Security-focused testing
* Newman HTML reporting

---

# Tools and Technologies Used

| Tool                   | Purpose                                       |
| ---------------------- | --------------------------------------------- |
| Postman                | API testing and automation                    |
| Newman                 | Command-line execution of Postman collections |
| Chai Assertion Library | API response assertions                       |
| GitHub                 | Version control and repository hosting        |
| Chrome DevTools        | API discovery and network inspection          |

---

# Project Structure

```text
├── Adjutor_API.postman_collection.json
├── README.md
├── newman/
│   └── htmlextra-report.html
```

---

# APIs Tested

The following functionalities were tested:

## Task 1 APIs

* Signup
* Login
* API Key Retrieval

## Task 2 APIs (Nigerian Country-Specific Endpoints)

* BVN Verification Endpoint
* Account Resolution Endpoint
* Additional Nigerian validation endpoints

---

# Test Coverage

The automated test scripts included validation for:

* HTTP status codes
* Response messages
* Response body structure
* Authentication handling
* Unauthorized access validation
* Invalid payload validation
* Response time validation
* Security-related negative testing

---

# Sample Chai Assertions Used

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response message exists", function () {
    const response = pm.response.json();
    pm.expect(response.message).to.exist;
});

pm.test("Response time is below 500ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(500);
});
```

---

# Environment Variables Used

The following Postman variables were configured:

| Variable     | Description                 |
| ------------ | --------------------------- |
| base_url     | Base API URL                |
| api_key      | Generated Adjutor API key   |
| access_token | Authentication bearer token |

---

# How to Set Up the Project

## 1. Clone the Repository

```bash
git clone https://github.com/TosinMary/Lendsqr-Adjutor.git
```

---

## 2. Install Node.js

Download and install Node.js:

[https://nodejs.org/](https://nodejs.org/)

---

## 3. Install Newman

```bash
npm install -g newman
```

---

## 4. Install Newman HTML Reporter

```bash
npm install -g newman-reporter-htmlextra
```

---

# How to Run the Test Scripts

Run the Postman collection using Newman:

```bash
newman run Adjutor_API.postman_collection.json -r cli,htmlextra
```

---

# HTML Test Report

After execution, the HTML report is generated inside:

```text
/newman
```

Open the generated `htmlextra-report.html` file in a browser to view:

* Passed tests
* Failed tests
* Assertions
* Response times
* Request and response details

---

# Test Result Summary

## Passed Tests

* Successful signup validation
* Successful API key generation validation
* HTTP status code validation
* Response message validation
* Unauthorized request handling validation
* Input validation scenarios

## Failed/Observed Issues

* Login flow instability after successful registration
* API key authorization inconsistency
* Nigerian country-specific endpoints returning authorization errors
* Some endpoints exceeding the 500ms response time threshold
* Delayed rate limiting activation
* Empty response body returned despite successful 200 OK response

---

# Performance Observation

During testing, some endpoints exceeded the expected response time benchmark of 500ms.

This may impact:

* User onboarding experience
* Real-time verification flow
* System responsiveness under high traffic conditions

Performance optimization recommendations include:

* Backend query optimization
* Caching implementation
* Improved request handling
* Continuous performance monitoring

---

# Security Observations

The following security-related observations were identified during testing:

* Duplicate account creation using existing email
* Weak validation on full name input fields
* Case-sensitive email uniqueness issue
* Delayed rate limiting enforcement
* API key lifecycle instability
* Authentication inconsistency affecting access validation

---

# Notes

* Sensitive tokens and API keys were removed from the repository for security purposes.
* Environment-specific secrets were replaced with Postman variables.
* The project was structured to follow basic API testing and QA automation best practices.

---

# Author

Tosin Bamidele

Quality Assurance Engineer
