- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
    - [Validate Response from Server](#validate-response-from-server)
    - [Variation(s) of problem](#variations-of-problem)
    - [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement

I to want create a new list and get its list Id #

## Prerequisites

---

1. A client to make an API call, such as postman [link](https://www.getpostman.com/)
1. Use base URL/Host : `https://clientapi.benchmarkemail.com`
1. RESTful collection found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections) 
1. A benchmark email account. API usage included with a free account [link](https://ui.benchmarkemail.com/Login)
   * Your API Key, for your requests to be validated. Found [here](https://ui.benchmarkemail.com/Integrate#API)

## Solution

<sub>using the Benchmark API v3.0 RESTful endpoints</sub>

1. Make a POST request with the information for your new list [link](https://developer.benchmarkemail.com/#16e1491e-69f8-e71a-c374-d99e55c322cf)

```js
   POST /Contact
   //minimal request body data you provide is {"Data":{"Name":"{{Name}}","Description":"{{Description}}"}}
   //Take the ID returned for future use in API calls
```

## Validate Response from Server

1. Confirm the response provides
    1. a status of 200 OK 
    1. the response body does NOT contain a value of -1 for Response.Status
    1. Confirm Response.Status value is 1.

## Variation(s) of problem

- I want to get the list Id # of pre-existing lists [link]()

---

# Index of all Problem Statements [link](https://benchmarkemail.github.io/RESTful-API-v3/)
