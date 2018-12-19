- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
    - [Validate Response from Server](#validate-response-from-server)
    - [Variation(s) of problem](#variations-of-problem)
- [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement

I to want create a new list and get its list Id #

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

2. Make a POST request with the information for your new list [link](https://developer.benchmarkemail.com/#16e1491e-69f8-e71a-c374-d99e55c322cf)

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
