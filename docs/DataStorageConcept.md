# Data Storage Concept
## Recipe
XML-File
own schema

information:
- title
- image
- description
- ingredient list
- servings
- categories
- cooking time
- instruction: seperated into steps, inline element for ingredient including amount

## Local DB
- id/key = hash of recipe
- title
- ingredient list
- servings
- categories
- cooking time
- file-link: could also save recipes with their hash as a file name, thus no file-link would be necessary

Hash of recipe: 
The hash is determined by the combination of title, servings, ingredient list, categories, cooking time and instructions using SHA256. 
So basically putting all text into the SHA256 algorithm.

Goal: 
save as little as possible in the db to decrease redundancy/storage, but still insure functionality and performance/speed


## Open Questions
How does this work together with editing recipes
