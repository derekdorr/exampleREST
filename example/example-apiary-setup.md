FORMAT: 1A
HOST: http://www.google.com

# ExampleREST
An attempt at a standard for RESTful APIs.

## Example Endpoints [/]
### Parent-est Endpoint [GET]

+ Response 200 (application/json)

    + Body
    
            {
                "request" : {
                    "method" : "GET"
                },
                "links" : [
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/"
                    },
                    {
                        "rel" : "schema",
                        "href" : "https://examplerest.apiary-mock.com/schema"
                    },
                    {
                        "rel" : "v1",
                        "description" : "Collection of V1 APIs",
                        "href" : "https://examplerest.apiary-mock.com/v1"
                    }
                ],
                "actions" : [
                    {
                        "method": "GET",
                        "href": "https://examplerest.apiary-mock.com"
                    }
                ]
            }
            
## Example Endpoints Schema [/schema]
### Example Endpoints Schema [GET]

+ Response 200 (application/json)

    + Body
    
            {
                "request" : {
                    "method" : "GET"
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com/"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/schema"
                    },
                    {
                        "rel" : "get",
                        "href" : "https://examplerest.apiary-mock.com/schema/get"
                    }
                ],
                "actions" : [
                    {
                        "method" : "GET",
                        "href" : "https://examplerest.apiary-mock.com/schema"
                    }
                ]
            }
            
## Example Endpoints GET Schemas [/schema/get]
### Example Endpoints GET Schemas [GET]

+ Response 200 (application/json)

    + Body
    
            {
                "request" : {
                    "method" : "GET"
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com/schema"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/schema/get"
                    },
                    {
                        "rel" : "200",
                        "description" : "Success",
                        "href" : "https://examplerest.apiary-mock.com/schema/get/200"
                    }
                ],
                "actions" : [
                    {
                        "method" : "GET",
                        "href" : "https://examplerest.apiary-mock.com/schema/get"
                    }
                ]
            }
            
## Example Endpoints 200 GET Schema [/schema/get/200]
### GET Schema [GET]

+ Response 200

    + Body

            {
                "request" : {
                    "method" : "GET"
                },
                "properties" : {
                    "schema" : {
                        "type":"object",
                        "required" : ["actions","links","request"],
                        "properties":{
                            "actions": {
                                "type":"array",
                                "items":
                                    {
                                        "type":"object",
                                        "required" : ["href","method"],
                                            "properties":{
                                            "href": {
                                                "type":"string"
                                            },
                                            "method": {
                                                "type":"string"
                                            }
                                        }
                                    }
                            },
                            "links": {
                                "type":"array",
                                "items":
                                    {
                                        "type":"object",
                                        "required" : ["href","rel"],
                                        "properties":{
                                            "href": {
                                                "type":"string"
                                            },
                                            "rel": {
                                                "type":"string"
                                            }
                                        }
                                    }
                            },
                            "request": {
                            "type":"object",
                                "required":["method"],
                                "properties":{
                                    "method": {
                                        "type":"string"
                                    }
                                }
                            }
                        }
                    }
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com/schema/get"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/schema/get/200"
                    }
                ],
                "actions" : [
                    {
                        "method" : "GET",
                        "href" : "https://examplerest.apiary-mock.com/schema/get/200"
                    }
                ]
            }

## Example V1 [/v1]
### V1 Collection [GET]

+ Response 200 (application/json)

    + Body
    
            {
                "request" : {
                    "method" : "GET"
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/v1"
                    },
                    {
                        "rel" : "users",
                        "description" : "Users API",
                        "href" : "https://examplerest.apiary-mock.com/v1/users"
                    }
                ],
                "actions" : [
                    {
                        "method": "GET",
                        "href": "https://examplerest.apiary-mock.com/v1"
                    }
                ]
            }
            
## Example Users [/v1/users]
### Users API [GET]

