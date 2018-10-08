# Use Case:

Given a list name, \
Then how to find its list Id?


## Solution:  



1.  Obtain your [API token](https://ui.benchmarkemail.com/Integrate#API) from your benchmark email account.
1.  Place the API token in your API client of choice, such as [postman](https://www.getpostman.com/apps) or your code 
    1.  For additional information on postman, please see _[Getting Started](https://drive.google.com/a/benchmarkemail.com/open?id=1j4nmyGE3Obepq4-ETSVANoMbY-7OWUIYF1_jlXfXUr4)_
1.  Find the benchmark email [postman collection](https://developer.benchmarkemail.com/), in the left navigation, find the reference : _GET 'Get a list of contacts' _[link](https://developer.benchmarkemail.com/#cc3ee91a-0ccb-79c1-9365-c96f8511a68b)
    1.  Navigation directions in postman collection: 
        1.  Go to left navigation of postman collection
        1.  In Directory: Contact
        1.  In Subdirectory: General 
        1.  Find _GET 'Get a list of contacts' _[link](https://developer.benchmarkemail.com/#cc3ee91a-0ccb-79c1-9365-c96f8511a68b)
        1.  Extra tip: Add a "SearchFilter" query string parameter to search the title of the list name using a value of a whole or partial list list name	 \
ex. `https://clientapi.benchmarkemail.com/Contact/?SearchFilter={{SearchFilter}}`
1.  Send Request
1.  If  Response HTTP Headers status to be '200 OK'
    1.  Check response body for 'Response.Status' to be a value of 1 [image](https://www.dropbox.com/s/1sktz2e2yfg60dl/2018-09-13_13-22-21.png?dl=0)
    1.  Take the ID returned for future use in other endpoint requests
1.  Confirm no errors in response body. The response body should NOT have 
    1.  Response.Errors array property value
    1.  Response.Status value of -1

Tags: "Find Id of a list", "only have list name", "list name"


## Variations of Problem

I want to make a new list and get its list Id #  [link](https://docs.google.com/document/d/15GOHDrPVoQrIyaLcLSj0zB2frJkUj1U6IqpIpwovhik/edit?usp=sharing)

I have my list Id # and want to find its list name. [link](https://docs.google.com/document/d/1b4YkPwiQ1p3yKIpAz4XF2jpQL0rAKRznedIFDPiH7ak/edit?usp=sharing) 
