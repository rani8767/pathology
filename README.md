# 🧪 Pathology Management System (Java Spring Boot)

A production-ready RESTful Web API application for Pathology Laboratories built with **Java 21**, **Spring Boot 3.2.x**, **Spring Data JPA**, **H2 Database**, **JUnit 5**, **Springdoc OpenAPI (Swagger UI)**, and **Postman Collection**.

---

## 🌟 Key Features

1. **Patient Management**:
   - Register patients with demographic info, contact details, and blood group.
   - Auto-generated unique patient code (`PAT-XXXXXXXX`).
   - Full search by name, mobile, or code.

2. **Doctor/Referrer Management**:
   - Track referring physicians, clinic/hospital affiliations, and referral commission %.

3. **Test Catalog & Pricing**:
   - Categories (Hematology, Biochemistry, Microbiology, Serology, etc.).
   - Test master with reference ranges (min/max numeric limits), sample type (Blood, Urine, Serum, Plasma, etc.), and unit of measurement.

4. **Lab Order & Billing**:
   - Book test orders for patients with assigned referring doctors.
   - Automated total amount calculation, discount application, and net payment tracking (`UNPAID`, `PARTIAL`, `PAID`).
   - Order fulfillment workflow tracking (`PENDING`, `SAMPLE_COLLECTED`, `IN_LAB`, `COMPLETED`, `CANCELLED`).

5. **Lab Result Entry & Report Generation**:
   - Input test parameter results.
   - **Automated Result Evaluation Engine**: Auto-evaluates results as `NORMAL`, `ABNORMAL`, or `CRITICAL` based on reference ranges.
   - Pathologist verification and approval status.

6. **Dashboard Analytics**:
   - Real-time aggregation of total patients, doctors, tests, orders, pending vs. completed lab tests, and total revenue.

7. **Interactive API Specs & Postman**:
   - OpenApi 3.0 UI embedded at `/swagger-ui.html`.
   - Complete Postman Collection v2.1 included in root directory (`Pathology_Management_System.postman_collection.json`).

---

## 🛠️ Technology Stack

- **Java Version**: JDK 21
- **Framework**: Spring Boot 3.2.3
- **Database**: H2 In-Memory DB (Console at `http://localhost:8080/h2-console`)
- **API Documentation**: `springdoc-openapi-starter-webmvc-ui`
- **Validation**: Jakarta Bean Validation (`spring-boot-starter-validation`)
- **Testing**: JUnit 5, Mockito 5, MockMvc

---

## 🚀 Quick Start Guide

### 1. Prerequisite
- Java 21 JDK installed (`java -version`)

### 2. Build & Run Application
Navigate to project directory and run Maven command:

```bash
# Using embedded Maven wrapper or Maven install:
mvn clean spring-boot:run
```

Or run via jar after building:
```bash
mvn clean package
java -jar target/pathology-management-springboot-1.0.0.jar
```

The application starts on **port 8080** by default.

---

## 🔗 Important Endpoints & Interfaces

| Resource | URL | Description |
| :--- | :--- | :--- |
| **Swagger UI** | [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html) | Interactive OpenAPI docs & API testing |
| **OpenAPI Docs** | [http://localhost:8080/v3/api-docs](http://localhost:8080/v3/api-docs) | Raw OpenAPI JSON spec |
| **H2 Console** | [http://localhost:8080/h2-console](http://localhost:8080/h2-console) | JDBC URL: `jdbc:h2:mem:pathologydb`, User: `sa`, Password: `password` |

---

## 🧪 Running Automated Tests

Run unit tests and integration tests:

```bash
mvn clean test
```

### Included Test Files:
- `PatientControllerTest.java` (Controller layer mock tests)
- `LabOrderServiceTest.java` (Business logic unit tests)
- `LabReportServiceTest.java` (Auto-evaluation logic tests)
- `PathologyIntegrationTest.java` (End-to-end HTTP integration flow)

---

## 📬 Postman Collection

Import `Pathology_Management_System.postman_collection.json` directly into Postman:
1. Open Postman -> Click **Import**.
2. Select `Pathology_Management_System.postman_collection.json`.
3. Pre-configured environment variable `{{baseUrl}}` is set to `http://localhost:8080/api/v1`.

---

## 📄 Test Cases Document

See [TEST_CASES.md](file:///c:/Users/upasa/Ai%20project/pathology-management-springboot/TEST_CASES.md) for the complete manual and automated test case matrix.
