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
The purpose of this use case is to let a user navigate and follow a recipe step by step.

### 1.2 Scope
This use case is related to the "Show recipe" use case, as that is the use case before the "Navigate through recipe" use case.

### 1.3 Definitions, Acronyms, and Abbreviations
n/a


### 1.4 References
[Blog](https://github.com/GermanJesus-lul/Rezeptbuch/discussions)

[Github](https://github.com/GermanJesus-lul/Rezeptbuch/)

### 1.5 Overview
In the following the flow of events for this use case is explained, supported by a sequence diagram.

## 2. Flow of Events—Design 
![](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/sequence_diagrams/NavigateThroughRecipeSequenceDiagram.png)

1. Select Recipe:
    The user selects the recipe
2. Load Recipe Data:
    The local recipe gets loaded into the application
3. Start Walkthrough:
    The user starts the walkthrough
4. Display Step 1:
    The first instruction step is displayed to the user
5. Next Step:
    The user wants to see the next step
6. Display Next Step:
    The next step is displayed to the user

Steps 4 to 6 are repeated until no steps are left.

7. Complete Walkthrough
    The user ends the walkthrough on the last step
8. Show Completion Message
    A completion message is displayed to the user
