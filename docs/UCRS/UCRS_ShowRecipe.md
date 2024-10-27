## Table of contents
- [Table of contents](#table-of-contents)
- [Introduction](#1-introduction)
    - [Purpose](#11-purpose)
    - [Scope](#12-scope)
    - [Definitions, Acronyms and Abbreviations](#13-definitions-acronyms-and-abbreviations)
    - [References](#14-references)
    - [Overview](#15-overview)
- [Flow of Events—Design](#2-flow-of-eventsdesign)
- [Derived Requirements](#3-derived-requirements)

## 1. Introduction
### 1.1 Purpose
The purpose of this use case is to show the user an overview of a recipe and allow him to publish the recipe.

### 1.2 Scope
This use case is related to the "List local recipes" use case, through which you get to this use case.

### 1.3 Definitions, Acronyms, and Abbreviations
n/a

### 1.4 References
[Blog](https://github.com/GermanJesus-lul/Rezeptbuch/discussions)

[Github](https://github.com/GermanJesus-lul/Rezeptbuch/)

### 1.5 Overview
In the following the flow of events for this use case is explained, supported by a sequence diagram.

## 2. Flow of Events—Design 
![](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/sequence_diagrams/ShowRecipeSequenceDiagram.png)

1. View Recipe:
   The user wants to get the overview of the recipe
2. Check Recipe Source:
    It is checked if the recipe was published or if it is a local/private recipe
3. Show Publish Button:
   If it is a local/private recipe a publish button is shown
4. Click Publish:
   The user wants to publish the recipe
5. Send Recipe data:
   The recipe data is sent to the server
6. Validate and Save Recipe:
   The recipe data is being validated and then saved to the list of online recipes
7. Show Publish Success Message:
   A dialog is displayed to the user if the publish action was successful or not
