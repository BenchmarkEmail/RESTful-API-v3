- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
    - [Validate Response from Server](#validate-response-from-server)
- [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement

Want to find the size, name, image gallery url of an image in your image gallery

## Prerequisites

---

1. An HTTP client library or app to make API Calls, such as postman [link](https://www.getpostman.com/)
1. Always use host of: : `https://clientapi.benchmarkemail.com`
1. RESTful collection found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections) 
1. Any free or paid Benchmark Email Account will have a needed API token.  [link](https://ui.benchmarkemail.com/Integrate#AP)


## Solution

<sub>using the Benchmark API v3.0 RESTful endpoints</sub>

1. Make a request to find your image id, then use it to find the image details [link](https://developer.benchmarkemail.com/#e216e2f6-fbbc-be61-ba25-54a025ba12a5)

```js
     GET /Images/{{ImageID}}
     // where the ImageID value if found from GET /images
```

## Validate Response from Server

1. Confirm the response provides
    1. a status of 200 OK 
    1. the response body does NOT contain a value of -1 for Response.Status
    1. Confirm Response.Status value is 1.

---

# Index of all Problem Statements [link](https://benchmarkemail.github.io/RESTful-API-v3/)