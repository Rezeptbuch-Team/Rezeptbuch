# Interface between Application and Server
## Endpoints
### /list
#### Request  
Method: GET  

Required URL-parameters:  
- offset
- count

Optional URL-parameters:
- order_by  
    possible values: "title", "cooking_time"  
    default: "title" 
- order  
      possible values: "ASC", "DESC"   
      default: "ASC"
- categories  
     comma-seperated list of strings

Example:
https://url.com/list?offset=0&count=15&order_by=cooking_time&order=DESC&categories=mexican,gluten-free,vegan


#### Response
Status Code: 200  
Content-Type: application/json  
Content: Json list of recipes (the information of each recipe (e.g. title, description) is saved in key-value-pairs)  

### /upload
#### Request  
Method: POST  
Content-Type: application/xml  
Content: XML-file  

#### Response
Status Code: 201  
Content: "success"

### /update
#### Request  
Method: POST  
Content-Type: application/json  
Content: {   
previous_hash,  
XML-file  
}

#### Response
Status Code: 200  
Content: "success"
