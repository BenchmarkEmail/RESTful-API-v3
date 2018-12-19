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

1. _Set Request Headers_. Secure your request by placing your Benchmark Email API Token in the header of your request. (Don't have a token?  Get one free, [link](https://ui.benchmarkemail.com/integrate?from=login#API))

```javascript
// example of headers from a python3 request

headers = {
    'AuthToken': "YOUR_BENCHMARK_EMAIL_API_TOKEN_HERE",
    'Content-Type': "application/json" 
}

// application/json is used for all GET requests
```

2. Retrieve your list(s) id # [link:](https://developer.benchmarkemail.com/#cc3ee91a-0ccb-79c1-9365-c96f8511a68b). 

```js
    GET /Contact
    // ADDITIONALLY: to refine the results, modify your request and add a SearchFilter to your request as a query string.
    GET /Contact/?SearchFilter={{SearchFilter}}
     // {{SearchFilter}} is a placeholder you replace with the part of the list name. 
     // list id found at Response.Data[0..n].ID
```

3. Use the ListId from previous step and make this next request to Add your new contact. [link](https://developer.benchmarkemail.com/#375fa862-2ac6-9d5d-3669-6e9a23524241). For a list of all data fields available to add contact information, see [link](https://www.benchmarkemail.com/models.htm#ContactDetailRecord)

```js
    POST /Contact/{{ListID}}/ContactDetails
    //where the minimum data to provide in the request body is:
      {"Data":{"Email":"{{EMail}}","FirstName":"{{FirstName}}","LastName":"{{LastName}}","EmailPerm":"{{1|0}}"}}
    //Note: `Data.EmailPerm` must be a 1 or it will not save, thus giving a status of -1.
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