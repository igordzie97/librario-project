# Librario - księgarnia

## Spis Treści
1. [Opis](opis)
2. [Technologie i architektura systemu](technologie-i-architektura)
  - [Backend](backend)
  - [Baza danych](baza-danych)
  - [Frontend](frontend)
3. [Lista zaimplementowanych funkcjonalności](lista-zaimplementowanych-funkcjonalności)
4. [Dokumentacja](#dokumentacja)

## Opis
Celem projektu było stworzenie aplikacji webowej wspomagającej pracę biblioteki. Aplikacja miała umożliwić realizację podstawowych procesów takich jak:
- Zarządzanie pracownikami
- Zarządzanie użytkownikami serwisu (rejestracja, logowanie, edycja)
- Zarządzanie zasobami (autorzy i książki)
- Wypożyczanie zasobów przez użytkowników końcowych

## Technologie i architektura systemu
- **Java 8 + Spring Boot** - Warstwa backend
- **Vue.js** - Warstwa frontend
- **MySQL** - relacyjny system do zarządzania bazą danych
- **Hibernate** - framework do mapowania obiektowo-relacyjnego (ORM)

<img width="400" alt="Screenshot 2021-08-18 at 01 29 11" src="https://user-images.githubusercontent.com/34041060/129813625-8bfd5643-ada6-4186-80c3-0ec9088d117b.png">

## Backend
Api oparte na stylu architektonicznym REST. 

Jako formę autoryzacji oraz autentyfikacji został wybrany mechanizm JWT:
- Użytkownik na samym początku wysyła żądanie HTTP typu POST, zawierające jego login oraz hasło
- Gdy serwer stwierdza, że dane są poprawne, generuje oraz wysyła z żeton JWT, który zawiera zakodowaną rolę użytkownika
- Klient zapisuje zwrócony token i przy każdym żądaniu dołącza go do nagłówka Authorization

### Adres
- http://localhost:8081

## Baza danych
Konfiguracja bazy danych z pliku application.properties:

<img width="822" alt="Screenshot 2021-08-21 at 11 59 23" src="https://user-images.githubusercontent.com/34041060/130318316-4d60f6a2-c512-462a-936f-e5839c38673b.png">

- **Nazwa bazy danych** - db_librario
- **Nazwa użytkownika** - springuser
- **Hasło użytkownika** - Password

## Frontend
Do komunikacji z serwerem została wykorzystana biblioteka axios, będąca klientem HTTP, który jednoznacznie określa sposób wymiany informacji oraz współpracy.

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
