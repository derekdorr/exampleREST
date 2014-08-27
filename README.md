exampleREST
===========

An attempt at an example REST Structure / Standard for API and JSON development.

Example endpoint collection can be interacted with at: https://examplerest.apiary-mock.com/

# Use of HTTP Response Codes

Standardized HTTP response codes should be used in cases of success or failure, depending on the type of success or failure achieved.

# Basic response structure

            {
                "request" : { // A wrapper containing information for the current request.
                    "method" : "GET", // Request Method... i.e. GET, PUT, POST, DELETE
                    "params" : [ // Query string or URI Parameters
                        {
                            "name" : "paramName",
                            "value" : "paramValue"
                        }
                    ],
                    "data" : {} // Data passed in via PUT or POST.
                },
                "properties" : {}, // If the request is succesful and returns consumable information, it is wrapped in a properties object.
                "fault" : {}, // If the request is unsuccessful, error details are wrapped in a fault object.
                "links" : [ // Links to information related to request.
                    {
                        "rel" : "self", // Relationship to current endpoint
                        "href" : "http://examplerest.apiary-mock.com/", // Fully qualified URL
                        "description" : "An example description" // Description of link target
                    }
                ],
                "actions" : [ // Methods able to be used on the current endpoint.
                    {
                        "method" : "GET",
                        "description" : "Description of method result",
                        "type" : "text/html" // Content type of the method request,
                        "params" : [ // Collection of params
                            {
                                "name" : "param1" // Parameter name,
                                "type" : "number" // Parameter data type,
                                "description" : "Description of parameter."
                            }
                        ]
                    }
                ]
            }
