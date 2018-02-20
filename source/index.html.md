---
title: LogUp Documentation v1.0.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2


---


# Introduction


> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.


The LogUp API is organized around REST. To interact with our APIs you have to use the "idGate" and "secretKey" received
after the gate creation. Remember to never expose your keys in any public website's client-side code.
All API responses is in JSON format. 

Base URLs:
<a href="https://api.logup.co/v1_0">https://api.logup.co/v1_0</a>


# Authentication

This API supports two modes of authentication:
<ul>
    <li><a href="#oauth2">OAuth2 Authentication</a>: Create authentication token to be used as HTTP Authentication</li>
    <li><a href="#http-authentication">HTTP Authentication</a>: Useful to access all APIs</li>
</ul>

## OAuth2

<a id="opId OAuth2 authentication"></a>
Retrieve the OAuth Access token to be used as HTTP Authentication Header. 
### Create The Authentication Token


<a id="opIdCreate The Authentication Token"></a>


> Code samples


```shell
# You can also use wget
curl -X POST https://api.logup.co/v1_0/oauth/token \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'


```


```http
POST https://api.logup.co/v1_0/oauth/token HTTP/1.1
Host: api.logup.co
Content-Type: application/json
Accept: application/json


```


```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'


};


$.ajax({
  url: 'https://api.logup.co/v1_0/oauth/token',
  method: 'post',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "client_id": "string",
  "client_secret": "string",
  "grant_type": "client_credentials"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'


};


fetch('https://api.logup.co/v1_0/oauth/token',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}


result = RestClient.post 'https://api.logup.co/v1_0/oauth/token',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}


r = requests.post('https://api.logup.co/v1_0/oauth/token', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://api.logup.co/v1_0/oauth/token");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`POST /oauth/token`


> Body parameter


```json
{
  "client_id": "gate_gateTestRandom",
  "client_secret": "gateSecretKeyRandom",
  "grant_type": "client_credentials"
}
```


<h3 id="Create_an_authentication_token-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|client_id|body|string|true|Gate's id received after you created your gate|
|client_secret|body|string|true|Secret key received after you created your gate|
|grant_type|body|string|true|Grant type that you're requesting. The only grant_type supported is: "client_credentials"|


> Example responses


```json
{
  "access_token": "EAWkU7gMdB3BjngA3VFy6mL42TMaThGhS2ceEgnLxA2YhSU9DwAWTJEAIB7umoblKoXk5Y1x3vt8qbudkI8twX23DXou4oc4PwSK9Zgx0dYc9qgqooWMmnnoMd5lTEuj",
  "token_type": "Baerer",
  "expires_in": 3600
}
```


<h3 id="Create_an_authentication_token-return">Return</h3>
Return the Authentication Token created

## HTTP Authentication

<a id="opId HTTP authentication"></a>
It's the authentication method you have to use in order to access all APIs. This authentication is performed via HTTP
Basic Auth with the Bearer scheme. <br>
All API requests must be made over HTTPS. Calls made over plain HTTP will fail. API requests without authentication will
also fail. <br>

You've to use this header in order to perform a correct API request: <br>
`-H "Authorization: Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS"`

# Interacting With The API

## Status Codes

Status codes implemented by LogUp endpoints:
<ul>
    <li>`200 OK` Successful request</li>
    <li>`201 Created` New object created</li>
    <li>`204 No Content` Object deleted</li>
    <li>`400 Bad Request` Returns JSON with the error message</li>
</ul>

## Making Requests

LogUp API implements following HTTP verbs:

<ul>
    <li><b>GET</b> - Read resources</li>
    <li><b>DELETE</b> - Remove resources</li>
    <li><b>POST</b> - Create new resources</li>
    <li><b>PUT</b> - Modify existing resources</li>
</ul>

# Subscription


Endpoint to be used to manage subscriptions. Thanks to this endpoint, you can retrieve subscription db values, 
update db values and delete db values.


## Update Subscription Db Values


<a id="opIdUpdate subscription db values"></a>


> Code samples


```shell
# You can also use wget
curl -X PUT https://api.logup.co/v1_0/subscription/{id_subscription}/db \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'
  -H 'Authorization: Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
