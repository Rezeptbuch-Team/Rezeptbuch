# Test plan

- [Test plan](#test-plan)
    - [1. Introduction](#1-introduction)
        - [1.1 Purpose](#11-purpose)
        - [1.2 Scope](#12-scope)
        - [1.3 Document Terminology and Acronyms](#13-document-terminology-and-acronyms)
    - [2. Evaluation Mission and Test Motivation](#2-evaluation-mission-and-test-motivation)
        - [2.1 Evaluation Mission](#21-evaluation-mission)
        - [2.2 Test Motivators](#22-test-motivators)
    - [3. Target Test Items](#3-target-test-items)
    - [4. Outline of Planned Tests](#4-outline-of-planned-tests)
        - [4.1 Outline of Test Inclusions](#41-outline-of-test-inclusions)
        - [4.2 Outline of Test Exclusions](#42-outline-of-test-exclusions)
    - [5. Test Approach](#5-test-approach)
        - [5.1 Testing Techniques and Types](#51-testing-techniques-and-types)
        - [5.2 Total Test Coverage](#52-total-test-coverage)
    - [6. Deliverables](#6-deliverables)
        - [6.1 Test Evaluation Summaries](#61-test-evaluation-summaries)
        - [6.2 Reporting on Test Coverage](#62-reporting-on-test-coverage)
        - [6.3 Perceived Quality Reports](#63-perceived-quality-reports)
        - [6.4 Incident Logs and Change Requests](#64-incident-logs-and-change-requests)
        - [6.5 Smoke Test Suite and Supporting Test Scripts](#65-smoke-test-suite-and-supporting-test-scripts)
    - [7. Testing Workflow](#7-testing-workflow)
    - [8. Environmental Needs](#8-environmental-needs)
        - [8.1 Base System Hardware](#81-base-system-hardware)
        - [8.2 Base Software Elements in the Test Environment](#82-base-software-elements-in-the-test-environment)
        - [8.3 Productivity and Support Tools](#83-productivity-and-support-tools)
    - [9. Risks, Dependencies, Assumptions, and Constraints](#9-risks-dependencies-assumptions-and-constraints)

## 1. Introduction

### 1.1 Purpose

The purpose of the Iteration Test Plan is to gather all of the information necessary to plan and control the test effort for a given iteration. It describes the approach to testing the software.
This Test Plan for Rezeptbuch supports the following objectives:

- Identifies the items that should be targeted by the tests.
- Identifies the motivation for and ideas behind the test areas to be covered.
- Outlines the testing approach that will be used.
  
### 1.2 Scope

This test plan will cover tests assuring the functionality of the server and the application's frontend, backend.
It will also cover the communication between the server and the application.
This document shows the following types of testing:

- Unit Testing
- Stress Testing
- Response-time Testing
- Integration Testing (API Testing)
- UI/UX Testing

### 1.3 Document Terminology and Acronyms

| Abbr | Abbreviation                        |
|------|-------------------------------------|
| API  | Application Programmable Interface  |
| CI   | Continuous Integration              |
| CD   | Continuous Delivery/Deployment      |
| n/a  | not applicable                      |
| UI   | User Interface                      |
| UX   | User Experience                     |

## 2. Evaluation Mission and Test Motivation

### 2.1 Evaluation Mission
As mentioned above testing can help identify defects, errors, and bugs early in the development process, making it easier and less expensive to fix these issues. With this testing is a crucial part of the development process.

The focus of the testing effort will be on identifying critical defects that could negatively impact the user experience, as well as identifying any potential quality risks that could impact the reliability of the application.

### 2.2 Test Motivators

The following elements will motivate the testing effort for Rezeptbuch:

1. **Quality risks and Use cases**: Testing will ensure that the application meets the desired level of quality and functionality, and will identify any areas where improvements can be made. Testing will focus on ensuring that the application meets the needs and requirements of its users.

2. **Technical risks**: The application relies on multiple subsystems and APIs, so testing will be crucial to ensure that all parts of the application are working together seamlessly.

3. **Functional requirements**: Testing will ensure that the application meets its intended functional requirements, and will identify any areas where improvements can be made to enhance its functionality.

4. **Scaling requirements**: Testing will ensure that the application can handle large amounts of recipes.

## 3. Target Test Items

The listing below identifies those test items: software, hardware, and supporting product elements that have been identified as targets for testing. This list represents what items will be tested. 

- .NET application core
- .NET Maui GUI
- API/server

## 4. Outline of Planned Tests

### 4.1 Outline of Test Inclusions

*Frontend: .NET Maui application*:

- manual UI/UX Testing
- automated UI Testing (if there is enough time)

*Application Core: .NET*:

- Unit testing
- Integration testing (API Testing)
- Stress Testing
- Response-time Testing

*API/Server: .NET*:

- Unit testing
- Integration testing
- Stress Testing
- Response-time Testing

## 5. Test Approach

### 5.1 Testing Techniques and Types

#### 5.1.1 Unit Testing

Unit testing ensures, that the tested sourcecode works as expected. Therefore small parts of the sourcecode will be tested independently.

|                        | Description                                                                                                                                        |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Technique Objective    | Ensure that each unit of code (functions, methods, classes) works as intended                                                                      |
| Technique              | Implement test methods using NUnit Framework                                                                           |
| Oracles                | Test results should be logged in CI/CD tool (GitHub Actions), and compared against expected output to determine if the tests passed or failed |
| Required Tools         | NUnit, CI/CD Pipeline                                                                    |
| Success Criteria       | All tests pass.                                                                                                                                    |
| Special Considerations | -                                                                                                                                                  |


#### 5.1.2 Manual UI Testing

UI testing evaluates the application's performance from a user's point of view, with the aim of verifying that the user interface operates as intended.

|                        | Description                                                                                                                                                                           |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Technique Objective    | Test the application from the perspective of the user                                                                                                        |
| Technique              | Manually execute common user interactions.                                                                                     |
| Oracles                | Expect that the UI elements are displayed and behave as expected during test execution. Test results are compared against expected output to determine if the tests passed or failed. |
| Required Tools         |    n/a   |
| Success Criteria       | All UI tests pass.                                                                                                                                                                    | 
| Special Considerations | -                                                                                                                                                                                     |

#### 5.1.3 Integration Testing (API Testing)

API Testing is part of integration testing. Integration tests test multiple modules of an application together. The main goal of API testing is to ensure, that the communication between application and API/server functions correctly.

|                        | Description                                                                                                                                        |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Technique Objective    | Ensure that the implemented API functions correctly and returns expected results. Ensure that the application addresses the API correctly                                                                 |
| Technique              | Implement test methods using NUnit Framework to perform HTTP requests and verify responses                                |            |
| Oracles                | Test results are logged in CI/CD tool (GitHub Actions), and compared against expected output to determine if the tests passed or failed |
| Required Tools         | NUnit, CI/CD pipelines                                                                                           |
| Success Criteria       | All tests pass.                                                                                                                                    |
| Special Considerations | APIs must be in a testable state, e.g., mock objects are used for dependencies that may not be available during tests                              |

#### 5.1.3 Stress/Response-time Testing

|                        | Description|
|------------------------|------------|
| Technique Objective    | Ensure that the application backend and the API can handle large amounts of recipes and requests in an adequate response time. |
| Technique              | Implement test methods to fill the database with recipes, make a lot of requests and register the response-time |
| Oracles                | Test results are logged in CI/CD tool (Github Actions) and compared against expected response-times to determine if the tests passed or failed |
| Required Tools         | NUnit, CI/CD pipelines |
| Success Criteria       | All tests pass in adequate response-time |
| Special Considerations | - |

### 5.2 Total Test Coverage

The total test coverage should be above 80%.

## 6. Deliverables

## 6.1 Test Evaluation Summaries
The project owns a certain amount of tests. Each pushed commit should trigger the projects CI/CD Pipeline, which builds the application and executes these tests.


## 6.2 Reporting on Test Coverage
This happens automatically on a push.

## 6.3 Perceived Quality Reports
If a build of our CI/CD Pipeline fails the administrators will be messaged. This includes a fail due to a failed test.

## 6.4 Incident Logs and Change Requests
Every time someone pushes to the main repository, the pipeline with a build will be triggered. If a build fails this is directly visible in GitHub Actions.

## 6.5 Smoke Test Suite and Supporting Test Scripts
The automated test execution in our CI/CD Pipeline enables regression testing. With this approach it is clearly visible when changes break existing functions and affect the correct behaviour of the application.

## 7. Testing Workflow
1. Local testing in the IDE
2. A Commit or Push to the main repository triggers the build and test exection in the CI/CD Pipeline
3. This triggers the pipeline (build and test)
4. Before the automated deployment the build and test stages are executed

## 8. Environmental Needs

### 8.1 Base System Hardware
The following table sets forth the system resources for the test effort presented in this Test Plan.

| Resource              | Quantity | Name and Type    |
|-----------------------|:--------:|------------------|
| CI/CD server          |    1     | GitHub Actions   |
| local test machine    |    1     |                  |

### 8.2 Base Software Elements in the Test Environment
The following base software elements are required in the test environment for this Test Plan.

| Software Element Name        | Type and Other Notes       |
|------------------------------|----------------------------|
| Visual Studio Code, Rider    | Test Explorer / Test Runner          |
| NUnit                      | testing library            |
| Moq                      | library to mock components |

### 8.3 Productivity and Support Tools
The following tools will be employed to support the test process for this Test Plan.

| Tool Category or Type | Tool Brand Name                                        |
|-----------------------|--------------------------------------------------------|
| Repository            | [github.com](http://github.com/)                       |
| CI/CD Service         | [GitHub Actions](https://github.com/features/actions)  |


## 9. Risks, Dependencies, Assumptions, and Constraints
| Risk                                     | Mitigation Strategy                                      | Contingency (Risk is realized)      |
|------------------------------------------|----------------------------------------------------------|-------------------------------------|
| Code has lots of side effects            | Refactor code (Clean Code principles)                    | publish new refactored tests        |
| Test Runner is not able to execute tests | Use standard libraries which include working Test Runner | fix test execution configuration    |
