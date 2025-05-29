# Rezeptbuch

## Workload Statistics
### Hours and main task per person

### Hours per workflow

### Hours per phase


## Demo
Description + Screenshots



## Architectural Style
Layered Architecture (Frontend, Application Logic, API):
 - **Separation of Concerns:** Clear separation of GUI, Logic and Backend
 - **Flexibility:** Easily expandable for new features.

## Tech Stack
- **Frontend/Application Logic:** MAUI, MVVM (Community Toolkit)
- **Server/API:** ASP.NET Core, REST, Render (Hosting)
- **Database:** SQLite (lokal), PostgreSQL (Server)
- **Diagram Creation:** draw.io
- **Project Management:** Jira, GitHub (Code, Dokumentation)
- **Testing:** nUnit, Moq
- **API Spezifikation:** OpenAPI/Swagger

## Database Design
A description and diagram of the local database can be found [here.](https://github.com/Rezeptbuch-Team/Rezeptbuch/blob/main/docs/DataStorageConcept.md#local-db)

## Testing
We implemented unit and integration tests in the Application Logic and unit tests in the API.
The testplan can be found [here.](https://github.com/Rezeptbuch-Team/Rezeptbuch/blob/main/docs/Testplan.md)

## Code Metrics
We used Sonarqube to analyze our code.
The three key metrics we focussed on were:
- **Code Smells:** Minor issues that don’t break functionality but may impact maintainability.
- **Cognitive Complexity:** A readability-focused improvement over Cyclomatic Complexity.
- **Duplications:** Measures how much of the code is repeated unnecessarily.

A detailed documentation of our code metrics can be found [here.](https://github.com/Rezeptbuch-Team/Rezeptbuch/blob/main/docs/CodeMetrics.md)

## CI/CD
We used Github Actions to implement a CI pipeline to ensure that all tests of the Application Logic pass.
We also implemented a Github Actions CD pipeline to build a Windows version of our application.

By integrating Render into our API repository we also implemented continous deployment for our API.
