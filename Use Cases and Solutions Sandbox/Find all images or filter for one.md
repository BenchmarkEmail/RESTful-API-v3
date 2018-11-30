- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
    - [Validate Response from Server](#validate-response-from-server)
- [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement

Find a specific image or a list of all images

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

2. Make a request to get all or specific images [link](https://developer.benchmarkemail.com/#d20428c2-b8d2-dc82-bc02-2855b51816a4)

```js
      GET /Images/
     // where querystring params can be added to filter the search,
     // ex: /Images/?Filter={{Filter}}
     // were the {{Filter}} is the full por partial string name of the image searching for
```

## Validate Response from Server

1. Confirm the response provides
    1. a status of 200 OK 
    1. the response body does NOT contain a value of -1 for Response.Status
    1. Confirm Response.Status value is 1.

---

# Index of all Problem Statements [link](https://benchmarkemail.github.io/RESTful-API-v3/)