- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
    - [Validate Response from Server](#validate-response-from-server)
- [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement

You want to find the unsubscribe emails in a list by searching with a list Id #.

---

## Prerequisites

1. A free or paid Benchmark Email account. It will have your secured API token.  [link](https://ui.benchmarkemail.com/Integrate#AP)
1. Always use host of: `https://clientapi.benchmarkemail.com`
1. An HTTP library or HTTP app, such as [postman](https://www.getpostman.com/), to make API calls

## Solution

<sub>using the Benchmark API v3.0 RESTful endpoints. All our RESTful endpoints documentation found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections)></sub>

1. Secure your request by placing your Benchmark Email API Token, see prerequisite #1 above, in the header of your request.

```javascript
// example of headers from a python3 request

headers = {
    'AuthToken': "YOUR_BENCHMARK_EMAIL_API_TOKEN_HERE",
    'Content-Type': "application/json" 
}

// application/json is used for all GET requests
```

2. Make a request using your list Id and adding the 1 query-string parameter seen below
 [link](https://developer.benchmarkemail.com/#efdb4a44-2a7b-92b5-f49c-d59239d4d0d7)

```js
    GET /Contact/{{ListID}}/ContactDetails?Filter=2
    //where {{ListID}} will need to be replaced with your list id number
    //where the query string value of 2 is for unsubscribed emails in the list
    //
```

## Validate Response from Server

1. Confirm the response provides
    1. a status of 200 OK 
    1. the response body does NOT contain a value of -1 for Response.Status
    1. Confirm Response.Status value is 1.
    1. Also response body may have a status of -1 and a Response.Error array with one of the elements holding a message of Response.Error[0..n].message = "NO_RECORDS_FOUND" 
       1. Reason: Error is based upon the query results return a value of 0. Possibly not a true error, but rather just no results for the search.

---

# Index of all Problem Statements [link](https://benchmarkemail.github.io/RESTful-API-v3/)