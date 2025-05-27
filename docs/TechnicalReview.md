# Technical Review
27.05.2025 xx:xx - xx:xx

## Preparation
### Participants
Julius Göler, 

### Goals/Focus
The focus of this review was to analyze and improve critical backend components related to recipe retrieval and file handling:
- LocalRecipeListService
- OnlineRecipeListService
- GetRecipeFromFileService

We selected these components because they’re essential to the application’s functionality and are the primary determinants of its performance and correctness.

### Components for the Review
 - LocalRecipeListService: Retrieves a list of available recipes from the local database for the user to choose from.
 - OnlineRecipeListService: Retrieves a list of available recipes from the remote API for the user to choose from.
 - GetRecipeFromFileService: Loads and parses recipe files from disk.

### Review criteria
| Component                | Criteria |
|--------------------------|----------|
| LocalRecipeListService   | Code quality, performance |
| OnlineRecipeListService  | Code quality, error handling |
| GetRecipeFromFileService | Code quality, reliability/error handling |

### Review methodology
Walkthrough:
 - Responsible developer presents code
 - Reviewers ask questions and suggest improvements
 - Discussion afterwards covering the review criteria

## Results
### Review outcomes
#### LocalRecipeListService

Findings:
 - The methods GetCategories() and GetIngredients() contains duplicate or at least similar code

Actions:
 - Outsource code in a different method.
 
#### OnlineRecipeListService

Findings:
  - DownloadImage(): Filestream may throw error if file does not exist.
  - GetCategories(): Json deserialization on empty json may fail

Actions:
 - add more error handling in DownloadImage() and GetCategories()

#### GetRecipeFromFile

Findings:
  - File service may throw error
  - XML reader may fail

Actions:
 - add more error handling


