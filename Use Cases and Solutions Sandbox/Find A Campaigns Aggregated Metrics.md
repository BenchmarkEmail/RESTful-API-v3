- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
    - [Validate Response from Server](#validate-response-from-server)
- [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement

You have a contact list id and want to get a summary of common metrics for your email campaign, such as Opens, Clicks, Bounces, Unsubscribes, etc.

---

## Prerequisites

1. A free or paid Benchmark Email account. It will have your secured API token.  [link](https://ui.benchmarkemail.com/Integrate#AP)
1. Always use host of: `https://clientapi.benchmarkemail.com`
1. An HTTP library or HTTP app, such as postman [link](https://www.getpostman.com/), to make API calls

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

2. Make a request for the email ID to be used for the report request [link](https://developer.benchmarkemail.com/#0068614f-f224-141b-b1eb-8768abc0f5d3)

```js
     GET /Emails
     or
     GET /Emails/?Filter={{Filter}}
     //where the call can be enhanced by using the optional parameters, see documentation in link above
     //In the response body see the Response.Data array of a list objects.Seen in reesponse body as Response.Data[0..n].ID
```

2. Make a request using the email id, above, to get the summary data such as Opens, Clicks, Bounces, Unsubscribes [link](https://developer.benchmarkemail.com/#8819bcb9-afc9-9e7c-b31a-44aab47ed758)

```js
    GET /Emails/{{ID}}/Report
```

## Validate Response from Server

1. Confirm the response provides
    1. a status of 200 OK 
    1. the response body does NOT contain a value of -1 for Response.Status
    1. Confirm Response.Status value is 1.

---

# Index of all Problem Statements [link](https://benchmarkemail.github.io/RESTful-API-v3/)