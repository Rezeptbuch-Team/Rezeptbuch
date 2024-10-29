# Data Storage Concept
## Recipe
XML-File with custom schema

### Hash of Recipe
The hash is determined by the combination of title, servings, ingredient list, categories, cooking time and instructions using SHA256. 
So basically putting all text into the SHA256 algorithm.

Save the recipe file in the form of $hash$.xml  

### XML Format

information:
- hash of contents
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
- is_downloaded: if the recipe was downloaded or if it is created by the user
- is_published: if it has been published
- is_modified: if it has been edited and not published again
- last_published_hash: hash of the last version of the recipe that has been published
- title
- ingredient list
- servings
- categories
- cooking time

Goal:  
save as little as possible in the db to decrease redundancy/storage, but still insure functionality and performance/speed

## Application Startup actions
1. Check if there are any conflicts:
- hash of filename does not fit content -> indicates editing outside of software  
    edit entry that has the hash in the xml: set previous_hash to current hash, set is_modified to true, set id/hash to newly calculated hash
- recipe listed in database does not exist in file system -> indicates deletion or renaming  
    Search for file that has that hash saved in its information:  
              handle it as if it was modified outside of the software and rename the file to the new hash  
    If there was no match found:  
              delete it from the database (will be processed in step 2)
  
2. Check if there are any recipes whose filename/hash are not in the database.
If so ask the user if they should be included in the cookbook.
If so rename the file to $hash$.xml and insert the needed data into the database.

3. Ask the user (and on edit in the recipe editor) if he wants to upload the recipe updates (all entries where is_modified==true and is_published==true).
If so publish updates and set the is_modified attribute to false and the last_published_hash attribute to the current hash.
On the server delete the entry with the last_published_hash and insert the new recipe.
