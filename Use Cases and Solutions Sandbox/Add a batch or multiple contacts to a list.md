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

1. Secure each of the 3 requests below by placing your Benchmark Email API Token. see prerequisite #1 above, in the header of your request. (Don't have a token?  Get one free, see pre-requisite #1 above.)

```javascript
// example of headers from a python3 request
headers = {
    'AuthToken': "YOUR_BENCHMARK_EMAIL_API_TOKEN_HERE",
    'Content-Type': "application/json" 
}
// application/json is used for all GET requests
```

This is a 3 step solution which is for uploading the file, mapping the fields and setting the compilation fields

  1. Upload your csv file with the following endpoint. The response will provide you with a new file name in the response body json object. This new name will be used for the subsequent calls 2 and 3, in this process. The new name provided in the response body will be found in the property `Response.Message` property. The value for `Resonse.Message` is a large string of key value pairs, ex <br>
  `"Message": "contact_master_id=15981783&id=hfkff4sq.uv0.csv&f=csvUploadOneEmail.csv&m=0&of=csvUploadOneEmail.csv&redir="` <br>
  Parse the string to find the the key/value pair `id=NEW_UPLOADED_FILE_NAME.csv`, ex:<br>
  `id=hfkff4sq.uv0.csv`. <br>
  Use your value recieved for the id in the next 2 endpoint requests for their needed `fileName` value. 

```javascript
POST  /Contact/{ListID}/ContactDetails/CSV/Upload
// Upload the file
```

  2. While setting the file mapping, this name , 'id' (above 2.1), should be passed as the value for the field "FileName", below.

```javascript
PATCH /Contact/{ListID}/Mapping
```

  3. While changing the list compilation, this name , 'id' (above 2.1), should be passed as the value for the field "FileName", below.

```javascript
PATCH /Contact/{ListID}/Compilation
```
