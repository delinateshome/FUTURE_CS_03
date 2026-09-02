# FUTURE_CS_03
# API Security Risk Analysis

## Cyber Security Task 3 | Future Interns

This project focuses on analyzing the security of a public test API and identifying common API security risks using safe, read-only testing.

## 📌 Project Overview

The objective of this task was to perform a basic API security assessment of JSONPlaceholder, a public fake REST API designed for testing and development.

The assessment focused on:

* Authentication requirements
* Access control observations
* Data exposure
* HTTP response headers
* Rate limiting
* Security-related configurations
* Potential business impact
* Recommended security improvements

All testing was performed within the permitted ethical scope.

## 🔗 API Tested

**JSONPlaceholder**

`https://jsonplaceholder.typicode.com`

JSONPlaceholder provides free fake REST API endpoints for testing and development purposes.

## 🛠️ Tools Used

* Postman — API requests and response analysis
* GitHub — Project documentation and evidence
* Microsoft Word / Google Docs— Report preparation
* PDF — Final report format

## 🔍 Endpoints Tested

| Endpoint    | Method | Authentication | Result |
| ----------- | ------ | -------------- | ------ |
| `/posts`    | GET    | No Auth        | 200 OK |
| `/users`    | GET    | No Auth        | 200 OK |
| `/comments` | GET    | No Auth        | 200 OK |
| `/todos`    | GET    | No Auth        | 200 OK |

## 🧪 Methodology

The assessment followed these steps:

1. Reviewed the API documentation.
2. Selected safe, publicly available endpoints.
3. Sent read-only GET requests using Postman.
4. Inspected HTTP status codes and response data.
5. Reviewed response headers and security-related controls.
6. Checked whether authentication was required.
7. Identified potential security risks.
8. Classified findings according to severity.
9. Considered potential business impact in a real-world SaaS environment.
10. Developed remediation recommendations.

## ⚠️ Key Findings

### 1. Unauthenticated API Access — Low

The tested endpoints were accessible without authentication.

This is acceptable for a public demonstration API such as JSONPlaceholder, but in a real SaaS application, sensitive or private resources should require appropriate authentication and authorization.

### 2. User/Contact-Style Data Exposure — Low

The `/users` and `/comments` endpoints returned fields such as names, email addresses, phone numbers, and other contact-style information.

The data is fictional in JSONPlaceholder, so the practical risk in this environment is low. In a real application containing genuine customer information, excessive exposure could create privacy and security risks.

### 3. Technology Disclosure — Low

The API response included the `X-Powered-By: Express` header.

This reveals the underlying server-side technology. While this is not a critical vulnerability by itself, unnecessary technology disclosure can provide attackers with additional information about the application stack.

### 4. CORS Configuration — Informational

CORS-related headers were observed during testing. However, the available response headers were not sufficient to confirm a CORS vulnerability.

No CORS exploitation or bypass testing was performed.

## ✅ Positive Security Controls Observed

Several useful security controls were also observed:

* HTTPS was used for API communication.
* Rate-limit headers were present.
* `X-Content-Type-Options: nosniff` was present.
* The API returned the expected JSON content type.
* The API responded successfully with appropriate HTTP status codes.

## 📊 Risk Summary

| Finding                          | Severity      |
| -------------------------------- | ------------- |
| Unauthenticated API access       | Low           |
| User/contact-style data exposure | Low           |
| Technology disclosure            | Low           |
| CORS configuration observation   | Informational |

## 🛡️ Recommended Remediation

For a production SaaS API, recommended controls include:

* Require authentication for protected resources.
* Implement strong authorization and object-level access controls.
* Return only the data required by the client.
* Avoid exposing unnecessary personal or sensitive information.
* Remove unnecessary technology-disclosure headers.
* Implement appropriate rate limiting.
* Validate and sanitize API inputs.
* Use secure authentication tokens and enforce proper token handling.
* Configure CORS according to the application's trusted origins and requirements.
* Continuously monitor API activity and security events.

## 🔐 Ethical Scope

This assessment was conducted only against a public test API.

The testing was limited to safe, read-only requests and documentation-based analysis.

The following activities were **not performed**:

* Authentication bypass
* Authorization bypass
* Exploitation of vulnerabilities
* Denial-of-service or flooding
* Attacks against private systems
* Attacks against production APIs
* Unauthorized access to data

## 📁 Project Files

* `API_Security_Risk_Analysis_Report.docx` — Complete security assessment report
* `01_GET_posts.png`, `02_GET_users.png`, `03_GET_comments.png`, `04_GET_todos.png` — Postman testing evidence

## 👩‍💻 Author

**Delina Million**

Cyber Security Track
Future Interns — Cyber Security Internship
Task 3 — API Security Risk Analysis
**Repository:** `FUTURE_CS_03`
**Date:** September 2, 2026
