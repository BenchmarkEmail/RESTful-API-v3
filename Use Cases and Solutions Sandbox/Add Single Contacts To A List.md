# Use Case:

Given an email and the contacts attributes,
Then I want to add the contact to a list.

Variations of problem:



1.  I want to get a list id # for an existing list(s). Solution: continue with this document.
1.  I want to create a new list and get its list id #. Solution: see [link](https://docs.google.com/document/d/15GOHDrPVoQrIyaLcLSj0zB2frJkUj1U6IqpIpwovhik/edit?usp=sharing) 


## Solution:  



1.  Pull my lists and get its respective list id # from by bme account.
    1.  **GET /Contact/ **(scenario to search amongst your pre-existing lists) [link:](https://developer.benchmarkemail.com/#cc3ee91a-0ccb-79c1-9365-c96f8511a68b)
        1.  where SearchFilter is the partial or full name of the list
        1.  where PageSize is the number of items to be returned for each [image:](https://www.dropbox.com/s/h2sw440mz9gfgha/2018-09-06_11-03-40.png?dl=0 )        	
1.  Identify which list I want to add to so I can add contact(s) to that specific list, 
1.  Add your contact using the listID and your contacts information


## Directions and Steps 



1.  Open an http client to test a request (we'll use postman, for postman setup see Getting Started )
1.  To add a contact, you need to know the list name and its ID#. This is done by one of two ways: 
    1.  finding the list ID amongst your pre-existing list, see 3, below
    1.  making a new list, to make a new list see instructions, [Creating a new list](https://docs.google.com/document/d/15GOHDrPVoQrIyaLcLSj0zB2frJkUj1U6IqpIpwovhik/edit?usp=sharing), and return here afterwards
1.  Get your list ID for the list you will add your contact(s) to.
    1.  **GET /Contact ** (option 2a above)** ** ** **
        1.  In the response body see the Response.Data array of a list objects. Find the `Response.Data[0..n].ID` . This is the needed id for the next step
1.  Adding your new contact by providing the contacts information and the listID from 2a or 2b above
    1.  **POST /Contact/{{ListID}}/ContactDetails **[link](https://developer.benchmarkemail.com/#375fa862-2ac6-9d5d-3669-6e9a23524241 ) 
        1.  where the request body requires information seen here `{"Data":{"Email":"{{EMail}}","FirstName":"{{FirstName}}","LastName":"{{LastName}}","EmailPerm":"{{1|0}}"}}`. 
            1.  Note the key in the request of "EmailPerm". This be a 1 or it will not save and will be an error
        1.  Send the POST request and confirm two things
            1.  the response status is 200 OK and 
            1.  response body does not have a status of -1 or an 'error' property   	[screenshot](https://www.dropbox.com/s/yyw0dv5l90ymaqx/2018-09-06_11-36-07.png?dl=0) 
            1.  Confirm your success screenshot