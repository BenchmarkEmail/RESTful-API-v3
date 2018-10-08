- [Use Case:](#use-case)
    - [Solution](#solution)
    - [Variation(s) of problem.](#variations-of-problem)
# Use Case:

Given a benchmarkemail account. \
Then How do I see all its lists and the details of those lists?

## Solution

1.  Obtain your [API token](https://ui.benchmarkemail.com/Integrate#API) from your benchmark email account.
1.  Place the API token in your API client of choice, such as [postman](https://www.getpostman.com/apps) or your code 
    1.  For additional information on postman, please see _[Getting Started](https://drive.google.com/a/benchmarkemail.com/open?id=1j4nmyGE3Obepq4-ETSVANoMbY-7OWUIYF1_jlXfXUr4)_
1.  In the benchmark email [postman collection](https://developer.benchmarkemail.com/) left navigation, find the reference :  \
**GET Get a list of contacts ** [link](https://developer.benchmarkemail.com/#cc3ee91a-0ccb-79c1-9365-c96f8511a68b) 
    1.  Navigation directions in postman collection:
        1.  Go to left navigation of postman collection
        1.  In Directory: Contact
        1.  In Subdirectory: General 
        1.  Find _GET 'Get a list of contacts' _[link](https://developer.benchmarkemail.com/#cc3ee91a-0ccb-79c1-9365-c96f8511a68b) 
        1.  https://clientapi.benchmarkemail.com/Contact/**?SearchFilter={{SearchFilter}}**
            1.  Where the "SearchFilter" will be whole or partial list name	
1.  Take the ID returned for future use in API calls      
1.  Confirm the response provides 
    1.  a status of 200 OK 
    1.  the response body does NOT contain an Response.Errors array property and/or the response body does NOT contain a value of -1 for Response.Status 
    1.  Confirm Response.Status value is 1 [screenshot](https://www.dropbox.com/s/1sktz2e2yfg60dl/2018-09-13_13-22-21.png?dl=0)


## Variation(s) of problem. 



*   I want to make a new list and get its list Id #  [link](https://docs.google.com/document/d/15GOHDrPVoQrIyaLcLSj0zB2frJkUj1U6IqpIpwovhik/edit?usp=sharing)
*   I want to search for a specific list by name to get its details [link](https://docs.google.com/document/d/1WoV5I5hh05CBUGsNpROqHtsvX5-ENawEfR5UHFgZrJQ/edit?usp=sharing)