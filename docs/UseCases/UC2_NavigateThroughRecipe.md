# Navigate Through Recipe
## Brief Decription
Allow the user to navigate step-by-step through the cooking instructions of a selected recipe. Before starting the recipe walkthrough, the user has the option to adjust the number of servings. Based on the serving size selected, the application automatically updates the ingredient quantities. The user can then proceed through the recipe steps in a guided manner, following the instructions one step at a time.

## Mockup
![NavigateRecipe](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/mockups/NavigateThroughRecipeMockup.png)

## Sequence Diagram
![Navigate Through Recipe sequence diagram](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/sequence_diagrams/NavigateThroughRecipeSequenceDiagram.png)

## Special Requirements
n/a

## Pre-Conditions
* Recipes are stored locally: All recipes must be stored locally in the .NET MAUI application and must be accessible for loading.
* Application is running: The .NET MAUI application is open and the user has access to the recipe list.
* User has selected a recipe: The user has chosen a recipe from the available list of recipes.
* Recipe contains all necessary data: The selected recipe contains all required information, such as ingredients, preparation steps, and default serving sizes.
* User can specify the servings: The application provides an interface allowing the user to input the desired number of servings.

## Post-Conditions
* Servings are set: The user has successfully specified the desired number of servings, and the ingredient quantities have been adjusted accordingly.
* Step-by-step walkthrough started: The user has started the step-by-step walkthrough of the recipe, and the initial step is displayed.
* Ingredient quantities adjusted: Ingredient quantities have been adjusted according to the selected number of servings and are displayed to the user.
* Recipe navigation completed: The user has navigated through all the recipe steps until the final step is reached.
* Completion summary shown: A completion summary or message is shown to the user once the recipe walkthrough is finished.

## Story Point Estimate
7
