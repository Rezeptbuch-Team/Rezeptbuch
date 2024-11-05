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
Headers: Content-Type: application/json  
Body: Json list of recipes (the information of each recipe (e.g. title, description) is saved in key-value-pairs)  

### /upload
#### Request  
Method: POST  
Headers: Content-Type: application/xml  
Body: XML-file  

#### Response
Status Code: 201  
Body: "success"

### /update
#### Request  
Method: POST  
Headers: {  
Content-Type: application/xml,   
Previous-Hash: "previous_hash"  
}  
Body: XML-file

#### Response
Status Code: 200  
Body: "success"
