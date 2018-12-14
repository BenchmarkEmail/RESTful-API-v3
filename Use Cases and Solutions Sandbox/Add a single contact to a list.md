- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
    - [Validate Response from Server](#validate-response-from-server)
    - [Variations of problem](#variations-of-problem)
- [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement

Add an email address and the contact information to a list

---

## Prerequisites
1. A free or paid Benchmark Email account. Both account types provide free API usage. Sign up here, [link](https://ui.benchmarkemail.com/integrate?from=login#API)
1. Always use host of: `https://clientapi.benchmarkemail.com`
1. An HTTP library or HTTP app, such as [postman](https://www.getpostman.com/), to make API calls
## Solution
<sub>The following endpoints and more details can be found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections)</sub>

1. Secure your request by placing your Benchmark Email API Token in the header of your request. (Don't have a token?  Get one free, see pre-requisite #1 above.)

```javascript
// example of headers from a python3 request

headers = {
    'AuthToken': "YOUR_BENCHMARK_EMAIL_API_TOKEN_HERE",
    'Content-Type': "application/json" 
}

// application/json is used for all GET requests
```

2. Make an API call to retrieve your list(s) id # [link:](https://developer.benchmarkemail.com/#cc3ee91a-0ccb-79c1-9365-c96f8511a68b). The list id # will be found in the response body.

```js
    GET /Contact
    // or filter your search by adding the query string parameter
    GET /Contact/?SearchFilter={{SearchFilter}}
     // {{SearchFilter}} is a placeholder and will be provided by you. It is a your partial or full name of your list
     // to see full list of parameters available see docs. in link above
     // list id found at Response.Data[0..n].ID
```

2. Add your new contact by providing the contacts information and the listID from above, [link](https://developer.benchmarkemail.com/#375fa862-2ac6-9d5d-3669-6e9a23524241). For a list of all data fields available to add contact information, see [link](https://www.benchmarkemail.com/models.htm#ContactDetailRecord)

```js
    POST /Contact/{{ListID}}/ContactDetails
    //where the minimum data to provide in the request body is:
      {"Data":{"Email":"{{EMail}}","FirstName":"{{FirstName}}","LastName":"{{LastName}}","EmailPerm":"{{1|0}}"}}
    //Note the key in the request of "EmailPerm". This must be a 1 or it will not save and will be an error
```


## Validate Response from Server

1. Confirm the response provides
    1. a status of 200 OK
    1. the response body does NOT contain a value of -1 for Response.Status
    1. Confirm Response.Status value is 1.

## Variations of problem

1. I want to get a list id # for an existing list(s).
1. I want to create a new list and get its list id #.

---

# Index of all Problem Statements [link](https://benchmarkemail.github.io/RESTful-API-v3/)