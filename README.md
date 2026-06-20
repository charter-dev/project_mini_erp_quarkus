# Mini ERP System - Quarkus

ERP System adalah aplikasi backend ERP (Enterprise Resource Planning) yang dibangun menggunakan **Quarkus** dan **PostgreSQL** untuk mengelola proses bisnis perusahaan secara terintegrasi melalui REST API.

Project ini mengimplementasikan pendekatan modern Java dengan Quarkus, Hibernate ORM Panache, JWT Authentication, Bean Validation, dan OpenAPI Documentation.

---

## Features

### Master Data

* User Management
* Role Management
* Customer Management
* Supplier Management
* Product Management

### Security

* JWT Authentication
* Role-Based Access Control (RBAC)
* Secure REST API

### Business Process

* Inventory Management
* Purchasing Management
* Sales Management
* ERP Transaction Processing

### API

* RESTful API
* JSON Request/Response
* OpenAPI Documentation
* Swagger UI

---

## Technology Stack

### Backend Framework

| Technology | Version |
| ---------- | ------- |
| Java       | 17      |
| Quarkus    | 3.8.1   |
| Maven      | Latest  |

### Database

| Technology             | Purpose               |
| ---------------------- | --------------------- |
| PostgreSQL             | Relational Database   |
| JDBC PostgreSQL Driver | Database Connectivity |

### Persistence Layer

| Technology    | Purpose                            |
| ------------- | ---------------------------------- |
| Hibernate ORM | ORM Framework                      |
| Panache       | Repository & Active Record Pattern |

### Security

| Technology   | Purpose                            |
| ------------ | ---------------------------------- |
| SmallRye JWT | JWT Authentication & Authorization |

### API Layer

| Technology        | Purpose                            |
| ----------------- | ---------------------------------- |
| RESTEasy Reactive | REST API Framework                 |
| Jackson           | JSON Serialization/Deserialization |

### Validation

| Technology          | Purpose            |
| ------------------- | ------------------ |
| Hibernate Validator | Request Validation |

### Documentation

| Technology       | Purpose               |
| ---------------- | --------------------- |
| SmallRye OpenAPI | OpenAPI Specification |
| Swagger UI       | API Documentation UI  |

### Testing

| Technology | Purpose      |
| ---------- | ------------ |
| JUnit 5    | Unit Testing |

---

## Future Ready Components

Dependency sudah disiapkan untuk pengembangan lebih lanjut:

### Flyway Migration (Commented)

```xml
<artifactId>quarkus-flyway</artifactId>
```

Digunakan untuk:

* Database Versioning
* Schema Migration
* CI/CD Database Deployment

### Redis (Commented)

```xml
<artifactId>quarkus-redis-client</artifactId>
```

Digunakan untuk:

* Caching
* Session Storage
* Performance Optimization

### Kafka (Commented)

```xml
<artifactId>quarkus-smallrye-reactive-messaging-kafka</artifactId>
```

Digunakan untuk:

* Event Driven Architecture
* Asynchronous Processing
* Integration Services

---

## Project Structure

```text
src
├── main
│   ├── java
│   │   └── com.erp
│   │       ├── controller
│   │       ├── service
│   │       ├── repository
│   │       ├── entity
│   │       ├── dto
│   │       ├── security
│   │       └── config
│   │
│   └── resources
│       ├── application.properties
│       └── META-INF
│
└── test
    └── java
```

---

## Prerequisites

Sebelum menjalankan aplikasi, pastikan sudah terinstall:

* Java 17+
* Maven 3.9+
* PostgreSQL 14+
* Git

---

## Clone Repository

```bash
git clone https://github.com/charter-dev/project_mini_erp_quarkus.git

cd project_mini_erp_quarkus
```

---

## Database Configuration

Buat database PostgreSQL:

```sql
CREATE DATABASE erp_db;
```

Konfigurasi pada:

```properties
src/main/resources/application.properties
```

Contoh:

```properties
quarkus.datasource.db-kind=postgresql
quarkus.datasource.username=postgres
quarkus.datasource.password=password

quarkus.datasource.jdbc.url=jdbc:postgresql://localhost:5432/erp_db

quarkus.hibernate-orm.database.generation=update
```

---

## Running Application

### Development Mode

Quarkus menyediakan hot reload secara otomatis.

```bash
mvn quarkus:dev
```

Aplikasi berjalan pada:

```text
http://localhost:8080
```

---

## Build Production

```bash
mvn clean package
```

Output:

```text
target/quarkus-app/
```

Jalankan aplikasi:

```bash
java -jar target/quarkus-app/quarkus-run.jar
```

---

## API Documentation

### Swagger UI

```text
http://localhost:8080/q/swagger-ui
```

### OpenAPI JSON

```text
http://localhost:8080/q/openapi
```

---

## Authentication

Project menggunakan JWT Authentication.

Contoh Authorization Header:

```http
Authorization: Bearer <jwt_token>
```

---

## Testing

Menjalankan seluruh unit test:

```bash
mvn test
```

---

## Build Information

### Maven Coordinates

```xml
<groupId>com.erp</groupId>
<artifactId>erp_system</artifactId>
<version>0.0.1</version>
```

### Java Version

```text
Java 17
```

### Quarkus Version

```text
Quarkus 3.8.1
```

---

## Roadmap

* [ ] Multi Company
* [ ] Multi Warehouse
* [ ] Purchase Order
* [ ] Sales Order
* [ ] Accounting Module
* [ ] Approval Workflow
* [ ] Redis Cache
* [ ] Kafka Event Streaming
* [ ] Flyway Migration
* [ ] Audit Logging
* [ ] Dashboard Analytics

---

## Architecture

```text
┌─────────────┐
│ Client App  │
└──────┬──────┘
       │ REST API
       ▼
┌─────────────────────┐
│   Quarkus Backend   │
├─────────────────────┤
│ JWT Security        │
│ RESTEasy Reactive   │
│ Hibernate Panache   │
│ Bean Validation     │
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│ PostgreSQL Database │
└─────────────────────┘
```

---

## License

MIT License

---

### Tech Keywords

`Java 17` • `Quarkus 3.8.1` • `PostgreSQL` • `Hibernate ORM` • `Panache` • `RESTEasy Reactive` • `JWT` • `OpenAPI` • `Swagger` • `Bean Validation` • `Maven` • `JUnit 5`

README ini sudah cukup layak untuk portfolio GitHub, CV, maupun dokumentasi internal perusahaan.
