# Architecture Significant Requirements (ASR)
## Utility Tree
|Quality Attribute|Refinement|Quality Attribute Scenarios|Business Value|Technical Risk|
|-----------------|----------|---------------------------|--------------|--------------|
|Performance|Local list response time|A list of local recipes should load in less than 0.5 seconds when opening the page or adjusting filter options|H|M|
|    |Online list response time|A list of online recipes should load in less than 1.5 seconds when opening the page or adjusting filter options|M|H|
|Testability|TDD/Testing frameworks|Implement testing frameworks and follow TDD to ensure comprehensive automated tests and maintain code quality|H|M|
|Maintainability|Code modularity|The codebase should be structured modularly to support easy updates and the integration of new features|H|M|
|Usability|Intuitive design|The interface should be intuitive, requiring no formal training for new users|H|L|
|Security|Data integrity|Ensure recipe data is not lost or corrupted during updates or syncing|H|M|
|Availability|Offline access|Users should be able to view and search saved/local recipes offline|H|M|
|Scalability|Recipe data capacity|Efficiently manage and query up to 1 million stored recipes|M|H|

## Architectural Decisions
- TDD/Mocking
- Dependency Injection/Modularity (OCP)
- MVVM in the frontend
- Separation of concerns in the application logic (SRP)
- Decoupling of the application and the server, only communicating through a REST-API
- Consistent UI/UX patterns
- Ensure data integrity through the use of hashes
- Local data storage and database to support offline access

