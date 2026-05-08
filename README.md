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

---

# Test Coverage

The automated test scripts included validation for:

* HTTP status codes
* Response messages
* Response body structure
* Authentication handling
* Response time validation

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
| otp | Authentication otp |

---

## Exported Postman collection JSON file and link to Postman collection will be added to QA documentation as Github restricts collection with API Key to be directly pushed to github repository.

## Also a generated report has been added to show which test passes or fail

# How to Set Up the Project

## 1. Clone the Repository

```bash
git clone https://github.com/TosinMary/Adjutor-API.git
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

# Author

Tosin Bamidele

Quality Assurance Engineer
