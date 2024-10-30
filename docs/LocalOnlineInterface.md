# Interface between Application and Server
## Endpoints
### /list
#### Request  
Method: GET  
Content: {  
  offset, // from which index to get the entries (to allow for "infinite scroll")  
  count, // amount of entries/recipes to get  
  // search criterias  
  order_by: ["title", "time"],  // time refers to cooking time  
  order: ["ASC", "DESC"], 
  categories,  // list of category strings (if none are specified: include all)  
}
#### Response

### /upload
#### Request  
Method: POST  
Content: XML-file  

#### Response

### /update
#### Request  
Method: POST  
Content: {  
previous_hash,  
XML-file  
}

#### Response