```


```http
PUT https://api.logup.co/v1_0/subscription/{id_subscription}/db HTTP/1.1
Host: api.logup.co
Content-Type: application/json
Accept: application/json
Authorization: Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS

```


```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization': Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'

};


$.ajax({
  url: 'https://api.logup.co/v1_0/subscription/{id_subscription}/db',
  method: 'put',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "data": [
    {
      "key": "country",
      "value": "italy"
    },
    {
      "key": "age",
      "value": 21
    },
    {
      "key": "alreadySubscribed",
      "value": true
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization': 'Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'

};


fetch('https://api.logup.co/v1_0/subscription/{id_subscription}/db',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
}


result = RestClient.put 'https://api.logup.co/v1_0/subscription/{id_subscription}/db',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
}


r = requests.put('https://api.logup.co/v1_0/subscription/{id_subscription}/db', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://api.logup.co/v1_0/subscription/{id_subscription}/db");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`PUT /subscription/{id_subscription}/db`


Update bb values. If the key-value pair does not exist in LogUp DB, we create that key-value pair.
The are some limitations:
<ul>
    <li>Each subscription cannot have more than 20 fields (20 different keys)</li>
    <li>Each key can’t be longer than 32 characters</li>
    <li>Each value must be less than 1 kilobyte. Since we use UTF8 charset, this means no more than 1024 characters</li>
    <li>each value can contain only numbers, strings or boolean values</li>
</ul>

> Body parameter


```json
{
  "data": [
    {
      "key": "country",
      "value": "italy"
    },
    {
      "key": "age",
      "value": 21
    },
    {
      "key": "alreadySubscribed",
      "value": true
    }
  ]
}
```


<h3 id="Update_subscription_db_values-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id_subscription|path|string|true|Subscription's id you want to manage|
|data|body|[oneOf]|true|JSON Array containing all db values to be updated|

*oneOf*

|Name|Type|Required|Description|
|---|---|---|---|
|key|string|false|Key parameter|
|value|string|false|String value associated with the key|


*xor*

|Name|Type|Required|Description|
|---|---|---|---|
|key|string|false|Key parameter|
|value|integer|false|Integer value associated with the key|


*xor*

|Name|Type|Required|Description|
|---|---|---|---|
|key|string|false|Key parameter|
|value|boolean|false|Boolean value associated with the key|

> Example responses


```json
{
  "alreadySubscribed": false,
  "country": "italy",
  "age": 20
}
```


<h3 id="Update_subscription_db_values-responses">Return</h3>
Return subscription db values updated

## Get Subscription Db Values


<a id="opIdGet subscription values saved into db"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://api.logup.co/v1_0/subscription/{id_subscription}/db \
  -H 'Accept: application/json'\
  -H 'Authorization: Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
```


```http
GET https://api.logup.co/v1_0/subscription/{id_subscription}/db HTTP/1.1
Host: api.logup.co

Accept: application/json
Authorization: Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS

```


```javascript
var headers = {
  'Accept':'application/json',
  'Authorization': 'Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'

};


$.ajax({
  url: 'https://api.logup.co/v1_0/subscription/{id_subscription}/db',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json',
  'Authorization': 'Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
};


fetch('https://api.logup.co/v1_0/subscription/{id_subscription}/db',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
}


result = RestClient.get 'https://api.logup.co/v1_0/subscription/{id_subscription}/db',
  params: {
  }, headers: headers
  
p JSON.parse(result)
```


```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
}


r = requests.get('https://api.logup.co/v1_0/subscription/{id_subscription}/db', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://api.logup.co/v1_0/subscription/{id_subscription}/db");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /subscription/{id_subscription}/db`


Get values saved into LogUp DB. If you want to get some specific values, use query string parameter "keys". If you
set the keys query parameters and one of the key does not exist in our DB, that key will not be in the JSON response.


<h3 id="Get_subscription_values_saved_into_db-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id_subscription|path|string|true|Subscription's id you want to manage|
|keys|query|array[string]|false|You've to set this parameter if you want to receive some specific keys and associated values. Example: name,age,{other_keys},...|


> Example responses


```json
{
  "alreadySubscribed": false,
  "country": "italy",
  "age": 20
}
```


<h3 id="Get_subscription_values_saved_into_db-return">Return</h3>
Subscription db values loaded.

## Delete Subscription Db Values


<a id="opIdDelete subscription db values"></a>


> Code samples


```shell
# You can also use wget
curl -X DELETE https://api.logup.co/v1_0/subscription/{id_subscription}/db \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS' 


```


```http
DELETE https://api.logup.co/v1_0/subscription/{id_subscription}/db HTTP/1.1
Host: api.logup.co
Content-Type: application/json
Authorization: Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS

```


```javascript
var headers = {
  'Content-Type':'application/json',
  'Authorization': 'Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'


};


$.ajax({
  url: 'https://api.logup.co/v1_0/subscription/{id_subscription}/db',
  method: 'delete',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "keys": [
    "name",
    "age"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Authorization': Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'


};


fetch('https://api.logup.co/v1_0/subscription/{id_subscription}/db',
{
  method: 'DELETE',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Content-Type' => 'application/json',
  'Authorization' => Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
}


result = RestClient.delete 'https://api.logup.co/v1_0/subscription/{id_subscription}/db',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Authorization': Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
}


r = requests.delete('https://api.logup.co/v1_0/subscription/{id_subscription}/db', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://api.logup.co/v1_0/subscription/{id_subscription}/db");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`DELETE /subscription/{id_subscription}/db`

Delete db values associated with the subscription path parameter.


> Body parameter


```json
{
  "keys": [
    "name",
    "age"
  ]
}
```


<h3 id="Delete_subscription_db_values-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id_subscription|path|string|true|Subscription's id you want to manage|
|keys|body|array[string]|true|List of keys you want to delete|

<h3 id="Delete_subscription_db_values-responses">Responses</h3>
Subscription db values deleted.

# Verification

You have to use this endpoint to verify LogUp tokens received. 
You'll find the token needed to make this API call into the redirect URL query parameters logupToken={logupToken}. 
This logupToken is generated when the user finished his logup procedure.


## Verify Logup Token


<a id="opIdVerify Logup Token"></a>


> Code samples


```shell
# You can also use wget
curl -X POST https://api.logup.co/v1_0/verification \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'
  -H 'Authorization: Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
```


```http
POST https://api.logup.co/v1_0/verification HTTP/1.1
Host: api.logup.co
Content-Type: application/json
Accept: application/json
Authorization: Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS
```


```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization': Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
};


$.ajax({
  url: 'https://api.logup.co/v1_0/verification',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "logupToken": "gGJBBsskteAoZnFXRIzwnC9OQo2NuSBZIfBd8hcd8NaClHMP7LgeModXhGT2CiBSzMj5i0lLPUnW5oworEKIcg43NDl1zTxbMR7MeWpmtI9i067rZCHDq38sl4c7iXVq"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization': 'Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
};


fetch('https://api.logup.co/v1_0/verification',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
}


result = RestClient.post 'https://api.logup.co/v1_0/verification',
  params: {
  }, headers: headers

p JSON.parse(result)
```


```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
}


r = requests.post('https://api.logup.co/v1_0/verification', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://api.logup.co/v1_0/verification");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`POST /verification`

Verify logup token received


> Body parameter


```json
{
  "logupToken": "gGJBBsskteAoZnFXRIzwnC9OQo2NuSBZIfBd8hcd8NaClHMP7LgeModXhGT2CiBSzMj5i0lLPUnW5oworEKIcg43NDl1zTxbMR7MeWpmtI9i067rZCHDq38sl4c7iXVq"
}
```


<h3 id="Verify_logup_token_received-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|logupToken|body|string|true|Logup token received after the user redirect. You'll find it after the redirect url into the query string ?logupToken={logupToken}|

> Example responses


```json
{
  "verified": true,
  "errorMessage": "INVALID_LOGUP_TOKEN",
  "idActor": "acr_testActorLogUp",
  "idSubscription": "sub_testSubscription",
  "db": {
    "keyName": true
  }
}
```


<h3 id="Verify_logup_token_received-responses">Return</h3>
User which has completed the logup procedure.