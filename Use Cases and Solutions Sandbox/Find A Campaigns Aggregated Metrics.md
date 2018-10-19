- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
    - [Validate Response from Server](#validate-response-from-server)
    - [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement

You have a contact list id and want to get a summary of common metrics for my email campaign, such as Opens, Clicks, Bounces, Unsubscribes, etc.

## Prerequisites

---

1. A client to make an API call, such as postman [link](https://www.getpostman.com/)
1. Use base URL/Host : `https://clientapi.benchmarkemail.com`
1. RESTful collection found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections) 
1. A benchmark email account. APIs are included with a free account [link](https://ui.benchmarkemail.com/Login)
   * Your API Key, for your requests to be validated. Found [here](https://ui.benchmarkemail.com/Integrate#API)

## Solution

<sub>using the Benchmark API v3.0 RESTful endpoints</sub>

1. Make a request for the email ID to be used for the report request [link](https://developer.benchmarkemail.com/#0068614f-f224-141b-b1eb-8768abc0f5d3)

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

## Index of all Problem Statements [link](https://benchmarkemail.github.io/RESTful-API-v3/)