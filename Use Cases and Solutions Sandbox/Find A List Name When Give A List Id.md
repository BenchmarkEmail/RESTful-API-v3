# Use Case

 Given a list id, \
 When I want the list details like name, creation date, active contact count, the fields being used for the contacts. \
 Then what endpoint do I use?

---

## Solution


1.  Make a request using your list Id
    1.  **GET /Contact/{{ListID}}**
1.  Response body will have all information about the list or segment    

## Directions and Steps 

1.  Open an http client to test a request (we'll use postman, for postman setup see Getting Started )
1.  Prerequisite: you already have a list id but nothing else.
1.  Use a GET call ** **
    1.  **GET /Contact/{{ListID}} ** [link](https://developer.benchmarkemail.com/#dfa2a8a6-f1ba-d4b8-4d9f-d3b637be2291) 
1.  Confirm the response provides 
    1.  a status of 200 OK 
    1.  the response body does NOT contain a value of -1 for Response.Status  [screenshot](https://www.dropbox.com/s/kwu27jjk93nuk5y/2018-09-17_08-25-29.png?dl=0)
    1.  Confirm Response.Status value equals 1 [screenshot](https://www.dropbox.com/s/38tjd7hz0j1jo2h/2018-09-17_08-26-57.png?dl=0)