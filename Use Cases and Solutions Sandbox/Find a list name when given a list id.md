- [Use case:](#problem-statement)
  - [Prerequisites](#prerequisites)
  - [Solution](#solution)
    - [Response Notes](#response-notes)
  - [Index of all Problem Statements link](#index-of-all-use-cases-link)

# Problem Statement

You have a list id, and want the list details like list name, creation date, active contact count, the fields being used for the contacts in the list

## Prerequisites

---

1. A client to make an API call, such as postman [link](https://www.getpostman.com/)
1. Use base URL/Host : `https://clientapi.benchmarkemail.com`
1. RESTful collection found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections) 
1. A benchmark email account. API usage is included with a free account [link](https://ui.benchmarkemail.com/Login)
   * Your API Key, for your requests to be validated. Found [here](https://ui.benchmarkemail.com/Integrate#API)

## Solution

<sub>using the Benchmark API v3.0 RESTful endpoints</sub>

1. Make a request using your list id [link](https://developer.benchmarkemail.com/#dfa2a8a6-f1ba-d4b8-4d9f-d3b637be2291)

```js
    GET /Contact/{{ListID}}
    //where response body will provide list info. and fields used for contacts
```

### Response Notes

1. Confirm the response provides
    1. a status of 200 OK 
    1. the response body does NOT contain a value of -1 for Response.Status
    1. Confirm Response.Status value is 1.

---

## Index of all Problem Statements [link](https://benchmarkemail.github.io/RESTful-API-v3/)