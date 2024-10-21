# Rezeptbuch - Software Requirement Specification
## Table of Contents
- [Table of contents](#table-of-contents)
- [Introduction](#1-introduction)
  - [Purpose](#11-purpose)
  - [Scope](#12scope)
  - [Definitions, Acronyms and Abbreviations](#13definition-acronyms-and-abbreviations)
  - [References](#14references)
  - [Overview](#15overview)
- [Overall Description](#-2overall-description)
  - [Vision](#21vision)
  - [Use Case Diagram](#22-use-case-diagram)
  - [Technology Stack](#23-technology-stack)
- [Specific Requirements](#3-specific-requirements)
  - [Functionality](#31functionality)
  - [Usability](#32usability)
  - [Reliability](#33reliability)
  - [Performance](#34performance)
  - [Supportability](#35supportability)
  - [Design Constraints](#36design-constraints)
  - [Online User Documentation and Help System Requirements](#37online-user-documentation-and-help-system-requirements)
  - [Purchase components](#38purchased-components)
  - [Interfaces](#39interfaces)
  - [Legal, Copyright, and Other Notices](#310legal-copyright-and-other-notices)
  - [Applicable Standards](#311applicable-standards)
- [Supporting Information](#4supporting-information)

## 1. Introduction
### 1.1 Purpose
This document outlines the requirements for our application, including non-functional requirements, design constraints, and other key elements needed to present a full and detailed description of the specifications for Rezeptbuch.

### 1.2	Scope
Rezeptbuch is a cookbook application designed for offline use, with features for sharing and discovering new recipes through add-ons that enhance your personal collection. Key functionalities include:
- Adjusting the number of servings
- Searching recipes by category
- Filtering recipes by ingredients, with the option to input on-hand ingredients and receive matching recipe suggestions

For the planned subsystems and use-case models see the [use-case-diagram](#22-use-case-diagram).

### 1.3	Definitions, Acronyms and Abbreviations
| Abbreviation                                | Explanation   |
| -----------------------------------------|:---------- |
| MVVM | Model-View-Viewmodel |
| REST | Representational State Transfer  |

### 1.4	References

| Title                                                              | Date       | Publishing organization   |
| -------------------------------------------------------------------|:----------:| ------------------------- |
| [Rezeptbuch Blog](https://github.com/GermanJesus-lul/Rezeptbuch/discussions/categories/announcements)| 21.10.2024 | Rezeptbuch Team  |
| [GitHub](https://github.com/GermanJesus-lul/Rezeptbuch) | 21.10.2024 | Rezeptbuch Team  |

### 1.5	Overview
The upcoming chapter presents a project overview, featuring the vision and the Overall Use Case Diagram. Chapter three, titled Requirements Specification, delves deeper into the detailed requirements concerning functionality, usability, and design aspects. The final chapter includes supporting information.

## 2. Overall Description
### 2.1 Vision
Rezeptbuch is a cookbook application designed for offline use, with features for sharing and discovering new recipes through add-ons that enhance your personal collection and the ability to adjust the number of servings for a recipe.

### 2.2 Use Case Diagram
![](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/UseCaseDiagram.png)

### 2.3 Technology Stack

Below is an overview of the technology stack used for the development of this project:  
Backend: ASP.NET WebApi  
Frontend: .NET Maui  
Application logic: .NET  
Testing: NUnit  
IDE: Visual Studio Code  
Project management: Jira

## 3. Specific Requirements
### 3.1	Functionality
#### 3.1.1	Recipe overview
Display a comprehensive recipe overview, including a "Publish" button if the recipe was created by the current user.
The overview should feature the recipe's name, a brief description, an image of the dish, a list of ingredients, and the total cooking time.  
[Show recipe use case](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/UseCases/UC1_ShowRecipe.md)

#### 3.1.2	Recipe walkthrough
Provide a step-by-step walkthrough of the recipe, allowing users to follow each instruction sequentially.
Before beginning the walkthrough, include an option to adjust the number of servings to customize the ingredient quantities.  
[Show recipe use case](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/UseCases/UC2_NavigateThroughRecipe.md)

#### 3.1.3	List of installed recipes
Show a list of installed recipes with options for filtering, searching, and sorting. Additionally, provide ingredient-based recommendations to help users discover new recipes based on the ingredients they have.  
[Show recipe use case](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/UseCases/UC3_ListLocalRecipes.md)

#### 3.1.4	List of online recipes
Display a list of online recipes, showcasing the name and image of each, along with a download button. Provide options for filtering, searching, and sorting to help users easily find the recipes they need.  
[Show recipe use case](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/UseCases/UC4_ListOnlineRecipes.md)

#### 3.1.5	Recipe creation
Allow users to create new recipes, to extend their collection.  
[Show recipe use case](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/UseCases/UC5_CreateRecipe.md)

### 3.2	Usability 
The application should be intuitive and easy to use, reducing the need for extensive learning. Additionally, comprehensive documentation will be provided to guide users in navigating and maximizing the app's features.

#### 3.2.1 Simple Design
The application must maintain a clean, intuitive, and easy-to-navigate interface, ensuring that even users with minimal technical experience can create, search, and view recipes without confusion.

#### 3.2.2  Consistent Design
Design elements, such as buttons, menus, and icons, should remain consistent throughout the application to minimize the learning curve for users. All design components must follow a unified style guide to enhance usability and avoid confusion.

### 3.3	Reliability 
#### 3.3.1	Offline Access
The application must ensure data integrity by preventing loss or corruption, safeguarding users' recipes.

#### 3.3.2  Uptime
The application must maintain a minimum uptime of 99.5% to ensure users can access recipes and features without interruptions.

#### 3.3.3 Offline access
Users should be able to view their saved recipes and basic app functionality, such as searching installed recipes, even when offline.

### 3.4	Performance
#### 3.4.1	Storage
The application will prioritize minimizing storage usage to efficiently accommodate a large number of installed recipes.

#### 3.4.2  List Performance
The application must provide fast and accurate search and filter results. A recipe search should return relevant results within 1 second, even when searching across a large database.

#### 3.4.3 Capacity
The application must support up to 500 concurrent users without experiencing a noticeable degradation in performance or system responsiveness.

#### 3.4.4 Scalability
The system must be scalable to handle increased numbers of users and recipes over time, allowing the application to grow seamlessly without major performance issues.

### 3.5	Supportability

#### 3.5.1	Test-Driven Development
The development process should adhere to test-driven development to ensure complete test coverage from the start.

#### 3.5.2 Coding Standards
We will write the code following widely recognized clean code standards to ensure maintainability, readability, and scalability. This will include the use of best practices such as dependency injection, which promotes loose coupling between components, making the code more modular and easier to test, maintain, and extend over time. By adhering to these principles, we aim to create a robust and efficient codebase that can easily adapt to future changes and improvements.

### 3.6	Design Constraints
The software architecture will strictly adhere to the **MVVM (Model-View-ViewModel)** pattern, ensuring a clear separation between the user interface, application logic, and data management. **RESTful principles** will be followed for backend communication, promoting scalability, modularity, and ease of integration with external services. Additionally, the design will enforce **separation of concerns**, organizing the code into distinct layers with minimal overlap, enhancing maintainability, testability, and future extensibility of the system.

### 3.7	On-line User Documentation and Help System Requirements
The app should be highly intuitive, minimizing the need for additional documentation. For users who require assistance, a "Help" button will be available, offering access to a FAQ section.

### 3.8	Purchased Components
Currently, no purchased components have been integrated into the project. If any are acquired in the future, they will be documented and listed here.

### 3.9	Interfaces
#### 3.9.1	User Interfaces
The user interfaces are:
- Recipe overview
- List of installed recipes
- List of online recipes
- Recipe walkthrough
- Recipe creation

#### 3.9.3	Software Interfaces
The primary software interface is designed for Windows, with potential support for additional platforms planned in the future.

#### 3.9.4	Communications Interfaces
The user application will interact with the API via the HTTP protocol for data exchange and communication.

### 3.10	Legal, Copyright, and Other Notices
The logo is licensed to the Rezeptbuch Team and is only allowed to use for the application. We do not take responsibilty for any incorrect data or errors in the application.

### 3.11	Applicable Standards
The development will follow **REST API standards**, ensuring consistent HTTP methods, status codes, and structured URLs, as well as **clean code standards** to promote readability, maintainability, and modularity.

## 4.	Supporting Information
For any further information you can contact the Rezeptbuch team or check our Blog.  
The Team Members are:
- Julius Göler
- Luca Grimm
- Jaron Köhler
- Tom Jenrich
