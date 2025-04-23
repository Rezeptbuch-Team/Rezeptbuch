# Data Storage Concept
## Local Storage path
```cs
Environment.SpecialFolder.ApplicationData
```

bzw. %AppData%

## Recipe
XML-File with custom schema

### Hash of Recipe
The hash is determined by the combination of title, servings, ingredient list, categories, cooking time and instructions using SHA256. 
So basically putting all text into the SHA256 algorithm.

Standard: Save the recipe file in the form of $hash$.xml  
Dont save recipe files created by the user in that format

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
- instructions: seperated into steps, inline element for ingredient including amount

## Upload/Update concept
Using the online features must be activated by the user.
Upon activation, a UUID is generated and stored on the user’s PC.

This UUID serves as the user's identification when uploading or updating recipes.
It is not disclosed when retrieving recipes, but is only stored in the remote database.
When uploading a recipe, the UUID must be sent along.
When updating a recipe, the UUID must also be included.
The server then checks whether it matches the one of the original uploader.

## Local DB
- id/key = hash of recipe
- is_downloaded: if the recipe was downloaded or if it is created by the user
- is_published: if it has been published
- is_modified: if it has been edited and not published again
- last_published_hash: hash of the last version of the recipe that has been published
- title
- description
- image path
- ingredient list
- categories
- cooking time
- filepath

Goal:  
save as little as possible in the db to decrease redundancy/storage, but still insure functionality and performance/speed
(e.g. recipe steps can be kept in the xml files, because they are not used when listing recipes)

[DBML](localDB.dbml)
[dbdiagram](https://dbdiagram.io/d/Rezeptbuch-local-DB-67f64ce44f7afba184ed8cd3)
![Rezeptbuch local DB](https://github.com/user-attachments/assets/0777ae6a-98f9-456e-9177-a23b1300c7f1)


## Remote DB
recommendation (may be changed by the server team)

- id/key = hash of recipe
- uploader UUID
- title
- description
- image path
- categories
- cooking time
- filepath


## Application Startup actions
1. Check if there are any conflicts:
- hash of recipe does not fit content -> indicates editing outside of software  
    edit entry that has the hash in the xml: set previous_hash to current hash, set is_modified to true, set id/hash to newly calculated hash
- recipe listed in database does not exist in file system -> indicates deletion or renaming  
    Search for file that has that hash saved in its information:  
        ->handle it as if it was modified outside of the software
    If there was no match found:  
        ->if is_published==false delete it from the database (will be processed in step 2)
        ->if is_published==true (not sure yet. probably can be deleted from the DB too)
  
2. Check if there are any recipes whose filename/hash are not in the database.
If so ask the user if they should be included in the cookbook.
If so insert the needed data into the database.

3. Ask the user (and on edit in the recipe editor) if he wants to upload the recipe updates (all entries where is_modified==true and is_published==true).
If so publish updates and set the is_modified attribute to false and the last_published_hash attribute to the current hash.
On the server delete the entry with the last_published_hash and insert the new recipe.
