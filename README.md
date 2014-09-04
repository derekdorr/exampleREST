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

## HTTP Request Methods

|Method|When To Use|Safe?|Secure?|Idempotent?|
|------|-----------|-----|-------|-----------|
|GET|Information retrieval|Yes|Yes|Yes|
|HEAD|Similiar to GET, but returns only header information.|Yes|Yes|Yes|
|POST|Create a new entity under a resource.|No|Yes|No|
|PUT|Update an existing entity under a resource.|No|Yes|Yes|
|DELETE|Delete an existing entity under a resource.|No|Yes|Yes|
|TRACE|Echo request made to target.|Yes|No|Yes|
|OPTIONS|Returns supported methods to client.|Yes|Yes|Yes|
|PATCH|Update a resource defined by a URI|No|No|No|

+ Safe: Information is only retrieved, it is not created, edited, or removed.
+ Secure: This method is not considered a potential security risk.
+ Idempotent: Multiple simultaneous requests should return the same response.

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

## Property Naming Conventions

+ Booleans should be in a format of `is` followed by a noun or adjective. I.E. `isError`, `isRed`, `isHappy`.

## Link Relations

The following table contains a list of link relations which might be useful in building a Hypermedia REST spec.  Where possible, link relations should be obtained from the standards presented by the IANA.

For a complete list of link relations accepted by IANA, see http://www.iana.org/assignments/link-relations/link-relations.xhtml

|Relation Name|Description|IANA Standard?|Reference|
|-------------|-----------|--------------|---------|
|first|Identifier for first resource in a series of resources|Yes|http://www.iana.org/go/rfc5988|
|schema|Indetifier for link to schema for current resource|No||
|self|Indentifier for link to current resource|Yes|http://tools.ietf.org/html/rfc4287|
|up|Identifier for parent resource of current resource|Yes|http://www.iana.org/go/rfc5988|

