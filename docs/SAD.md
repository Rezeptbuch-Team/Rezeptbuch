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


## 6. Process View


## 7. Deployment View


## 8. Implementation View

### 8.1 Overview


### 8.2 Layers


## 9. Data View (optional)


## 10. Size and Performance


## 11. Quality