+ Response 200 (application/json)

    + Body
    
            {
                "request" : {
                    "method" : "GET"
                },
                "properties" : {
                    "count" : 2000,
                    "verified" : 1492
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com/v1"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/v1/users"
                    },
                    {
                        "rel" : "specify",
                        "description" : "Retrieve general information about a specific user",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/{userId}",
                        "params" : [
                            {
                                "name" : "userId",
                                "type" : "number",
                                "description" : "Unique user identifier"
                            }
                        ]
                    }
                ],
                "actions": [
                    {
                        "method": "GET",
                        "description" : "Return high-level users information.",
                        "href": "https://examplerest.apiary-mock.com/v1/users"
                    },
                    {
                        "method": "POST",
                        "description" : "Create a new user",
                        "href" : "https://examplerest.apiary-mock.com/v1/users",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "firstName",
                                "description" : "User first name.",
                                "type" : "string"
                            },
                            {
                                "name" : "lastName",
                                "description" : "User last name.",
                                "type" : "string"
                            },
                            {
                                "name" : "favoriteBand",
                                "description" : "User's favorite band.",
                                "type" : "string"
                            },
                            {
                                "name" : "isCool",
                                "description" : "Indicator of whether the user is cool.",
                                "type" : "boolean"
                            }
                        ]
                    }
                ]
            }
            
### Create Users API [POST]

+ Request (application/json)
    
    + Body
    
            {
                "firstName" : "Derek",
                "lastName" : "Dorr",
                "favoriteBand" : "The Octogenarian Throat Singers",
                "isCool" : true
            }

+ Response 200 (application/json)

    + Body
    
            {
                "request" : {
                    "method" : "POST",
                    "data" : {
                        "firstName" : "Derek",
                        "lastName" : "Dorr",
                        "favoriteBand" : "The Octogenarian Throat Singers",
                        "isCool" : true
                    }
                },
                "properties" : {
                    "firstName" : "Derek",
                    "lastName" : "Dorr",
                    "favoriteBand" : "The Octogenarian Throat Singers",
                    "isCool" : true,
                    "coolnessLevel" : 9001,
                    "verified" : false,
                    "userId" : 2001
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com/v1"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/v1/users"
                    },
                    {
                        "rel" : "specify",
                        "description" : "Retrieve general information about a specific user",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/{userId}",
                        "params" : [
                            {
                                "name" : "userId",
                                "type" : "number",
                                "description" : "Unique user identifier",
                                "value" : 2001
                            }
                        ]
                    }
                ],
                "actions": [
                    {
                        "method": "GET",
                        "description" : "Return high-level users information.",
                        "href": "https://examplerest.apiary-mock.com/v1/users"
                    },
                    {
                        "method": "POST",
                        "description" : "Create a new user",
                        "href" : "https://examplerest.apiary-mock.com/v1/users",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "firstName",
                                "description" : "User first name.",
                                "type" : "string"
                            },
                            {
                                "name" : "lastName",
                                "description" : "User last name.",
                                "type" : "string"
                            },
                            {
                                "name" : "favoriteBand",
                                "description" : "User's favorite band.",
                                "type" : "string"
                            },
                            {
                                "name" : "isCool",
                                "description" : "Indicator of whether the user is cool.",
                                "type" : "boolean"
                            }
                        ]
                    }
                ]
            }

## User Drilldown [/v1/users/{userId}]
### Drilldown to User [GET]

+ Response 200 (application/json)

    + Body
    
            {
                "request" : {
                    "method" : "GET",
                    "params" : [
                        {
                            "name": "userId",
                            "value": 2001
                        }
                    ]
                },
                "properties" : {
                    "firstName" : "Derek",
                    "lastName" : "Dorr",
                    "favoriteBand" : "The Octogenarian Throat Singers",
                    "isCool" : true,
                    "coolnessLevel" : 9001,
                    "verified" : false,
                    "userId" : 2001
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com/v1/users"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001"
                    },
                    {
                        "rel" : "profile",
                        "description" : "Retrieve user profile information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/profile"
                    },
                    {
                        "rel" : "account",
                        "description" : "Retrieve user account information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/account"
                    }
                ],
                "actions": [
                    {
                        "method": "GET",
                        "description" : "Return specific user information.",
                        "href": "https://examplerest.apiary-mock.com/v1/users/2001"
                    },
                    {
                        "method": "PUT",
                        "description" : "Update user",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "firstName",
                                "description" : "User first name.",
                                "type" : "string"
                            },
                            {
                                "name" : "lastName",
                                "description" : "User last name.",
                                "type" : "string"
                            },
                            {
                                "name" : "favoriteBand",
                                "description" : "User's favorite band.",
                                "type" : "string"
                            },
                            {
                                "name" : "isCool",
                                "description" : "Indicator of whether the user is cool.",
                                "type" : "boolean"
                            }
                        ]
                    },
                    {
                        "method" : "DELETE",
                        "description" : "Delete user.",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001"
                    }
                ]
            }
            
