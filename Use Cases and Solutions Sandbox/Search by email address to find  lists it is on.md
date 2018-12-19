- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
        - [Response Notes](#response-notes)
    - [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement

You want search using an email address to find what lists the email subscribes to. Results will provide the email id # and list id #. Also provides the first, last and middle name and rating.

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

2. Make a request to search by known email address [link]()

```js
     Get /Contact/ContactDetails?Search={{Search}} 
     // REQUIRED: the {{Search}} is a placeholder that you will replace with the full email address.
     // If the full email address isn't known, adding the SearchFilter value will allow you to use a partioal email
     // SearchFilter values: 1 - Starts 2 - exact 3 - contains 4 - end
     // the result will give the list id as the ContactMasterID
     DELETE /Contact/ContactDetails/All
     // body
     {"ListID":"{{ListID}}","ContactID":"{{ContactID}}"}
     // DELETE Contact only from search contact page
```

## Validate Response from Server

1. Confirm the response provides
    1. a status of 200 OK 
    1. the response body does NOT contain a value of -1 for Response.Status
    1. Confirm Response.Status value is 1.

---

# Index of all Problem Statements [link](https://benchmarkemail.github.io/RESTful-API-v3/)