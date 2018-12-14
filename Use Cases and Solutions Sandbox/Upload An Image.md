- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
    - [Validate Response from Server](#validate-response-from-server)
- [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement

Upload an image to your image gallery

---

## Prerequisites

1. A free or paid Benchmark Email account. Both account types provide free API usage. Sign up here, [link](https://ui.benchmarkemail.com/Integrate#AP)
1. Always use host of: `https://clientapi.benchmarkemail.com`
1. An HTTP library or HTTP app, such as [postman](https://www.getpostman.com/), to make API calls

## Solution

<sub>The follwoing endpoints and more details can be found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections)</sub>

1. Secure your request by placing your Benchmark Email API Token in the header of your request. (Don't have a token?  Get one free, see pre-requisite #1 above.)

```javascript
// example of headers from a python3 request

headers = {
    'AuthToken': "YOUR_BENCHMARK_EMAIL_API_TOKEN_HERE",
    'content-type': "multipart/form-data;",
    'Content-Type': "application/x-www-form-urlencoded"
}

```

2. Make a POST request of content type multipart/form-data with the body showing the form-data of a "Data" object [link](https://developer.benchmarkemail.com/#c6f94eae-3d70-41d5-8423-040e8c945a22)

```js
POST /Images/

// where the body will hold the image reference psuedo example:
  payload = "Content-Disposition: form-data; name=\"Data\"; filename=\"C:\\Path\\To\\Pictures\\benchmark-logo.1.jpg\" Content-Type: image/jpeg"
```

## Validate Response from Server

1. Confirm the response provides
    1. a status of 200 OK 
    1. the response body does NOT contain a value of -1 for Response.Status
    1. Confirm Response.Status value is 1.

---

# Index of all Problem Statements [link](https://benchmarkemail.github.io/RESTful-API-v3/)