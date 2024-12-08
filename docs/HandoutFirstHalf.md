# Rezeptbuch

## Workload Statistics

### 1. Hours per Person and Main Contribution
| Person               | Hours     | Main Contribution                        |
|----------------------|-----------|------------------------------------------|
| Julius Göler         | 28        | Application Logic, Project Documentation |
| Luca Grimm           | 9         | Frontend Design/Development (MAUI)       |
| Jaron Köhler         | 5         | Server/API                               |
| Tom Jenrich          | 2         | Server/API                               |

#### 2. Hours per Workflow
| Workflow                    | Hours     |
|-----------------------------|-----------|
| Requirements Analysis       | 15        |
| Public Relations            | 5         |
| Software Architecture       | 10        |
| Tool Setup                  | 7         |
| Implementation (Prototype)  | 7         |

#### 3. Hours per Phase
| Phase               | Hours |
|---------------------|-------|
| Inception           |       |
| Elaboration         |       |
| Construction        |       |



## Overall Use Case Diagram

**Diagram:**  
![Overall Use Case Diagram]()

**Focus for the Demo:**  
- List local recipes
- List online recipes


## **Architectural Styles/Decisions and Key Arguments**

- **Architectural Style**: Layered Architecture (Frontend, Application Logic, API)
  - **Key Arguments**:
    - **Separation of Concerns**: Clear distinction between the user interface, logic, and backend.
    - **Flexibility**: Easily extendable for new features.
    - **Testability**: Supports Test-Driven Development (TDD).

- **Additional Decisions**:
  - **MVVM in Frontend**: Ensures a clean separation of UI and logic.
  - **RESTful API**: Standardized communication between application and server.
  - **Modularity**: Simplifies maintenance and future development.

### **Software Tools/Platforms/Technologies**

| Category                   | Tools/Technologies      |
|----------------------------|-----------------------------|
| Frontend/Application Logic | MAUI, MVVM                  |
| Server/API                 | ASP.NET Core, REST          |
| Database                   | SQLite (local), MySQL (online, not final yet), XML |
| Diagram Creation           | draw.io                     |
| Project Management         | Jira, Github (Code, Documentation) |
| Testing                    | nUnit, Moq                  |
