# Use Case:

Given a list id, and an email address.
Then how do I find an email id for other API calls, but only have my email name

## Solution:  

1. Get the email ID to be used for the report request
    1.  `GET /Emails`  [link](https://developer.benchmarkemail.com/#0068614f-f224-141b-b1eb-8768abc0f5d3) 
        1.  Add the 'Filter' parameter to the querystring and provide part of the email name or the whole email name as the value  \
Ex: ?Filter={{Filter}}

## Directions and Steps 

1. Open an http client to test a request (we'll use postman, for postman setup see Getting Started )
1. Use a GET call  
   1.  `GET /Emails`  [link](https://developer.benchmarkemail.com/#0068614f-f224-141b-b1eb-8768abc0f5d3) 
        1.  where the call can be enhanced by using the optional parameters on seen in the [documentation](https://developer.benchmarkemail.com/#0068614f-f224-141b-b1eb-8768abc0f5d3) 
        1.  Add the 'Filter' parameter to the querystring and provide part of the email name or the whole email name as the value  \
Ex: `?Filter={{Filter}}`
        1.  In the response body see the Response.Data array of a list objects. Find the <code>Response.Data[0..n].ID </code>[screenshot](https://www.dropbox.com/s/9m0t0hvhq0g4wza/2018-09-19_10-52-59.png?dl=0)
1.  Confirm the response provides 
    1.  a status of 200 OK 
    1.  the response body does NOT contain a value of -1 for Response.Status 
    1.  Confirm Response.Status value is 1 [screenshot](https://www.dropbox.com/s/ewwb8p0pshwwwxz/2018-09-13_13-41-35.png?dl=0)