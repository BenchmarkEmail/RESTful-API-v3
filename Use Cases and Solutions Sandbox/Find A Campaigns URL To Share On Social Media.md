- [Problem](#problem)
    - [Solution](#solution)
    - [Directions and Steps](#directions-and-steps)

# Problem

You want to get a summary of common metrics related to your email campaign, such as Opens, Clicks, Bounces, Unsubscribes, etc

---

## Prerequisites

1. A free or paid Benchmark Email account. t will have your secured API token.  [link](https://ui.benchmarkemail.com/Integrate#AP)
1. Always use host of: `https://clientapi.benchmarkemail.com`
1. An HTTP library or HTTP app, such as postman [link](https://www.getpostman.com/), to make API calls

## Solution

<sub>using the Benchmark API v3.0 RESTful endpoints. All our RESTful endpoints documentation found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections)></sub>

## Directions and Steps 

1. Open an http client to test a request (we'll use postman, for postman setup see Getting Started )
1. Use a GET call``
    1.`GET /Emails` [link](https://developer.benchmarkemail.com/#0068614f-f224-141b-b1eb-8768abc0f5d3) 
        1. where the call can be enhanced by using the optional parameters on seen in the [documentation](https://developer.benchmarkemail.com/#0068614f-f224-141b-b1eb-8768abc0f5d3) 
        1. In the response body see the Response.Data array of a list objects. Find the <code>Response.Data[0..n].ID </code>[screenshot](https://www.dropbox.com/s/cbk89hccj3vpvj4/2018-09-13_13-38-31.png?dl=0)
1. Use a GET call
    1. <strong>GET /Emails/{ID}/Report  </strong>[link](https://developer.benchmarkemail.com/#8819bcb9-afc9-9e7c-b31a-44aab47ed758)
1. Confirm the response provides 
    1. a status of 200 OK 
    1. the response body does NOT contain a value of -1 for Response.Status 
    1. Confirm Response.Status value is 1 [screenshot](https://www.dropbox.com/s/ewwb8p0pshwwwxz/2018-09-13_13-41-35.png?dl=0)
1. See the response body for Response.ShareUrl [screenshot](https://www.dropbox.com/s/bijnxgti7e5ga6l/2018-09-13_13-44-41.png?dl=0)