+ Response 404 (application/json)

    + Body
    
            {
                "request" : {
                    "method" : "GET",
                    "params" : [
                        {
                            "name": "userId",
                            "value": 2002
                        }
                    ]
                },
                "fault" : {
                    "reason":404,
                    "message": "User not found."
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com/v1/users"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2002"
                    }
                ]
            }
            
### Update user information [PUT]

+ Response 200 (application/json)

    + Body
            
            {
                "request" : {
                    "method" : "PUT",
                    "data" : {
                        "firstName" : "Derek",
                        "lastName" : "Dorr",
                        "favoriteBand" : "The Octogenarian Throat Singers",
                        "isCool" : true,
                        "coolnessLevel" : 9001,
                        "verified" : false,
                    }
                },
                "properties" : {
                    "firstName" : "Derek",
                    "lastName" : "Dorr",
                    "favoriteBand" : "The Octogenarian Throat Singers",
                    "isCool" : true,
                    "coolnessLevel" : 9001,
                    "verified" : false,
                    "userId" : 2001
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com/v1/users"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001"
                    },
                    {
                        "rel" : "profile",
                        "description" : "Retrieve user profile information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/profile"
                    },
                    {
                        "rel" : "account",
                        "description" : "Retrieve user account information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/account"
                    }
                ],
                "actions": [
                    {
                        "method": "GET",
                        "description" : "Return specific user information.",
                        "href": "https://examplerest.apiary-mock.com/v1/users/2001"
                    },
                    {
                        "method": "PUT",
                        "description" : "Update user",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "firstName",
                                "description" : "User first name.",
                                "type" : "string"
                            },
                            {
                                "name" : "lastName",
                                "description" : "User last name.",
                                "type" : "string"
                            },
                            {
                                "name" : "favoriteBand",
                                "description" : "User's favorite band.",
                                "type" : "string"
                            },
                            {
                                "name" : "isCool",
                                "description" : "Indicator of whether the user is cool.",
                                "type" : "boolean"
                            }
                        ]
                    },
                    {
                        "method" : "DELETE",
                        "description" : "Delete user.",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001"
                    }
                ]
            }
            
### Delete user [DELETE]

+ Response 200 (application/json)

    + Body
    
            {
                "request" : {
                    "method" : "DELETE"
                },
                "properties" : {
                    "isSuccess" : true
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com/v1/users"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001"
                    }
                ],
                "actions": []
            }
            
## User Profile Information [/v1/users/{userId}/profile]
### Get user profile information [GET]

+ Response 200 (application/json)

    + Body

            {
                "request" : {
                    "method" : "GET"
                },
                "properties" : {
                    "address" : {
                        "line1" : "1452 Imagination Lane",
                        "line2" : "c/o The Dragon",
                        "city" : "Tigerville",
                        "state" : "ME",
                        "zip" : "00000"
                    },
                    "userId" : 2001
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/profile"
                    },
                    {
                        "rel" : "account",
                        "description" : "Retrieve user account information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/account"
                    }
                ],
                "actions": [
                    {
                        "method": "GET",
                        "description" : "Return user profile information.",
                        "href": "https://examplerest.apiary-mock.com/v1/users/2001/profile"
                    },
                    {
                        "method": "PUT",
                        "description" : "Update user profile information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/profile",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "line1",
                                "description" : "First line of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "line2",
                                "description" : "Second line of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "city",
                                "description" : "City of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "state",
                                "description" : "State of user address.",
                                "type" : "string"
                            },
                            {
                                "name": "zip",
                                "description": "Zip of user address.",
                                "type": "string"
                            }
                        ]
                    },
                    {
                        "method": "POST",
                        "description" : "Create user profile information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/profile",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "line1",
                                "description" : "First line of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "line2",
                                "description" : "Second line of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "city",
                                "description" : "City of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "state",
                                "description" : "State of user address.",
                                "type" : "string"
                            },
                            {
                                "name": "zip",
                                "description": "Zip of user address.",
                                "type": "string"
                            }
                        ]
                    }
                ]
            }

