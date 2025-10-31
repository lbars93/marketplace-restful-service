# Marketplace RESTful Service

A minimal Spring Boot REST backend for managing marketplace resources. Uses PostgreSQL, Spring Data JPA, Bean Validation, and Actuator.

## Tech stack
- Java 17, Maven
- Spring Boot (Web, Data JPA, Validation, Actuator)
- PostgreSQL (via Docker Compose)

## Prerequisites
- Java 17+
- Maven 3.9+
- Docker (for local PostgreSQL)

## Quick start
1) Start the database (Docker):
```
docker compose up -d
```
This starts:
- PostgreSQL on localhost:5432 with DB `marketplace`, user `utest`, password `upass`
- pgAdmin on http://localhost:8888 (email: lbars93@mail.com, password: lbars)

2) Run the application:
```
mvn spring-boot:run
```
The app starts on http://localhost:8080.

3) Verify health:
```
curl http://localhost:8080/actuator/health
```

## Useful URLs
- App: http://localhost:8080
- Health check: http://localhost:8080/actuator/health
- pgAdmin: http://localhost:8888 (login with the email/password above)

## Troubleshooting
- Port 5432 already in use: stop local Postgres or change the mapped port in `docker-compose.yml`.
- Connection refused: ensure `docker compose ps` shows the `postgresql` container is healthy before starting the app.
