---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='https://github.com/katerinapat/users-api-rh'>Feel free to fork the project on Github</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the users API rh! You can use the API to access user API endpoints, which can get information on various informations regarding to a user, such as his location, pictures of him and any available contact information.

You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.


# Authentication


users API rh is public to the world. 
So you are allowed to access API endpoints without authenication


# Users

## Get All Users


```shell
curl https://users-api-rh.herokuapp.com/api/v1/users
  
```

> The above command returns JSON structured like this:

```json
{  
   "object":{  
      "id":1,
      "gender":"female",
      "title":"miss",
      "first_name":"alison",
      "last_name":"reid",
      "email":"alison.reid@example.com",
      "username":"tinywolf709",
      "password":"rockon",
      "salt":"lypI10wj",
      "md5":"bbdd6140e188e3bf68ae7ae67345df65",
      "sha1":"4572d25c99aa65bbf0368168f65d9770b7cacfe6",
      "sha256":"ec0705aec7393e2269d4593f248e649400d4879b2209f11bb2e012628115a4eb",
      "registered":null,
      "dob":932871968,
      "phone":"031-541-9181",
      "cell":"081-647-4650",
      "PPS":"3302243T"
   },
   "locations":[  
      {  
         "id":1,
         "street":"1097 the avenue",
         "city":"Newbridge",
         "state":"ohio",
         "zip":28782,
         "user_id":1
      }
   ],
   "pictures":[  
      {  
         "id":1,
         "user_id":1,
         "large":"https://randomuser.me/api/portraits/women/60.jpg",
         "medium":"https://randomuser.me/api/portraits/med/women/60.jpg",
         "thumbnail":"https://randomuser.me/api/portraits/thumb/women/60.jpg"
      }
   ]
}


```

This endpoint retrieves all users.

### HTTP Request

`GET https://users-api-rh.herokuapp.com/api/v1/users`


## Get a Specific User



```shell
curl https://users-api-rh.herokuapp.com/api/v1/users/1
```

> The above command returns JSON structured like this:

```json
{  
   "object":{  
      "id":1,
      "gender":"female",
      "title":"miss",
      "first_name":"alison",
      "last_name":"reid",
      "email":"alison.reid@example.com",
      "username":"tinywolf709",
      "password":"rockon",
      "salt":"lypI10wj",
      "md5":"bbdd6140e188e3bf68ae7ae67345df65",
      "sha1":"4572d25c99aa65bbf0368168f65d9770b7cacfe6",
      "sha256":"ec0705aec7393e2269d4593f248e649400d4879b2209f11bb2e012628115a4eb",
      "registered":null,
      "dob":932871968,
      "phone":"031-541-9181",
      "cell":"081-647-4650",
      "PPS":"3302243T"
   },
   "locations":[  
      {  
         "id":1,
         "street":"1097 the avenue",
         "city":"Newbridge",
         "state":"ohio",
         "zip":28782,
         "user_id":1
      }
   ],
   "pictures":[  
      {  
         "id":1,
         "user_id":1,
         "large":"https://randomuser.me/api/portraits/women/60.jpg",
         "medium":"https://randomuser.me/api/portraits/med/women/60.jpg",
         "thumbnail":"https://randomuser.me/api/portraits/thumb/women/60.jpg"
      }
   ]
}
```

This endpoint retrieves a specific user.

### HTTP Request

`GET https://users-api-rh.herokuapp.com/api/v1/users/<ID>`

### URL Parameters

Parameter | Type | Description
--------- | ----------- | -----------
ID | string | The ID of the user to retrieve

## Create a User


```shell
curl --data "first_name=katerina" https://users-api-rh.herokuapp.com/api/v1/users/
```

> The above command returns JSON structured like this:

```json
{  
   "status":200,
   "message":"User with ID::ID created successfully"
}
```

This endpoint create a new instance of a user.

### HTTP Request

`POST https://users-api-rh.herokuapp.com/api/v1/users/PARAMETERS`

### Query Parameters 


Parameter | Type | Description
--------- | ----------- | ----------
title | string | The title of the user
first_name | string | The name of the user
last_name | string | The last name of the user
registered | integer | When the user is registered
street | string | street of the user
city | string | the city of the user

## Update a User


```shell
curl -X PUT -d title=mrs  -d first_name=katerina https://users-api-rh.herokuapp.com/api/v1/users/1
```

> The above command returns JSON structured like this:

```json
{  
   "status":200,
   "message":"User with ID:1 updated successfully"
}
```

