# Show recipe
## Brief Decription
Display a comprehensive recipe overview, including a "Publish" button if the recipe was created by the current user. The overview should feature the recipe's name, a brief description, an image of the dish, a list of ingredients, and the total cooking time.

## Mockup
![ShowRecipe](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/mockups/ShowRecipeMockup.png)

## Sequence Diagram
![Show Recipe Sequence diagram](https://github.com/GermanJesus-lul/Rezeptbuch/blob/main/docs/sequence_diagrams/ShowRecipeSequenceDiagram.png)

## Special Requirements
n/a

## Pre-Conditions
* Recipes are stored locally: All recipes must already be saved on the local storage of the .NET MAUI application.
* Application is running: The .NET MAUI application is open and ready for interaction.
* User has selected a recipe: The user has successfully chosen a specific recipe from the available local list.
* Recipe contains necessary information: The selected recipe has all required details like ingredients, preparation steps, and image.

## Post-Conditions
* Recipe is displayed: The full recipe details, including the name, image, list of ingredients, required time, and description, are shown to the user.
* No publish button displayed (if downloaded): If the recipe was not created by the user (it was downloaded from the database), the publish button is not displayed.
* Optional actions enabled: The user can proceed with further actions such as adjusting servings or starting the step-by-step walkthrough for preparing the recipe.

## Story Point Estimate
5
