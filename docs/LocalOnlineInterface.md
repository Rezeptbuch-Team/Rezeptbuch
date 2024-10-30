# Interface between Application and Server
## Endpoints
### /list
Request
Method: GET
Content: {
  offset, // from which index to get the entries (to allow for "infinite scroll")
  count // amount of entries/recipes to get
  // search criterias  
}

### /upload
Request
Method: POST
Content: XML-file

### /update
Request
Method: POST
Content: {
previous_hash,  
XML-file 
}
