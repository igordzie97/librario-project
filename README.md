# Librario
Celem projektu było stworzenie aplikacji webowej wspomagającej pracę biblioteki. Aplikacja miała umożliwić realizację podstawowych procesów takich jak:
- Zarządzanie pracownikami
- Zarządzanie użytkownikami serwisu (rejestracja, logowanie, edycja)
- Zarządzanie zasobami (autorzy i książki)
- Wypożyczanie zasobów przez użytkowników końcowych

## Stos technologiczny
- Java 8 + Spring Boot - Warstwa backend
- Vue.js - Warstwa frontend
- MySQL - relacyjny system do zarządzania bazą danych Northwind
- Hibernate - framework do mapowania obiektowo-relacyjnego (ORM)

Warstwa backend została oparta na stylu architektonicznym REST. 

Komunikacja pomiędzy klientem i serwerem odbywa się za pomocą protokołu HTTP, który jednoznacznie określa zasady wymiany informacji oraz współpracy.

Jako forma autoryzacji oraz autentykacji wybrany został mechanizm JWT:
- Użytkownik na samym początku wysyła żądanie HTTP typu POST, zawierające jego login oraz hasło
- Gdy serwer stwierdza, że dane są poprawne, generuje oraz wysyła z żeton JWT, który zawiera zakodowaną rolę użytkownika
- Klient zapisuje zwrócony token i przy każdym żądaniu dołącza go do nagłówka Authorization

<img width="400" alt="Screenshot 2021-08-18 at 01 29 11" src="https://user-images.githubusercontent.com/34041060/129813625-8bfd5643-ada6-4186-80c3-0ec9088d117b.png">

## Opis aplikacji i funkcji
### Role użytkowników w systemie
- **Użytkownik** (czytelnik)
- **Pracownik** - ma możliwość dodawania usuwania i edycji pozycji książek oraz kategorii i autorów. Dodatkowo posiada możliwość oznaczenia wybranej książki jako wypożyczonej i jako dostępnej do wypożyczenia. Możliwość zablokowania wybranego użytkownika (np. ze względu na nieoddanie książek w zdefiniowanym terminie).
- **Administrator** - ma możliwość dodawania, usuwania i edycji pracowników. Drugą funkcjonalnością dostępną dla administratora jest import oraz eksport bazy książek.


