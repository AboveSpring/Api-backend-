# Api-backend-

## Endpoints

### /users
#### Description: Gets an array of all users.
#### GET
##### Example: curl http://api.softhouse.rocks/users
Result:
```{ 
    "address": {
      "geo": {
        "lat": -31.8129,
        "lng": 62.5342
      },
      "street": "Skiles Walks",
      "suite": "Suite 351",
      "city": "Roscoeview",
      "zipcode": "33263"
    },
    "_id": "5e9eb464a8eb15002609e47f",
    "name": "Nisse",
    "username": "Kamren",
    "email": "Lucio_Hettinger@annie.ca",
    "id": 380,
    "__v": 0
  }
]
```
##### 200 OK

### /users/1
#### Description: Gets a single user from /users/{userid}
#### GET
#### example: curl http://api.softhouse.rocks/users/1
Result: 
```
{
  "address": {
    "geo": {
      "lat": -37.3159,
      "lng": 81.1496
    },
    "street": "Kulas Light",
    "suite": "Apt. 556",
    "city": "Gwenborough",
    "zipcode": "92998-3874"
  },
  "_id": "5e806d9f42fbde006b6b9ec5",
  "id": 1,
  "name": "Leanne Graham",
  "username": "Bret",
  "email": "Sincere@april.biz",
  "__v": 0
}
```
#### 200 OK

### /users
#### Description: Create a post
#### POST
#### Headers: 
```"Content-Type: application/json"```

##### Body:
```
{
  "title":"Hi, World", 
  "body":"Fresh as morning dew", 
  "userId": "800"
}
```

##### Example: 
curl -X POST -H "Content-Type: application/json" http://api.softhouse.rocks/users -d '{"title":"Hi, World", "body":"Fresh as morning dew", "userId": "1"}'

Result:
```
{
  "title":"Hi, World", 
  "body":"Fresh as morning dew", 
  "userId": "800"
}
```
#### 201 Created