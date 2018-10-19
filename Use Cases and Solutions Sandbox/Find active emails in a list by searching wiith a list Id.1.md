- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
        - [Response Notes](#response-notes)
    - [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement

You want to find the active email address(es) in a list, exluding the hard-bounces and unsubscirbes by searching with a list Id #.

## Prerequisites

---

1. A client to make an API call, such as postman [link](https://www.getpostman.com/)
1. Use base URL/Host : `https://clientapi.benchmarkemail.com`
1. RESTful collection found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections) 
1. A benchmark email account. API usage is included with a free account [link](https://ui.benchmarkemail.com/Login)
   * Your API Key, for your requests to be validated. Found [here](https://ui.benchmarkemail.com/Integrate#API)

## Solution

<sub>using the Benchmark API v3.0 RESTful endpoints</sub>

1. Make a request using your list Id and adding the 1 query-string parameter seen below
 [link](https://developer.benchmarkemail.com/#efdb4a44-2a7b-92b5-f49c-d59239d4d0d7)

```js
    GET /Contact/{{ListID}}/ContactDetails
    //where {{ListID}} will need to be replaced with your list id number
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