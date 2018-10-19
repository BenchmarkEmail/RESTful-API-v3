- [Problem Statement](#problem-statement)
    - [Prerequisites](#prerequisites)
    - [Solution](#solution)
        - [Response Notes](#response-notes)
    - [Variations of problem](#variations-of-problem)
    - [Index of all Problem Statements link](#index-of-all-problem-statements-link)

# Problem Statement

Add an email address and the contact information to a list

## Prerequisites

---

1. A client to make an API call, such as postman [link](https://www.getpostman.com/)
1. Use base URL/Host : `https://clientapi.benchmarkemail.com`
1. RESTful collection found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections) 
1. A benchmark email account. API usage is included with a free account [link](https://ui.benchmarkemail.com/Login)
   * Your API Key, for your requests to be validated. Found [here](https://ui.benchmarkemail.com/Integrate#API)

## Solution

<sub>using the Benchmark API v3.0 RESTful endpoints</sub>

1. Make an API call to retrieve your list(s) and get its respective list id # [link:](https://developer.benchmarkemail.com/#cc3ee91a-0ccb-79c1-9365-c96f8511a68b). The list id # will be found in the response body.

```js
    GET /Contact
    or
    GET /Contact/?SearchFilter={{SearchFilter}}
     //where SearchFilter is a partial or full name of a list
     //to see full list of parameters available see docs. in link above
     // id found at Response.Data[0..n].ID
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