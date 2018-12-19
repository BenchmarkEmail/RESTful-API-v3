- [File Upload for csv lists using RESTful API](#file-upload-for-csv-lists-using-restful-api)
- [Problem Statement](#problem-statement)
  - [Prerequisites](#prerequisites)
  - [Solution](#solution)

# File Upload for csv lists using RESTful API

# Problem Statement

 I want to upload multiple contacts to a list.

## Prerequisites

1. A basic .csv file holding your contacts
2. Your list id, if unknown, see Use Case: _'Find a contact list id by searching with its list name'_ [link](https://benchmarkemail.github.io/RESTful-API-v3/)
3. A free or paid Benchmark Email account. Both account types provide free API usage. Sign up here, [link](https://ui.benchmarkemail.com/Integrate#AP)
4. Always use host of: `https://clientapi.benchmarkemail.com`
5. An HTTP library or HTTP app, such as [postman](https://www.getpostman.com/), to make API calls

## Solution

<sub>The following endpoints and more details can be found on [web](https://developer.benchmarkemail.com/) or [github](https://github.com/BenchmarkEmail/RESTful-API-v3/tree/master/Postman%20Collections)</sub>

1. Secure each of the 3 requests below by placing your Benchmark Email API Token in the header of your request. (Don't have a token?  Get one free, see pre-requisite #3 above.)

2. This is a 3 step solution which is for uploading the file, mapping the fields and setting the compilation fields.
   1. Upload your csv file with the following endpoint. The response will provide you with a file name which is a new name and replaces your origial uploaded file name. This new file name, not your original file name, will be used for the subsequent calls 2 and 3, in this process. The new name will be provided in the response body of this call, found in the property `Response.Message`. The value for `Resonse.Message` is a large string of key value pairs combined, ex <br>`"Message": "contact_master_id=15981783&id=hfkff4sq.uv0.csv&f=csvUploadOneEmail.csv&m=0&of=csvUploadOneEmail.csv&redir="` <br>Parse the string to find the the key/value pair `id=NEW_UPLOADED_FILE_NAME.csv`, ex:<br>`id=hfkff4sq.uv0.csv`. <br>

   ```javascript
   // example of headers from a python3 request
   headers = {
        'AuthToken': "YOUR_BENCHMARK_EMAIL_API_TOKEN_HERE",
        'Content-Type': 'application/x-www-form-urlencoded',
        'content-type': 'multipart/form-data'
   }
   // ENDPOINT
   POST  /Contact/{ListID}/ContactDetails/CSV/Upload
   // Upload the file
   //  Use *your* recieved `id` value for the next 2 endpoint requests as the value for their parameter `fileName`. 
   ```

   2. Let's give some context about this field mapping step. First, let's call your csv file the `source file` and the your benchmark email list will be referenced as the `destination file`. Every row of your `source file` contains 1 or more values describing your contact, these values, also known as attributes, are separated by a comma. This `source file` has the same type of value in each column of each row. For example, the first column could be the first name of the contact. Therefore, the `source file` has fifty rows of contacts, then in each row, the first column would contain a first name for that contact or a blank. \n
   Typically the fields have a header row to describe each value When uploading the csv file you did not include, c to benchmark default list headers.h In your original list you have specific labels, also known as csv headers, field names, etc. As you uploaded the list in the previous step, benchmark email has your list now and also has your benchmark email list you reference with the `list id`. You'll now map your 'uploaded' field names with your 'benchmark email list' field names. ex: <br>If your uploaded list has field `email` you will map it to the benchmark email field `Email Address`, meaning the default list keys will take your values of your field names in your original list. While setting the field mapping, the 'id' (above 2.1), will be used as the value for the field "fileName", in this request below. For "Field" attribute please find the below value used by the system for the field.<br>(Note : In the example field/value mapping below, it may change if you edited the benchmark email contact list's field names. To validate exact fields and their values, use `GET /Contact/{LISTID}`, (image:  https://www.screencast.com/t/40z7copdWruP).

   ```javascript
   // endpoint
   PATCH /Contact/{ListID}/Mapping

   // Request Body
   {
     FileName: '{{FileName}}',
     OriginalFileName: '{{OriginalFileName}}',
     Mode: '0',
     Login: '{{login}}',
     Token: '{{AuthToken}}',
     Data: {Field: [ {{FieldJSONArray}} ]} // see below
   }
   ```

    `{{FieldJSONArray}}` value for attribute `Field` above as `Data.Field.[JSONArray]`

    | Field <br>(benchmark email list's fields) | Value<br>(your field names of your uploaded list) |
    | ----------------------------------------- | ------------------------------------------------- |
    | Email Address                             | email                                             |
    | First Name                                | firstname                                         |
    | Last Name                                 | lastname                                          |
    | Middle Name                               | middlename                                        |
    | Email Preference                          | emailtype                                         |
    | Address                                   | field1                                            |
    | City                                      | field2                                            |
    | State                                     | field3                                            |
    | Zip                                       | field4                                            |
    | Country                                   | field5                                            |
    | Phone                                     | field6                                            |
    | Fax                                       | field7                                            |
    | Cell phone                                | field8                                            |
    | Company name                              | field9                                            |
    | Job title                                 | field10                                           |
    | Business phone                            | field11                                           |
    | Business fax                              | field12                                           |
    | Business address                          | field13                                           |
    | Business city                             | field14                                           |
    | Business state                            | field15                                           |
    | Business zip                              | field16                                           |
    | Business country                          | field17                                           |
    | Notes                                     | field18                                           |
    | Date 1                                    | field19                                           |
    | Date 2                                    | field20                                           |
    | Extra 3                                   | field21                                           |
    | Extra 4                                   | field22                                           |
    | Extra 5                                   | field23                                           |
    | xtra 6                                    | field24                                           |

   1. While changing the list compilation, find 'id' (above 2.1), to be used as the value for the field "fileName", below

    ```javascript
    PATCH /Contact/{ListID}/Compilation
    ```
