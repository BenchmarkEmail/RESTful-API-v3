- [Use Case](#use-case)
    - [Solution](#solution)
    - [Directions and Steps](#directions-and-steps)
  
# Use Case

Given a list id,
Then I want to see the unsubscribed recipients on the list.

## Solution 

1. Make a request using your list Id and adding the 1 query-string parameter seen below
    1. `GET /Contact/{{ListID}}/ContactDetails`
        1. Where the 'Filter' is a value of 100, see docs
2. Response body will have all list of all contacts in the list that have unsubscribed    

## Directions and Steps 

1. Open an http client to test a request (we'll use postman, for postman setup see Getting Started )
1. Prerequisite: Have the list id # to search through.
1. Use a GET call ` `
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