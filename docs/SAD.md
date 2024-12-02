## Table of Contents
1. [Introduction](#1-introduction)
   
   1.1 [Purpose](#11-purpose)
   
   1.2 [Scope](#12-scope)
   
   1.3 [Definitions, Acronyms and Abbreviations](#13-definitions,-acronyms-and-abbreviations)
   
   1.4 [References](#14-references)
   
   1.5 [Overview](#15-overview)

3. [Architectural Representation](#11-purpose)

4. [Architectural Goals and Constrains](#3-architectural-goals-and-constraints)

5. [Use Case View](#4-use-case-view)
   
   4.2 [Use Case Realizations](#42-use-case-realizations)

6. [Logical View](#5-logical-view)
   
   5.1 [Overview](#51-overview)
   
   5.2 [Architecturally Significant Design Packages](#52-architecturally-significant-design-packages)

7. [Process View](#6-process-view)

8. [Deployment View](#8-deployment-view)

9. [Implementation View](#8-implementation-view)
   
   8.1 [Overview](#81-overview)
   
   8.2 [Layers](#82-layers)

10. [Data View](#9-data-view-(optional))

11. [Size and Performance](#10-size-and-performance)

12. [Quality](#11-quality)

## 1. Introduction

### 1.1 Purpose
This Software Architecture Document (SAD) provides an overview of the architecture for the cookbook application,
capturing the significant design decisions made to address the system’s requirements and goals.
It presents the architecture from multiple perspectives, including logical, process, and deployment views.

The document is intended for the development team, stakeholders, and future maintenance teams,
serving as a reference to ensure consistency in implementation, alignment with project objectives,
and ease of future updates.

### 1.2 Scope
This Software Architecture Document defines the architecture of the Rezeptbuch application,
covering key components, interactions, and design decisions.
It guides development, deployment, and maintenance to ensure alignment with performance,
scalability, and usability goals.

### 1.3 Definitions, Acronyms and Abbreviations
| Abbreviation                                | Explanation   |
| -----------------------------------------|:---------- |
| SAD | Software Architecture Document |
| ASR | Architecturally Significant Requirements |
| DI  | Dependency Injection |
| OCP | Open-Closed-Principle |
| SRP | Single-Responsibility-Principle |


### 1.4 References
| Title                                                              | Date       | Publishing organization   |
| -------------------------------------------------------------------|:----------:| ------------------------- |
| [Rezeptbuch Blog](https://github.com/GermanJesus-lul/Rezeptbuch/discussions/categories/announcements)| 27.11.2024 | Rezeptbuch Team  |
| [GitHub](https://github.com/GermanJesus-lul/Rezeptbuch) | 27.11.2024 | Rezeptbuch Team  |


### 1.5 Overview
This document outlines the architecture of Rezeptbuch, covering the purpose, key goals,
architectural representation, and views (Use-Case, Logical, Process, Deployment, and Implementation).
It also addresses size, performance, and quality considerations.

## 2. Architectural Represantation


## 3. Architectural Goals and Constraints
The architecture of Rezeptbuch is shaped by Architecturally Significant Requirements (ASR)
that define the system's quality attributes and constraints.
These requirements address critical aspects such as performance, testability, maintainability,
usability and scalability.

For a detailed overview of the ASR and the associated architectural decisions,
refer to the [ASR document](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/ASR.md).


## 4. Use-Case-View
Below is the Use Case Diagram for Rezeptbuch, which provides a visual representation of the system’s core use cases
and the interactions between actors and the system:

![Use Case Diagram](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/UseCaseDiagram.png)

Below is the list of key use cases for Rezeptbuch, each detailing a specific interaction between the user and the system:
- [Show recipe](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/UseCases/UC1_ShowRecipe.md)  
   Displays detailed information about a specific recipe, including ingredients, instructions, and related metadata.
- [Navigate through recipe](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/UseCases/UC2_NavigateThroughRecipe.md)  
   Guides the user step-by-step through the cooking process with the option to adjust servings before starting.
- [List local recipes](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/UseCases/UC3_ListLocalRecipes.md)  
   Provides a list of locally saved recipes with filtering, sorting, and searching capabilities.
- [List online recipes](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/UseCases/UC4_ListOnlineRecipes.md)  
   Fetches and displays a list of online recipes with options for filtering and sorting.
- [Create recipe](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/UseCases/UC5_CreateRecipe.md)  
   Allows users to create and save a new recipe with details such as title, ingredients, and instructions.

### 4.1 Use-Case Realizations
For two of these use cases, Use-Case Realization Specifications (UCRS) have been created
to provide deeper insights into their implementation:
- [Navigate through recipe](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/UCRS/UCRS_NavigateThroughRecipe.md)
- [Show recipe](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/UCRS/UCRS_ShowRecipe.md)

## 5. Logical View
The MAUI frontend interacts with various services provided by the application logic
to implement the core functionality of Rezeptbuch.
These services manage tasks such as recipe retrieval, filtering and synchronization,
ensuring a clean separation between the user interface and the backend logic.

The following diagram illustrates the class structure of the application logic:
![Application Class Diagram](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/class_diagrams/ApplicationLogicDiagram.drawio.png)


## 6. Process View
The Process View illustrates the runtime interactions between the system's components during key operations.
Below are the component-level sequence diagrams for core processes:

1. Show Recipe:  
Demonstrates how the system retrieves and displays detailed information about a specific recipe.  
![Show Recipe Sequence Diagram](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/sequence_diagrams/ShowRecipeSequenceDiagram.png)

2. Navigate Through Recipe:  
Visualizes the step-by-step process of navigating a recipe.  
![Navigate Through Recipe Sequence Diagram](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/sequence_diagrams/NavigateThroughRecipeSequenceDiagram.png)

3. List Local Recipes:  
Shows how the system fetches locally saved recipes.  
![List Local Recipes Sequence Diagram](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/sequence_diagrams/ListLocalRecipesSequenceDiagram.png)

4. List Online Recipes:  
Depicts the process of retrieving recipes from the server.  
![List Online Recipes Sequence Diagram](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/sequence_diagrams/ListOnlineRecipesSequenceDiagram.png)

## 7. Deployment View


## 8. Implementation View

### 8.1 Overview
The Rezeptbuch implementation model is organized into three main layers:
1. **Frontend**:  
   Handles user interaction and presentation
2. **Application Logic**:  
   Serves as the core of the application, managing workflows (e.g., startup logic, recipe handling) and acting as the intermediary between the Frontend and API layers.
3. **API (Server)**:  
   Provides the online service for recipe storage, retrieval and listing.

### 8.2 Layers
The following package diagram illustrates the organization of the Rezeptbuch implementation model into three main layers:
Frontend, Application Logic, and API (Server), highlighting the dependencies and interactions between these layers.

![Package Diagram](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/PackageDiagram/PackageDiagram.png)


## 9. Data View (optional)


## 10. Size and Performance


## 11. Quality
The architecture of Rezeptbuch is designed to support key quality attributes:  
- **Performance**:  
Local recipe lists load in under 0.5 seconds and online recipes in under 1.5 seconds, achieved through optimized data retrieval mechanisms.
- **Testability**:  
Test-Driven Development (TDD) ensures high code quality, supported by mocking frameworks for effective testing of isolated components.
- **Maintainability**:  
The modular codebase follows principles like Dependency Injection (DI), Open-Closed-Principle (OCP) and Single-Responsibility-Principle (SRP), enabling straightforward updates and feature integration.
- **Usability**:  
The intuitive UI requires no formal training, with consistent UX patterns ensuring ease of use for all users.
- **Security**:  
Data integrity is safeguarded using hashes during syncing.
- **Availability**:  
Offline access is supported through local storage and database synchronization, allowing uninterrupted usage.
- **Scalability**:  
Designed to handle up to 1 million recipes.  

This design ensures the system is robust, user-friendly, and adaptable to future needs.
