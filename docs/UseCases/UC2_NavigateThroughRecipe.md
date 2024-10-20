# Navigate Through Recipe
## Brief Decription
including the change of the amount of servings (before starting the walkthrough of the recipe)

## Mockup

## Sequence Diagram

## Special Requirements

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
