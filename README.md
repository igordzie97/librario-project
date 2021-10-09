# Librario

## Table of Consents
1. [Description](#description)
2. [Technologies and system architecture](technologie-i-architektura)
  - [Backend](#backend)
  - [Database](#database)
  - [Frontend](frontend)
3. [Implemented functionalities](lista-zaimplementowanych-funkcjonalności)
4. [Documentation](#documentation)

## Description
The project puropse was to create a web app which will support library activities, for example:
- employee management
- users management - registration, login, account edition
- sources management - authors and books
- borrowing books by end-users.

## Technologies and system architecture
- **Java 8 and Spring Boot** - Backend
- **Vue.js** - Frontend
- **MySQL** - Relational Database Management System
- **Hibernate** - Object-Relational Mapping framework

<img width="400" alt="Screenshot 2021-08-18 at 01 29 11" src="https://user-images.githubusercontent.com/34041060/129813625-8bfd5643-ada6-4186-80c3-0ec9088d117b.png">

## Backend
API based on REST architectural style.

JWT mechanism is used for authorization and autentification:
- At the begining client sends HTTP request (POST) with login and password
- If credentials are correct - server generates JWT token with encoded user role and sends it to the client
- Client saves the token and attaches it in every request as Authorization header

**Address:** http://localhost:8081

## Database
Dependencies from pom.xml:
```xml
<dependency>
  <groupId>mysql</groupId>
  <artifactId>mysql-connector-java</artifactId>
  <scope>runtime</scope>
</dependency>
```

MySQL database configuration is included in configuration file which is supported by Spring Boot - `application.properties`:
```properties
server.port = 8081

# database configuration
spring.jpa.hibernate.ddl-auto=update
spring.datasource.url=jdbc:mysql://${MYSQL_HOST:localhost}:3306/db_librario?serverTimezone=UTC
spring.datasource.username=springuser
spring.datasource.password=Password
```

## Frontend
Axios library is used for communication with server - as a HTTP client, unambiguously defines the way of information exchange.

From UI perspective - it is used one of the most common components library for Vue.js 2.0, [Element](https://element.eleme.io/#/en-US).

### Start up
`npm install` - installing all modules which are defined in package.json

`npm start` - launching the application (returns what is the local address)

**Address:** https://localhost:9000

## Implemented functionalities
- Import/export book database
- CRUD operations on employee database
- CRUD operations on books database
- CRUD operations on authors database
- Users and their reservations preview
- Curret account data preview
- Books availability preview
- User registration
- Automatic e-mail notifications about starting and ending reservation
- Access to content depending on permissions

## Documentation
Full documentation in Polish:
- [Vision](https://github.com/igordzie97/librario-project/blob/main/documentation/Wizja.pdf)
- [Requirements](https://github.com/igordzie97/librario-project/blob/main/documentation/Wymagania.pdf)
- [Architecture](https://github.com/igordzie97/librario-project/blob/main/documentation/Architektura.pdf)

## Authors
- Igor Dzierwa
- Adrian Nędza
- Konrad Makuch