### Update user profile information [PUT]

+ Request (application/json)

    + Body
    
            {
                "line1" : "1452 Imagination Lane",
                "line2" : "c/o The Dragon",
                "city" : "Tigerville",
                "state" : "ME",
                "zip" : "00000"
            }

+ Response 200 (application/json)

    + Body

            {
                "request" : {
                    "method" : "PUT",
                    "data" : {
                        "line1" : "1452 Imagination Lane",
                        "line2" : "c/o The Dragon",
                        "city" : "Tigerville",
                        "state" : "ME",
                        "zip" : "00000"
                    }
                },
                "properties" : {
                    "address" : {
                        "line1" : "1452 Imagination Lane",
                        "line2" : "c/o The Dragon",
                        "city" : "Tigerville",
                        "state" : "ME",
                        "zip" : "00000"
                    },
                    "userId" : 2001
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/profile"
                    },
                    {
                        "rel" : "account",
                        "description" : "Retrieve user account information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/account"
                    }
                ],
                "actions": [
                    {
                        "method": "GET",
                        "description" : "Return user profile information.",
                        "href": "https://examplerest.apiary-mock.com/v1/users/2001/profile"
                    },
                    {
                        "method": "PUT",
                        "description" : "Update user profile information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/profile",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "line1",
                                "description" : "First line of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "line2",
                                "description" : "Second line of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "city",
                                "description" : "City of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "state",
                                "description" : "State of user address.",
                                "type" : "string"
                            },
                            {
                                "name": "zip",
                                "description": "Zip of user address.",
                                "type": "string"
                            }
                        ]
                    },
                    {
                        "method": "POST",
                        "description" : "Create user profile information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/profile",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "line1",
                                "description" : "First line of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "line2",
                                "description" : "Second line of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "city",
                                "description" : "City of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "state",
                                "description" : "State of user address.",
                                "type" : "string"
                            },
                            {
                                "name": "zip",
                                "description": "Zip of user address.",
                                "type": "string"
                            }
                        ]
                    }
                ]
            }
            
### Create user profile [POST]

+ Request (application/json)

    + Body
    
            {
                "line1" : "1452 Imagination Lane",
                "line2" : "c/o The Dragon",
                "city" : "Tigerville",
                "state" : "ME",
                "zip" : "00000"
            }

+ Response 200 (application/json)

    + Body
    
            {
                "request" : {
                    "method" : "POST",
                    "data" : {
                        "line1" : "1452 Imagination Lane",
                        "line2" : "c/o The Dragon",
                        "city" : "Tigerville",
                        "state" : "ME",
                        "zip" : "00000"
                    }
                },
                "properties" : {
                    "address" : {
                        "line1" : "1452 Imagination Lane",
                        "line2" : "c/o The Dragon",
                        "city" : "Tigerville",
                        "state" : "ME",
                        "zip" : "00000"
                    },
                    "userId" : 2001
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/profile"
                    },
                    {
                        "rel" : "account",
                        "description" : "Retrieve user account information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/account"
                    }
                ],
                "actions": [
                    {
                        "method": "GET",
                        "description" : "Return user profile information.",
                        "href": "https://examplerest.apiary-mock.com/v1/users/2001/profile"
                    },
                    {
                        "method": "PUT",
                        "description" : "Update user profile information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/profile",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "line1",
                                "description" : "First line of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "line2",
                                "description" : "Second line of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "city",
                                "description" : "City of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "state",
                                "description" : "State of user address.",
                                "type" : "string"
                            },
                            {
                                "name": "zip",
                                "description": "Zip of user address.",
                                "type": "string"
                            }
                        ]
                    },
                    {
                        "method": "POST",
                        "description" : "Create user profile information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/profile",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "line1",
                                "description" : "First line of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "line2",
                                "description" : "Second line of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "city",
                                "description" : "City of user address.",
                                "type" : "string"
                            },
                            {
                                "name" : "state",
                                "description" : "State of user address.",
                                "type" : "string"
                            },
                            {
                                "name": "zip",
                                "description": "Zip of user address.",
                                "type": "string"
                            }
                        ]
                    }
                ]
            }
            
## User Account Information [/v1/users/{userId}/account]
### Get user account information [GET]

