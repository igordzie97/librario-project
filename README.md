# Librario

## Table of Consents
1. [Description](#description)
2. [Technologies and system architecture](technologie-i-architektura)
  - [Backend](#backend)
  - [Database](#database)
  - [Frontend](frontend)
3. [Implemented functionalities](lista-zaimplementowanych-funkcjonalności)
4. [Documentation](#dokumentacja)

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
MySQL database configuration is included in configuration file which is supported by Spring Boot - `application.properties`:

<img width="1000" alt="Screenshot 2021-08-21 at 11 59 23" src="https://user-images.githubusercontent.com/34041060/130318316-4d60f6a2-c512-462a-936f-e5839c38673b.png">

## Frontend
Axios library is used for communication with server - as HTTP client, unambiguously defines the way of information exchange.

W aspekcie wizualnym została wykorzystana bilbioteka komponentów dla Vue.js w wersji 2, Element: 
- https://element.eleme.io/#/en-US

Jako menadżer pakietów została wykorzystana oficjalna propozycja od twórców Node.js - Npm.

### Uruchomienie
`npm install` - ściągnięcie wszystkich potrzebnych paczek (node_modules), które są zdefiniowane w package.json.

`npm start` - uruchomienie aplikacji, które zwraca pod jakim adresem można otworzyć lokalny projekt.

### Adres
- https://localhost:9000

## Lista zaimplementowanych funkcjonalności
- Import/eksport bazy książek
- Operacje CRUD na bazie pracowników
- Operacje CRUD na bazie książek
- Operacje CRUD na bazie autorów
- Podgląd użytkowników i ich rezerwacji
- Podgląd danych obecnego konta
- Podgląd rezerwacji i możliwość usunięcia
- Podgląd dostępnych książek
- Rejestracja użytkownika
- Automatyczne wysyłanie powiadomień na maila o rozpoczęciu i zakończeniu rezerwacji
- Dostęp do zawartości strony w zależności od uprawnień

## Dokumentacja
- [Wizja](https://github.com/igordzie97/librario-project/blob/main/documentation/Wizja.pdf)
- [Wymagania](https://github.com/igordzie97/librario-project/blob/main/documentation/Wymagania.pdf)
- [Architektura](https://github.com/igordzie97/librario-project/blob/main/documentation/Architektura.pdf)

## Autorzy
- Igor Dzierwa
- Adrian Nędza
- Konrad Makuch
