- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
    - [Validate Response from Server](#validate-response-from-server)
- [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement

You want to create a webhook to be notified when a field of a contact changes for a given list [link](https://developer.benchmarkemail.com/#a83163d0-3af1-9671-8a8c-c7d4d31e6c13)

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

2. Make a request to create a webhook, the body of the request will given a value of 1 for being notified of an event and a 0 value for not being notified with the given URL [link](https://developer.benchmarkemail.com/#a83163d0-3af1-9671-8a8c-c7d4d31e6c13)

```js
     POST /Contact/{{ListID}}/Webhooks
     //where request body you provide will be 
     //Where {{ListID}} will be your list id this webhook will be associated with
     {
        "Data": {
          "CleanedAddress": "0",
          "EmailChanged": "0",
          "ProfileUpdates": "1",
          "Subscribes": "0",
          "Unsubscribes": "0",
          "ClientUrl": "{{URL}}",
          "ContactMasterID": "{{ListID}}"
        }
     }
     //where {{URL}} will be your host URL for benchmark to send the data to
     //where {{ListID}} will be your list id this webhook will be associated with
```

## Validate Response from Server

1. Confirm the response provides
    1. a status of 200 OK 
    1. the response body does NOT contain a value of -1 for Response.Status
    1. Confirm Response.Status value is 1.

---

# Index of all Problem Statements [link](https://benchmarkemail.github.io/RESTful-API-v3/)