This endpoint update a specific fields of the user.

### HTTP Request

`PUT https://users-api-rh.herokuapp.com/api/v1/users/PARAMETERS`

### Query Parameters 


Parameter | Type | Description
--------- | ----------- | ----------
id        | integer | The ID of the user that will update
last_name | string | Updates the last name of the user
email | string | Updates the last name of the user

## Delete a specific User


```shell
curl -X "DELETE" https://users-api-rh.herokuapp.com/api/v1/users/:ID
```

> The above command returns JSON structured like this:

```json
{  
   "status":200,
   "message":"User with ID::ID deleted successfully"
}
```

This endpoint update a specific fields of the user.

### HTTP Request

`DELETE https://users-api-rh.herokuapp.com/api/v1/users/PARAMETERS`

### Query Parameters 


Parameter | Type | Description
--------- | ----------- | ----------
id        | integer | The ID of the user that will be deleted

# Search 

## Search query


```shell
curl https://users-api-rh.herokuapp.com/api/v1/users/search?q=wal
  
```

> The above command returns JSON structured like this:

```json
[  
   {  
      "object":{  
         "id":40,
         "gender":"male",
         "title":"mr",
         "first_name":"john",
         "last_name":"wallace",
         "email":"john.wallace@example.com",
         "username":"yellowelephant285",
         "password":"infantry",
         "salt":"eF2hvNgI",
         "md5":"4424816b186a17e53f6ab411294dd993",
         "sha1":"78c5b05999b876a093d329a4235d0902fd89c23f",
         "sha256":"3ef7321aa09b09eeba37225be12475c44330b94c3f55fe646398e986823df20f",
         "registered":null,
         "dob":962253785,
         "phone":"011-317-5827",
         "cell":"081-087-0635",
         "PPS":"5633289T"
      },
      "locations":[  
         {  
            "id":40,
            "street":"7348 the avenue",
            "city":"Tuam",
            "state":"illinois",
            "zip":52871,
            "user_id":40
         }
      ],
      "pictures":[  
         {  
            "id":40,
            "user_id":40,
            "large":"https://randomuser.me/api/portraits/men/24.jpg",
            "medium":"https://randomuser.me/api/portraits/med/men/24.jpg",
            "thumbnail":"https://randomuser.me/api/portraits/thumb/men/24.jpg"
         }
      ]
   },
   {  
      "object":{  
         "id":46,
         "gender":"male",
         "title":"mr",
         "first_name":"walter",
         "last_name":"smythe",
         "email":"walter.smythe@example.com",
         "username":"heavybutterfly622",
         "password":"sucking",
         "salt":"9vxGlFWX",
         "md5":"74605c416e65880e0c6e18507503f561",
         "sha1":"d3542f1cd948dff7156b3b4a822fb2bc8472ef4d",
         "sha256":"6007eb13dd433b4d023b5938a7e37455c0f925c590e29fcc355afbc1dd723c40",
         "registered":null,
         "dob":765400665,
         "phone":"031-245-1812",
         "cell":"081-917-4018",
         "PPS":"4491944T"
      },
      "locations":[  
         {  
            "id":46,
            "street":"8485 boghall road",
            "city":"Kildare",
            "state":"rhode island",
            "zip":50269,
            "user_id":46
         }
      ],
      "pictures":[  
         {  
            "id":46,
            "user_id":46,
            "large":"https://randomuser.me/api/portraits/men/91.jpg",
            "medium":"https://randomuser.me/api/portraits/med/men/91.jpg",
            "thumbnail":"https://randomuser.me/api/portraits/thumb/men/91.jpg"
         }
      ]
   }
]


```

This endpoint search and retrieves all users that their first name or last name match the query.

### HTTP Request

`GET https://users-api-rh.herokuapp.com/api/v1/users/search?q=query`

### Query Parameters 


Parameter | Type | Description
--------- | ----------- | ----------
q        | string | Search with the value of this parameter

# Filter 

## Sort


```shell
curl https://users-api-rh.herokuapp.com/api/v1/users?sort
  
```

> The above command returns JSON structured like this:

```json

```

This endpoint sort the users based on the params. If params are not set,
users are sorted by default ascending by their first name.

### HTTP Request

`GET https://users-api-rh.herokuapp.com/api/v1/users?sort=column&by=asc`

### Query Parameters 


Parameter | Type | Default | Available Params 
--------- | ----------- | ---------- | ---------- 
sort      | string | first_name | first_name, last_name, username
by        | string | ASC | asc, desc