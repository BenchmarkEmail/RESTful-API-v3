- [Problem Statement](#problem-statement)
    - [Solution](#solution)
    - [Directions and Steps](#directions-and-steps)
  
# Problem Statement

Given a list id,
Then I want to see the unsubscribed recipients on the list.

---

## Prerequisites

1. A free or paid Benchmark Email account. It will have your secured API token.  [link](https://ui.benchmarkemail.com/Integrate#AP)
1. Always use host of: `https://clientapi.benchmarkemail.com`
1. An HTTP library or HTTP app, such as postman [link](https://www.getpostman.com/), to make API calls

## Solution

<sub>using the Benchmark API v3.0 RESTful endpoints. All our RESTful endpoints documentation found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections)></sub>

1. Secure your request by placing your Benchmark Email API Token, see prerequisite #1 above, in the header of your request.

```javascript
// example of headers from a python3 request

headers = {
    'AuthToken': "YOUR_BENCHMARK_EMAIL_API_TOKEN_HERE",
    'Content-Type': "application/json" 
}

// application/json is used for all GET requests
```

2. Make a request using your list Id and adding the 1 query-string parameter seen below

```javascript
GET /Contact/{{ListID}}/ContactDetails

// where the 'Filter' is a value of 100, see docs
// response body will have all list of all contacts in the list that have unsubscribed    
```

## Directions and Steps 

    1. `GET /Contact/{{ListID}}/ContactDetails` [link](https://developer.benchmarkemail.com/#efdb4a44-2a7b-92b5-f49c-d59239d4d0d7)
        1. Where the 'Filter' is a value of 100, see [docs ](https://developer.benchmarkemail.com/#efdb4a44-2a7b-92b5-f49c-d59239d4d0d7)
1. Confirm the response provides
    1. a status of 200 OK
    1. If total count is zero, image
       1. response body may have a Response.Status of -1 
       1. Response body may have a Response.Error array with one of the elements holding a message of Response.Error[0..n].message = "NO_RECORDS_FOUND"  
    1. Confirm response body shows count greater than zero by image
       1. Response.Status value equals 1 to validate that count of unsubscribes is greater than 0. Confirm Response.
          1. Response.Count >= 1 confirms unsubscribes greater than zero.
       1. Response.Data array holds object elements of contacts that unsubscribed
            1. Find each object in Response.Data[0..n] to have a property 'Rating' [image](https://www.dropbox.com/s/7hg4tpgq64zla3l/2018-09-17_14-12-35.png?dl=0)