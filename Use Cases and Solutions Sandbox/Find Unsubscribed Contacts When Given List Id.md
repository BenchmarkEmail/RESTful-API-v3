- [Use Case 1](#problem-statement-1)
    - [Solution](#solution)
    - [Directions and Steps](#directions-and-steps)

# Problem Statement

Given Any free or paid Benchmark Email Account will have a needed API Token. \
Then I want to see the recipients on a list who are unsubscribed. 

---

## Prerequisites

1. A free or paid Benchmark Email account. Both account types provide free API usage. Sign up here, [link](https://ui.benchmarkemail.com/Integrate#AP)
1. Always use host of: `https://clientapi.benchmarkemail.com`
1. An HTTP library or HTTP app, such as [postman](https://www.getpostman.com/), to make API calls

## Solution

<sub>The following endpoints and more details can be found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections)</sub>

1. _Set Request Headers_. Secure your request by placing your Benchmark Email API Token in the header of your request. (Don't have a token?  Get one free, [link](https://ui.benchmarkemail.com/integrate?from=login#API))

```javascript
// example of headers from a python3 request

headers = {
    'AuthToken': "YOUR_BENCHMARK_EMAIL_API_TOKEN_HERE",
    'Content-Type': "application/json" 
}

// application/json is used for all GET requests
```

2. Make a request using your list Id and adding the 1 query-string parameter seen below

```javascript
GET /Contact/{{ListID}}/ContactDetails

// where the 'Filter' is a value of 2, see docs [link](https://developer.benchmarkemail.com/#efdb4a44-2a7b-92b5-f49c-d59239d4d0d7)
// response body will have all list of all contacts in the list that have unsubscribed    
```

## Directions and Steps

1. Prerequisite: Have the list id # to search through.
1. Use a GET call ` `
   1. `GET /Contact/{{ListID}}/ContactDetails`
      1. Where the 'Filter' is a value of 2, see docs [link](https://developer.benchmarkemail.com/#efdb4a44-2a7b-92b5-f49c-d59239d4d0d7)
1. Confirm the response provides 
    1. a status of 200 OK 
    1. If total count is zero, [image](https://www.dropbox.com/s/ftfpclgx77czc8l/2018-09-17_12-46-59.png?dl=0) 
        1. response body may have a Response.Status of -1 
        1. Response body may have a Response.Error array with one of the elements holding a message of Response.Error[0..n].message = "NO_RECORDS_FOUND" 
    1. Confirm response body shows count greater than zero by [image](https://www.dropbox.com/s/nd9psjxeeq2434c/2018-09-17_12-49-31.png?dl=0)
        1. Response.Status value equals 1 to validate that count of unsubscribes is greater than 0. Confirm Response.
        1. Response.Count >= 1 confirms unsubscribes greater than zero.
        1. Response.Data array holds object elements of contacts that unsubscribed

