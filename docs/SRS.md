# Rezeptbuch - Software Requirement Specification
## Table of Contents

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
[The system’s performance characteristics should be outlined in this section. Include specific response times. Where applicable, reference related Use Cases by name.
•	response time for a transaction (average, maximum)
•	throughput, for example, transactions per second
•	capacity, for example, the number of customers or transactions the system can accommodate
•	degradation modes (what is the acceptable mode of operation when the system has been degraded in some manner)
•	resource utilization, such as memory, disk, communications, etc.

#### 3.4.1	<Performance Requirement One>
[The requirement description goes here.]

### 3.5	Supportability
[This section indicates any requirements that will enhance the supportability or maintainability of the system being built, including coding standards, naming conventions, class libraries, maintenance access, maintenance utilities.]

#### 3.5.1	<Supportability Requirement One>
[The requirement description goes here.]

### 3.6	Design Constraints
[This section should indicate any design constraints on the system being built. Design constraints represent design decisions that have been mandated and must be adhered to.  Examples include software languages, software process requirements, prescribed use of developmental tools, architectural and design constraints, purchased components, class libraries, etc.]

#### 3.6.1	<Design Constraint One>
[The requirement description goes here.]

### 3.7	On-line User Documentation and Help System Requirements
[Describes the requirements, if any, for on-line user documentation, help systems, help about notices, etc.]

### 3.8	Purchased Components
[This section describes any purchased components to be used with the system, any applicable licensing or usage restrictions, and any associated compatibility and interoperability or interface standards.]

### 3.9	Interfaces
[This section defines the interfaces that must be supported by the application. It should contain adequate specificity, protocols, ports and logical addresses, etc. so that the software can be developed and verified against the interface requirements.]

#### 3.9.1	User Interfaces
[Describe the user interfaces that are to be implemented by the software.]

#### 3.9.2	Hardware Interfaces
[This section defines any hardware interfaces that are to be supported by the software, including logical structure, physical addresses, expected behavior, etc. ]

#### 3.9.3	Software Interfaces
[This section describes software interfaces to other components of the software system. These may be purchased components, components reused from another application or components being developed for subsystems outside of the scope of this SRS but with which this software application must interact.]

#### 3.9.4	Communications Interfaces
[Describe any communications interfaces to other systems or devices such as local area networks, remote serial devices, etc.]

### 3.10	Licensing Requirements
[Defines any licensing enforcement requirements or other usage restriction requirements that are to be exhibited by the software.]

### 3.11	Legal, Copyright, and Other Notices
[This section describes any necessary legal disclaimers, warranties, copyright notices, patent notice, wordmark, trademark, or logo compliance issues for the software.]

### 3.12	Applicable Standards
[This section describes by reference any applicable standard and the specific sections of any such standards which apply to the system being described. For example, this could include legal, quality and regulatory standards, industry standards for usability, interoperability, internationalization, operating system compliance, etc.]

## 4.	Supporting Information
[The supporting information makes the SRS easier to use.  It includes:
•	Table of contents
•	 Index
•	Appendices
These may include use-case storyboards or user-interface prototypes. When appendices are included, the SRS should explicitly state whether or not the appendices are to be considered part of the requirements.]
