exampleREST
===========

An attempt at an example REST Structure / Standard for API and JSON development.

Example endpoint collection can be interacted with at: https://examplerest.apiary-mock.com/

## Use of HTTP Status Codes

Standardized HTTP status codes should be used in cases of success or failure, depending on the type of success or failure achieved. Some useful response codes are outlined below.

More information on HTTP response codes can be found here: http://en.wikipedia.org/wiki/List_of_HTTP_status_codes
Or, pull them right from W3: http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html

### Success - 2XX

|Response Code|Name|Description|
|-------------|----|-----------|
|200|OK|Standard response for an HTTP request.|
|202|Accepted|The request was successful, but has not yet been acted upon. It may be rejected later.|

### Client Error - 4XX

|Response Code|Name|Description|
|-------------|----|-----------|
|400|Bad Request|The request cannot be completed due to bad syntax.|
|401|Unauthorized|The request requires authentication to be completed.|
|403|Forbidden|Similar to 401, but authentication will not allow request to be completed.|
|404|Not Found|The requested resource was not found.|
|405|Method Not Allowed|An unsupported method was used.|
|408|Request Timeout|The request timed out.|
|410|Gone|The resource used to exist, but no longer exists.|
|418|I'm A Teapot|I'm a teapot...|
|429|Too Many Requests|Number of requests have exceeded the rate limit.|

### Server Error - 5XX

|Response Code|Name|Description|
|-------------|----|-----------|
|500|Internal Server Error|Generic server fault status.|
|501|Not Implemented|The requested resource has not yet been implemented.|
|503|Service Unavailable|The service is temporarily down.|

## Basic response structure

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
                        "href" : "http://examplerest.apiary-mock.com/", // Fully qualified URL
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
