- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
    - [Validate Response from Server](#validate-response-from-server)
- [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement

You want to create one webhook to be notified for multiple events on a contact for a given list [link](https://developer.benchmarkemail.com/#a83163d0-3af1-9671-8a8c-c7d4d31e6c13)

## Prerequisites

---

1. An HTTP client library or app to make API Calls, such as postman [link](https://www.getpostman.com/)
1. Always use host of: : `https://clientapi.benchmarkemail.com`
1. RESTful collection found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections) 
1. Any free or paid Benchmark Email Account will have a needed API token.  [link](https://ui.benchmarkemail.com/Integrate#AP)

1. The API Token, above, is used as a   key/value pair in your request header, key is `AuthToken` and its value is `{{Authentication Token}}`, where {{Authentication Token}} is replaced with your API Token [image](https://images.benchmarkemail.com/client963265/image6234734.png).

## Solution

<sub>using the Benchmark API v3.0 RESTful endpoints</sub>

1. Make a request to create a webhook, the body of the request will given a value of 1 for being notified of an event and a 0 value for not being notified with the given URL [link](https://developer.benchmarkemail.com/#a83163d0-3af1-9671-8a8c-c7d4d31e6c13)

```js
     POST /Contact/{{ListID}}/Webhooks
     //where request body you provide will be 
     //Where {{ListID}} will be your list id this webhook will be associated with
     {
        "Data": {
          "CleanedAddress": "1",
          "EmailChanged": "1",
          "ProfileUpdates": "1",
          "Subscribes": "1",
          "Unsubscribes": "1",
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