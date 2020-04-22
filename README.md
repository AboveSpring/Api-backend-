# Api-backend-

## Endpoints for /users and /posts
#### /users dont have DELETE and PATCH

#### Body example for users:
```
{
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
```
#### Body example for posts:
```
{
  "title": "string",
  "body": "string",
  "userId": 0
}
```
-------------------------------------------------------------------
### /users
#### Method: GET
Description: Gets an array of all users.
##### Example: curl http://api.softhouse.rocks/users
Result:
```
{
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
```
##### 200 OK
-------------------------------------------------------------------
### /users/1
#### Method: GET
Description: Gets a single user from /users/{userid}
#### Example: curl http://api.softhouse.rocks/users/1
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
    "city": "Shire",
    "zipcode": "92998-3874"
  },
  "_id": "5e806d9f42fbde006b6b9ec5",
  "id": 1,
  "name": "Frodo Baggins",
  "username": "Bret",
  "email": "Sincere@april.biz",
  "__v": 0
}
```
##### 200 OK
-------------------------------------------------------------------
### /users
#### Method: POST
Description: Create a user
#### Headers:
```"Content-Type: application/json"```

##### Body:
```
'{
  "address": {
    "geo": {
      "lat": -37.3159,
      "lng": 81.1496
    },
    "street": "Kulas Light",
    "suite": "Apt. 556",
    "city": "Shire",
    "zipcode": "92998-3874"
  },
  "_id": "5e806d9f42fbde006b6b9ec5",
  "id": 1,
  "name": "Frodo Baggins",
  "username": "Bret",
  "email": "Sincere@april.biz",
  "__v": 0
}'
```

##### Example:
curl -i -X POST -H "Content-Type:application/json" http://api.softhouse.rocks/users -d '{
  "address": {
    "geo": {
      "lat": -37.3159,
      "lng": 81.1496
    },
    "street": "Kulas Light",
    "suite": "Apt. 556",
    "city": "Shire",
    "zipcode": "92998-3874"
  },
  "_id": "5e806d9f42fbde006b6b9ec5",
  "id": 1,
  "name": "Frodo Baggins",
  "username": "Bret",
  "email": "Sincere@april.biz",
  "__v": 0
}'

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
    "city": "Shire",
    "zipcode": "92998-3874"
  },
  "_id": "5e806d9f42fbde006b6b9ec5",
  "id": 1,
  "name": "Frodo Baggins",
  "username": "Bret",
  "email": "Sincere@april.biz",
  "__v": 0
}
```
##### 201 Created
-------------------------------------------------------------------
### /users/{userId}
#### Method: PUT
Description: Replace a user
#### Headers:
```"Content-Type: application/json"```

##### Body:
```
{
  "address": {
    "geo": {
      "lat": 0,
      "lng": 0
    },
    "street": "string",
    "suite": "string",
    "city": "string",
    "zipcode": "string"
  },
  "_id": "5e806d9f42fbde006b6b9ece",
  "id": 10,
  "name": "string",
  "username": "string",
  "email": "string",
  "__v": 0
}

```
##### Example:
curl -i -X PUT -H "Content-Type:application/json" http://api.softhouse.rocks/users/50 -d '{
  "address": {
    "geo": {
      "lat": -37.3159,
      "lng": 81.1496
    },
    "street": "Kulas Light",
    "suite": "Apt. 556",
    "city": "Shire",
    "zipcode": "92998-3874"
  },
  "_id": "5e806d9f42fbde006b6b9ec5",
  "id": 1,
  "name": "Frodo Baggins",
  "username": "Bret",
  "email": "Sincere@april.biz",
  "__v": 0
}'

Result:
```
'{
  "address": {
    "geo": {
      "lat": -37.3159,
      "lng": 81.1496
    },
    "street": "Kulas Light",
    "suite": "Apt. 556",
    "city": "Shire",
    "zipcode": "92998-3874"
  },
  "_id": "5e806d9f42fbde006b6b9ec5",
  "id": 1,
  "name": "Frodo Baggins",
  "username": "Bret",
  "email": "Sincere@april.biz",
  "__v": 0
}'
```
##### 200 OK
-------------------------------------------------------------------
### /posts/{postId}
#### Method: PATCH
Description: Update a post
#### Headers:
```"Content-Type: application/json"```

##### Body:
{
  "title": "string",
  "body": "string",
  "userId": 0
}
##### Example:
curl -i -X PATCH -H "Content-Type:application/json" http://api.softhouse.rocks/posts/10 -d '{ "title": "Lord of the Rings",
  "body": "Gollum",
  "userId": 0
}'

Result:
```
{
  "n": 1,
  "nModified": 0,
  "opTime": {
    "ts": "6818464584756625409",
    "t": 139
  },
  "electionId": "7fffffff000000000000008b",
  "ok": 1,
  "operationTime": "6818464584756625409",
  "$clusterTime": {
    "clusterTime": "6818464584756625409",
    "signature": {
      "hash": "AAAAAAAAAAAAAAAAAAAAAAAAAAA=",
      "keyId": 0
    }
  }
}
```
##### 200 OK
-------------------------------------------------------------------
### /posts/{postId}
#### Method: DELETE
Description: Delete a post

##### Example: 
curl -i -X DELETE http://api.softhouse.rocks/posts/10

Result:
##### 200 OK