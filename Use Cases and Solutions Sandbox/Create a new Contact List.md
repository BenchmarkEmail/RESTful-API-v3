
# Use Case:

Given a new List Name, \
Then I want create a new list and get its list Id #

Variation of problem. I want to get the list Id # of pre-existing lists [link](https://docs.google.com/document/d/1WoV5I5hh05CBUGsNpROqHtsvX5-ENawEfR5UHFgZrJQ/edit?usp=sharing)


## Solution:  



1.  Make a POST request with the information for your new list
    1.  **POST /Contact **
        1.  where the minimal data needed is {"Data":{"Name":"{{Name}}","Description":"{{Description}}"}} 	
1.  Take the ID returned for future use in API calls      


## Directions and Steps 



1.  Open an http client to test a request (we'll use postman, for postman setup see Getting Started )
1.  Use a POST call with minimal information to create the list** **
    1.  **POST /Contact/ ** [link](https://developer.benchmarkemail.com/#16e1491e-69f8-e71a-c374-d99e55c322cf ) 
        1.  where the body of the request has two properties that need values, see cURL example in link above
1.  Confirm the response provides 
    1.  a status of 200 OK 
    1.  the response body does NOT contain an Response.Errors array property and/or the response body does NOT contain a value of -1 for Response.Status screenshot [screenshot](https://www.dropbox.com/s/qnjkgxfizio8aqk/2018-09-13_13-17-08.png?dl=0)
    1.  Confirm Response.Status value is 1 [screenshot](https://www.dropbox.com/s/1sktz2e2yfg60dl/2018-09-13_13-22-21.png?dl=0)