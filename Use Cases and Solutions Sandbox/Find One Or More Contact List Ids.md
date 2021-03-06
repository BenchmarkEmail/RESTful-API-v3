- [Use Case:](#problem-statement)
    - [Solution](#solution)
    - [Variation(s) of problem.](#variations-of-problem)

# Problem Statement

Given a benchmarkemail account. \
Then How do I see all its lists and the details of those lists?

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

1. In the benchmark email [postman collection](https://developer.benchmarkemail.com/) left navigation, find the reference :  \
`GET Get a list of contacts ` [link](https://developer.benchmarkemail.com/#cc3ee91a-0ccb-79c1-9365-c96f8511a68b) 
    1. Navigation directions in postman collection:
        1. Go to left navigation of postman collection
        1. In Directory: Contact
        1. In Subdirectory: General 
        1. Find _GET 'Get a list of contacts' _[link](https://developer.benchmarkemail.com/#cc3ee91a-0ccb-79c1-9365-c96f8511a68b) 
        1. https://clientapi.benchmarkemail.com/Contact/`?SearchFilter={{SearchFilter}}`
        1. Where the "SearchFilter" will be whole or partial list name	
1. Take the ID returned for future use in API calls      
1. Confirm the response provides 
    1. a status of 200 OK 
    1. the response body does NOT contain an Response.Errors array property and/or the response body does NOT contain a value of -1 for Response.Status 
    1. Confirm Response.Status value is 1 [screenshot](https://www.dropbox.com/s/1sktz2e2yfg60dl/2018-09-13_13-22-21.png?dl=0)

## Variation(s) of problem. 

*   I want to make a new list and get its list Id #  [link](https://docs.google.com/document/d/15GOHDrPVoQrIyaLcLSj0zB2frJkUj1U6IqpIpwovhik/edit?usp=sharing)
*   I want to search for a specific list by name to get its details [link](https://docs.google.com/document/d/1WoV5I5hh05CBUGsNpROqHtsvX5-ENawEfR5UHFgZrJQ/edit?usp=sharing)