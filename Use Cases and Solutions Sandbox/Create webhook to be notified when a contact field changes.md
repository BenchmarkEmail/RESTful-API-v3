- [Use case](#use-case)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
        - [Response Notes](#response-notes)
    - [Index of all Problem Statements link](#index-of-all-use-cases-link)

# Problem Statement

You want to create a webhook to be notified when a field of a contact changes for a given list [link](https://developer.benchmarkemail.com/#a83163d0-3af1-9671-8a8c-c7d4d31e6c13)

## Prerequisites

---

1. A client to make an API call, such as postman [link](https://www.getpostman.com/)
1. Use base URL/Host : `https://clientapi.benchmarkemail.com`
1. RESTful collection found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections) 
1. A benchmark email account. API usage is included with a free account [link](https://ui.benchmarkemail.com/Login)
   * Your API Key, for your requests to be validated. Found [here](https://ui.benchmarkemail.com/Integrate#API)

## Solution

<sub>using the Benchmark API v3.0 RESTful endpoints</sub>

1. Make a request to create a webhook, the body of the request will given a value of 1 for being notified of an event and a 0 value for not being notified with the given URL [link](https://developer.benchmarkemail.com/#a83163d0-3af1-9671-8a8c-c7d4d31e6c13)

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

### Response Notes

1. Confirm the response provides
    1. a status of 200 OK 
    1. the response body does NOT contain a value of -1 for Response.Status
    1. Confirm Response.Status value is 1.

---

## Index of all Problem Statements [link](https://benchmarkemail.github.io/RESTful-API-v3/)