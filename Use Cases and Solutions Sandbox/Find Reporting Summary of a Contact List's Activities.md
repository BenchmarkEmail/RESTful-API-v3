- [Problem Statement](#problem-statement)
    - [Solution](#solution)
    - [Directions and Steps](#directions-and-steps)

# Problem Statement

Given a list id,
Then I want to see the aggregate summary of metrics for that list, ie:   \
Active Contact Counts, Bounced Contact Count, Hard Bounce Contact Count, Not Optin Contact Count, Optin Contact Count, \
Soft Contact Count, Unsubscribe Contact Count

---

## Prerequisites

1. A free or paid Benchmark Email account. Both account types provide free API usage. Sign up here, [link](https://ui.benchmarkemail.com/Integrate#AP)
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

2. Get a list id 
    1. 3 ways to get the list id #: 
        1. [Documentation link](https://developer.benchmarkemail.com/#cc3ee91a-0ccb-79c1-9365-c96f8511a68b), 
        1. [General solution](https://docs.google.com/document/d/1WoV5I5hh05CBUGsNpROqHtsvX5-ENawEfR5UHFgZrJQ/edit?usp=sharing), 
        1. [Search a for a list's details by its name](https://docs.google.com/document/d/1WoV5I5hh05CBUGsNpROqHtsvX5-ENawEfR5UHFgZrJQ/edit?usp=sharing)
3. Make a request using your list Id 
   1. `GET /Contact/{{ListID}}/ContactSummary`  [link](https://developer.benchmarkemail.com/#abd3f684-4b7b-b0f3-804d-09b1e98c0c0e)

## Directions and Steps 

1. Open an http client to test a request (we'll use postman, for postman setup see Getting Started )
1. Prerequisite: Have the list id # to search through.
   1. 3 ways to get the list id #: 
      1. [Documentation link](https://developer.benchmarkemail.com/#cc3ee91a-0ccb-79c1-9365-c96f8511a68b), 
      1. [General solution](https://docs.google.com/document/d/1WoV5I5hh05CBUGsNpROqHtsvX5-ENawEfR5UHFgZrJQ/edit?usp=sharing), 
      1. [Search a for a list's details by its name](https://docs.google.com/document/d/1WoV5I5hh05CBUGsNpROqHtsvX5-ENawEfR5UHFgZrJQ/edit?usp=sharing)
1.  Use a GET call ` `
  1.  `GET /Contact/{{ListID}}/ContactSummary ` [link](https://developer.benchmarkemail.com/#abd3f684-4b7b-b0f3-804d-09b1e98c0c0e)
1. Confirm the response provides 
   1. Response status of 200 OK 
   1. Confirm response body 
   1. Response.Status value equals 1 
   1. Response.Data is an object with properties being searched for [image](https://www.dropbox.com/s/tqiwng1c5nsmtae/2018-09-19_13-40-42.png?dl=0)
       1. ActiveContactCount",
       1. BounceContactCount"
       1. HardContactCount"
       1. "NotOptinContactCount"
       1. "OptinContactCount"
       1. "SoftContactCount"
       1. "UnsubscribeContactCount"
