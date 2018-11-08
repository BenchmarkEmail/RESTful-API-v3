- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
    - [Validate Response from Server](#validate-response-from-server)
- [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement


## Prerequisites

---

1. A client to make an API call, such as postman [link](https://www.getpostman.com/)
1. Use base URL/Host : `https://clientapi.benchmarkemail.com`
1. RESTful collection found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections) 
1. A benchmark email account. API usage is included with a free account [link](https://ui.benchmarkemail.com/Login)
   * Your API Key, for your requests to be validated. Found [here](https://ui.benchmarkemail.com/Integrate#API)

## Solution

<sub>using the Benchmark API v3.0 RESTful endpoints</sub>

1. Make a POST request of content type multipart/form-data with the body showing the form-data of a "Data" object [link](https://developer.benchmarkemail.com/#c6f94eae-3d70-41d5-8423-040e8c945a22)

```js
     POST /Images/
     // where the body will hold the image reference psuedo example:
     headers = {
    'content-type': "multipart/form-data;, 
    'Content-Type': "application/x-www-form-urlencoded",
    }
    payload = "Content-Disposition: form-data; name=\"Data\"; filename=\"C:\\Path\\To\\Pictures\\benchmark-logo.1.jpg\" Content-Type: image/jpeg"
```

## Validate Response from Server

1. Confirm the response provides
    1. a status of 200 OK 
    1. the response body does NOT contain a value of -1 for Response.Status
    1. Confirm Response.Status value is 1.

---

# Index of all Problem Statements [link](https://benchmarkemail.github.io/RESTful-API-v3/)