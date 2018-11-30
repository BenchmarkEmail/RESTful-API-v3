- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
    - [Validate Response from Server](#validate-response-from-server)
- [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement

I want to get a temporary API Token to make api calls

## Prerequisites

---

1. An HTTP client library or app to make API Calls, such as postman [link](https://www.getpostman.com/)
1. Always use host of: : `https://clientapi.benchmarkemail.com`
1. RESTful collection found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections) 
1. Any free or paid Benchmark Email Account will have a needed API token.  [link](https://ui.benchmarkemail.com/Integrate#AP)


## Solution

<sub>using the Benchmark API v3.0 RESTful endpoints</sub>

1. Make a POST request sending in the user name and password [link]()

```js
     POST /Client/Authenticate
     // sending 'Content-Type': "application/json",
     // with the body : {"Username":"{{Username}}", "Password":"{{Password}}"}
     // RESPONSE will send back a 24 hour token
```

## Validate Response from Server

1. Confirm the response provides
    1. a status of 200 OK 
    1. the response body does NOT contain a value of -1 for Response.Status
    1. Confirm Response.Status value is 1.

---

# Index of all Problem Statements [link](https://benchmarkemail.github.io/RESTful-API-v3/)