+ Response 200 (application/json)

    + Body
    
            {
                "request" : {
                    "method" : "GET"
                },
                "properties" : {
                    "email" : "example@example.com",
                    "userName" : "ilikecats",
                    "userId" : 2001
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/account"
                    },
                    {
                        "rel" : "profile",
                        "description" : "Retrieve user profile information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/profile"
                    }
                ],
                "actions": [
                    {
                        "method": "GET",
                        "description" : "Return user account information.",
                        "href": "https://examplerest.apiary-mock.com/v1/users/2001/account"
                    },
                    {
                        "method": "PUT",
                        "description" : "Update user account information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/account",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "email",
                                "description" : "User email address.",
                                "type" : "string"
                            },
                            {
                                "name" : "userName",
                                "description" : "User login name.",
                                "type" : "string"
                            }
                        ]
                    },
                    {
                        "method": "POST",
                        "description" : "Create user account information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/account",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "email",
                                "description" : "User email address.",
                                "type" : "string"
                            },
                            {
                                "name" : "userName",
                                "description" : "User login name.",
                                "type" : "string"
                            }
                        ]
                    }
                ]
            }
            
### Update user account information [PUT]

+ Request (application/json)

    + Body
    
            {
                "email" : "example@example.com,
                "userName" : "ilikecats"
            }

+ Response 200 (application/json)

    + Body
    
            {
                "request" : {
                    "method" : "PUT",
                    "data" : {
                        "email" : "example@example.com,
                        "userName" : "ilikecats"
                    }
                },
                "properties" : {
                    "email" : "example@example.com",
                    "userName" : "ilikecats",
                    "userId" : 2001
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/account"
                    },
                    {
                        "rel" : "profile",
                        "description" : "Retrieve user profile information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/profile"
                    }
                ],
                "actions": [
                    {
                        "method": "GET",
                        "description" : "Return user account information.",
                        "href": "https://examplerest.apiary-mock.com/v1/users/2001/account"
                    },
                    {
                        "method": "PUT",
                        "description" : "Update user account information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/account",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "email",
                                "description" : "User email address.",
                                "type" : "string"
                            },
                            {
                                "name" : "userName",
                                "description" : "User login name.",
                                "type" : "string"
                            }
                        ]
                    },
                    {
                        "method": "POST",
                        "description" : "Create user account information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/account",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "email",
                                "description" : "User email address.",
                                "type" : "string"
                            },
                            {
                                "name" : "userName",
                                "description" : "User login name.",
                                "type" : "string"
                            }
                        ]
                    }
                ]
            }
            
### Create user account information [POST]

+ Request (application/json)

    + Body
    
            {
                "email" : "example@example.com,
                "userName" : "ilikecats"
            }

+ Response 200 (application/json)

    + Body
        
            {
                "request" : {
                    "method" : "POST",
                    "data" : {
                        "email" : "example@example.com,
                        "userName" : "ilikecats"
                    }
                },
                "properties" : {
                    "email" : "example@example.com",
                    "userName" : "ilikecats",
                    "userId" : 2001
                },
                "links" : [
                    {
                        "rel" : "parent",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001"
                    },
                    {
                        "rel" : "self",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/account"
                    },
                    {
                        "rel" : "profile",
                        "description" : "Retrieve user profile information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/profile"
                    }
                ],
                "actions": [
                    {
                        "method": "GET",
                        "description" : "Return user account information.",
                        "href": "https://examplerest.apiary-mock.com/v1/users/2001/account"
                    },
                    {
                        "method": "PUT",
                        "description" : "Update user account information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/account",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "email",
                                "description" : "User email address.",
                                "type" : "string"
                            },
                            {
                                "name" : "userName",
                                "description" : "User login name.",
                                "type" : "string"
                            }
                        ]
                    },
                    {
                        "method": "POST",
                        "description" : "Create user account information",
                        "href" : "https://examplerest.apiary-mock.com/v1/users/2001/account",
                        "type" : "application/json",
                        "params" : [
                            {
                                "name" : "email",
                                "description" : "User email address.",
                                "type" : "string"
                            },
                            {
                                "name" : "userName",
                                "description" : "User login name.",
                                "type" : "string"
                            }
                        ]
                    }
                ]
            }
