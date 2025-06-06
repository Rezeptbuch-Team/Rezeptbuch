# Rezeptbuch

## Presentation
[PDF](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/PresentationFirstHalf.pdf)  
[Google Slides](https://docs.google.com/presentation/d/19ac-nlXZU6XP5UNWN2HKG892zUa7CUVoy0YfmfxGHDY/edit#slide=id.g31d7731fb03_1_0)

## Vision
**Our Vision**  
Rezeptbuch is more than just another recipe app.
Our goal is to create a clean, distraction-free cooking companion that puts users in control.
Unlike many existing platforms, Rezeptbuch works fully offline by default, with no ads, no sign-up required, and no unnecessary features.
Users can store their personal recipes locally and only opt in to online features if they choose to share.
Even then, sharing is anonymous and simple.
We believe in privacy, clarity, and giving users full ownership of their cooking experience.

## Workload Statistics

### 1. Hours per Person and Main Contribution
| Person               | Hours     | Main Contribution                        |
|----------------------|-----------|------------------------------------------|
| Julius Göler         | 28        | Application Logic, Project Documentation |
| Luca Grimm           | 12        | Frontend Design/Development (MAUI)       |
| Jaron Köhler         | 7         | Server/API                               |
| Tom Jenrich          | 2         | Server/API                               |

#### 2. Hours per Workflow
| Workflow                    | Hours     |
|-----------------------------|-----------|
| Requirements Analysis       | 15        |
| Public Relations            | 5         |
| Software Architecture       | 12        |
| Tool Setup                  | 7         |
| Implementation (Prototype)  | 10        |

#### 3. Hours per Phase
| Phase               | Hours |
|---------------------|-------|
| Inception           | 17    |
| Elaboration         | 11    |
| Construction        | 21    |



## Overall Use Case Diagram

**Diagram:**  
![Overall Use Case Diagram](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/UseCaseDiagram.png)

**Focus for the Demo:**  
- List local recipes
- List online recipes


## **Architectural Styles/Decisions and Key Arguments**

- **Architectural Style**:
  - Layered Architecture (Frontend, Application Logic, API)
  - Key Arguments:
    - **Separation of Concerns**: Clear distinction between the user interface, logic, and backend.
    - **Flexibility**: Easily extendable for new features.

- **Additional Decisions**:
  - TDD/Mocking
  - Dependency Injection/Modularity (OCP)
  - MVVM in the frontend
  - Separation of concerns in the application logic (SRP)
  - Decoupling of the application and the server, only communicating through a RESTful API
  - Consistent UI/UX patterns
  - Ensure data integrity through the use of hashes
  - Local data storage and database to support offline access

### **Software Tools/Platforms/Technologies**

| Category                   | Tools/Technologies      |
|----------------------------|-----------------------------|
| Frontend/Application Logic | MAUI, MVVM                  |
| Server/API                 | ASP.NET Core, REST          |
| Database                   | SQLite (local), MySQL (online, not final yet), XML |
| Diagram Creation           | draw.io                     |
| Project Management         | Jira, Github (Code, Documentation) |
| Testing                    | nUnit, Moq                  |
