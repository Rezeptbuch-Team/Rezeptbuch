# Interface between Application and Server
# Deprecated. New: API_Specification
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
      possible values: "asc", "desc"   
      default: "asc"
- categories  
     comma-seperated list of strings

Example:
https://url.com/list?offset=0&count=15&order_by=cooking_time&order=DESC&categories=mexican,gluten-free,vegan


#### Response
Status Code: 200  
Headers: Content-Type: application/json  
Body: Json list of recipes (the information of each recipe (e.g. title, description) is saved in key-value-pairs)  

##### Example Body:
{  
"recipes": [{  
"hash": "asdafc",  
"title": "title1",  
"description": "description1",  
"image_path": "imagePath1",  
"categories": ["category1", "category2"],  
"cooking_time": 15  
},  
{  
"hash": "asdafc",  
"title": "title2",  
"description": "description2",  
"image_path": "imagePath2",  
"categories": ["category3", "category4"],  
"cooking_time": 45  
}]    
}"


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
