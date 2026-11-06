# Student Registration API

The system under test for the API contract and dynamic testing lab.
It is a Spring Boot REST API that manages students, courses, and course rosters.

## What you need

- JDK 17 or newer
- Maven
- Postman
- Newman (`npm install -g newman`), for running your collection from the command line

## Start the API

From the project root, run:

```bash
mvn spring-boot:run
```

The API is ready when the log says `Started StudentRegDemo`.

| What | Where |
| --- | --- |
| API base URL | `http://localhost:8080/api` |
| Swagger UI | `http://localhost:8080/swagger-ui.html` |
| OpenAPI contract (JSON) | `http://localhost:8080/v3/api-docs` |
| OpenAPI contract (YAML) | `http://localhost:8080/v3/api-docs.yaml` |
| H2 database console | `http://localhost:8080/h2-console` (JDBC URL `jdbc:h2:mem:studentdb`, user `sa`, password `password`) |

## The contract

The live contract is generated from the OpenAPI annotations in the controllers and DTOs.
`contract/openapi.json` and `contract/openapi.yaml` are saved copies of version 1.0.0, which you use as a fixed baseline.

## Test data

The database is in memory. It starts empty, and restarting the API clears it.
Your tests should create the data they need and save the returned ids in variables.
Don't assume a particular id, because ids keep increasing until the API restarts.
