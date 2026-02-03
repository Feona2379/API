# API

---

```md
# 🚀 API Testing Automation with Postman + GitHub Actions
## JSONPlaceholder Demo Project

This project demonstrates **API testing using Postman** with basic CRUD operations and **automation using GitHub Actions**.

The APIs are tested against the public fake REST service:

👉 https://jsonplaceholder.typicode.com/

The goal of this project is to showcase:

- REST API testing
- Request validation
- Automated test execution
- CI/CD integration using GitHub Actions

---

# 📌 Project Overview

This repository contains Postman collections designed to test API endpoints using:

✅ GET Requests  
✅ POST Requests  
✅ PUT Requests  
✅ DELETE Requests  

The tests include validations for:

- Status codes
- Response structure
- Data validation
- Basic assertions

Automation is handled using **Newman**, which runs Postman collections in a CI pipeline.

---

# 🧰 Tools & Technologies

- Postman
- Newman (Postman CLI Runner)
- GitHub Actions
- REST API Testing
- JSONPlaceholder API

---

# 🌐 API Base URL

```

[https://jsonplaceholder.typicode.com/](https://jsonplaceholder.typicode.com/)

```

This is a fake online REST API used for testing and prototyping.

⚠️ Note: Data changes are not actually saved on the server.

---

# 📂 Project Structure

```

.
├── postman/
│   ├── jsonplaceholder_collection.json
│   └── jsonplaceholder_environment.json
│
├── .github/
│   └── workflows/
│       └── postman-newman.yml
│
└── README.md

```

---

# 🧪 API Test Scenarios

## ✅ GET Request
Fetch list of posts.

Endpoint:
```

GET /posts

```

Validation:
- Status code = 200
- Response body exists

---

## ✅ POST Request
Create a new post.

Endpoint:
```

POST /posts

```

Validation:
- Status code = 201
- Response contains id

---

## ✅ PUT Request
Update an existing post.

Endpoint:
```

PUT /posts/1

```

Validation:
- Status code = 200
- Updated fields returned

---

## ✅ DELETE Request
Delete a post.

Endpoint:
```

DELETE /posts/1

````

Validation:
- Status code = 200

---

# 🧾 Sample Postman Test Script

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response contains userId", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property("userId");
});
````

---

# 💻 How to Run Tests Locally

## Step 1 — Install Node.js

Download from:
[https://nodejs.org](https://nodejs.org)

---

## Step 2 — Install Newman

```
npm install -g newman
```

---

## Step 3 — Run Collection

```
newman run postman/jsonplaceholder_collection.json
```

With environment file:

```
newman run postman/jsonplaceholder_collection.json -e postman/jsonplaceholder_environment.json
```

---

# ⚙️ GitHub Actions Automation

This project includes CI automation using GitHub Actions.

The workflow automatically runs API tests when:

* Code is pushed
* Pull requests are created
* Workflow is triggered manually

---

## 📄 Workflow File Location

```
.github/workflows/postman-newman.yml
```

---

## 🛠️ Example GitHub Actions Workflow

```yaml
name: Run Postman API Tests

on:
  push:
  pull_request:
  workflow_dispatch:

jobs:
  api-tests:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: 18

      - name: Install Newman
        run: npm install -g newman

      - name: Run Postman Collection
        run: newman run postman/jsonplaceholder_collection.json
```

---

# 📊 What This Project Demonstrates

✔ API Testing using Postman
✔ Writing automated test validations
✔ Running tests using Newman CLI
✔ CI/CD integration with GitHub Actions
✔ Basic QA automation workflow

---

# 👩‍💻 Author

**Feona Donnal**

LinkedIn:
[http://www.linkedin.com/in/feona-donnal-bb9a0a185](http://www.linkedin.com/in/feona-donnal-bb9a0a185)

GitHub:
[https://github.com/Feona2379](https://github.com/Feona2379)

---


