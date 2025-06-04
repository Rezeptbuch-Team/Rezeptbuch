# Rezeptbuch

## Workload Statistics
### Hours and main task per person
![Stunden pro Teammitglied](https://github.com/user-attachments/assets/08bc2bef-0017-4e99-9077-f5c20b47eaa4)


### Hours per workflow
![Stunden pro Workflow  (∑=184h)](https://github.com/user-attachments/assets/0118ced9-892e-4f3d-b918-51ffacd1cfb3)

### Hours per phase
![image](https://github.com/user-attachments/assets/d9eda9e8-1246-4103-8049-9b0cac1548f6)


## Demo
### Display available online recipes
![Onlie]("https://github.com/user-attachments/assets/44aaa568-53f5-454c-8088-ec497e23b838")
### Display list of localy available recipes
![Local]("https://github.com/user-attachments/assets/7d488073-8391-4d15-9fbd-17480a908460")
### Display a selected recipe and its ingerdients according to the selected serving size
![ShowRecipe]("https://github.com/user-attachments/assets/328af950-08fb-475a-be64-a9f5798ec6b2")
### Naviagte through diffrent steps of the recipe
![NavigateRecipe]("https://github.com/user-attachments/assets/48dae28a-e7b4-4baf-990d-a0c8ee448395")


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
