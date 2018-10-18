- [Use case](#use-case)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
        - [Response Notes](#response-notes)
    - [Index of all Use Cases link](#index-of-all-use-cases-link)

# Use case

You want to find the active contacts in the list by searching with its contact list name.
examples of contact list data details [link](https://www.benchmarkemail.com/models.htm#ContactFullRecord)
## Prerequisites

---

1. A client to make an API call, such as postman [link](https://www.getpostman.com/)
1. Use base URL/Host : `https://clientapi.benchmarkemail.com`
1. RESTful collection found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3) 
1. A benchmark email account. API usage is included with a free account [link](https://ui.benchmarkemail.com/Login)
   * Your API Key, for your requests to be validated. Found [here](https://ui.benchmarkemail.com/Integrate#API)

## Solution

<sub>using the Benchmark API v3.0 RESTful endpoints</sub>

1. Make a request to search for the contact list [link](https://developer.benchmarkemail.com/#cc3ee91a-0ccb-79c1-9365-c96f8511a68b). The response body will provide the list details if it finds the list queried [link](https://www.benchmarkemail.com/models.htm#ContactFullRecord).

```js
    GET /Contact/?SearchFilter={{SearchFilter}}
    //where {{SearchFilter}} will be replaced with all or part of your contact list name.
    //in the response body find Resonse.Data[1..n].ContactCount for the respective list name
```

### Response Notes

1. Confirm the response provides
    1. a status of 200 OK 
    1. the response body does NOT contain a value of -1 for Response.Status
    1. Confirm Response.Status value is 1.

---

## Index of all Use Cases [link](https://benchmarkemail.github.io/RESTful-API-v3/)