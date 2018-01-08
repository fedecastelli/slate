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


<h1 id="LogUp-Documentation">Introduction</h1>


> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.


The LogUp API is organized around REST. To interact with our APIs you have to use the "idGate" and "secretKey" received
after the gate creation. Remember to never expose your keys in any public website's client-side code.
All API responses is in JSON format. 

Base URLs:
<a href="https://api.logup.co/1_0">https://api.logup.co/1_0</a>


<h1 id="LogUp-Documentation-authentication">Authentication</h1>

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
curl -X POST https://api.logup.co/1_0/oauth/token \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'


```


```http
POST https://api.logup.co/1_0/oauth/token HTTP/1.1
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
  url: 'https://api.logup.co/1_0/oauth/token',
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


fetch('https://api.logup.co/1_0/oauth/token',
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


result = RestClient.post 'https://api.logup.co/1_0/oauth/token',
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


r = requests.post('https://api.logup.co/1_0/oauth/token', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://api.logup.co/1_0/oauth/token");
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


*Create the authentication token*


> Body parameter


```json
{
  "client_id": "string",
  "client_secret": "string",
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


<h1 id="LogUp-Documentation-actor">Actor</h1>


Endpoint to be used to manage actors. An actor is the identity of a user inside LogUp. An Actor in LogUp is a user
subscribed to your gate. Thanks to this endpoint, you can retrieve actor db values, update db values and db actor db 
values.

## Delete actor db values


<a id="opIdDelete actor db values"></a>


> Code samples


```shell
# You can also use wget
curl -X DELETE https://api.logup.co/dev/actor/{id_actor}/db \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS' 


```


```http
DELETE https://api.logup.co/dev/actor/{id_actor}/db HTTP/1.1
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
  url: 'https://api.logup.co/dev/actor/{id_actor}/db',
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


fetch('https://api.logup.co/dev/actor/{id_actor}/db',
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


result = RestClient.delete 'https://api.logup.co/dev/actor/{id_actor}/db',
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


r = requests.delete('https://api.logup.co/dev/actor/{id_actor}/db', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://api.logup.co/dev/actor/{id_actor}/db");
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


`DELETE /actor/{id_actor}/db`


*Delete actor db values*


> Body parameter


```json
{
  "keys": [
    "name",
    "age"
  ]
}
```


<h3 id="Delete_actor_db_values-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id_actor|path|string|true|Actor's id you want to manage|
|keys|body|array[string]|true|List of keys you want to delete|

<h3 id="Delete_actor_db_values-responses">Responses</h3>
Actor db values deleted.

## Get Actor Db Values


<a id="opIdGet actor values saved into db"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://api.logup.co/1_0/actor/{id_actor}/db \
  -H 'Accept: application/json'\
  -H 'Authorization: Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
```


```http
GET https://api.logup.co/1_0/actor/{id_actor}/db HTTP/1.1
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
  url: 'https://api.logup.co/1_0/actor/{id_actor}/db',
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


fetch('https://api.logup.co/1_0/actor/{id_actor}/db',
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


result = RestClient.get 'https://api.logup.co/1_0/actor/{id_actor}/db',
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


r = requests.get('https://api.logup.co/1_0/actor/{id_actor}/db', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://api.logup.co/1_0/actor/{id_actor}/db");
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


`GET /actor/{id_actor}/db`


*Get actor values saved into db*


If you want to get some specific values, use query string parameter keys


<h3 id="Get_actor_values_saved_into_db-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id_actor|path|string|true|Actor's id you want to manage|
|keys|query|array[string]|false|You've to set this parameter if you want to receive some specific keys and associated values. Example: name,age,{other_keys},...|


> Example responses


```json
{
  "alreadySubscribed": false,
  "country": "italy",
  "age": 20
}
```


<h3 id="Get_actor_values_saved_into_db-responses">Return</h3>
Actor db values loaded


## Update Actor Db Values


<a id="opIdUpdate actor db values"></a>


> Code samples


```shell
# You can also use wget
curl -X PUT https://api.logup.co/1_0/actor/{id_actor}/db \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'
  -H 'Authorization: Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
```


```http
PUT https://api.logup.co/1_0/actor/{id_actor}/db HTTP/1.1
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
  url: 'https://api.logup.co/1_0/actor/{id_actor}/db',
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


fetch('https://api.logup.co/1_0/actor/{id_actor}/db',
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


result = RestClient.put 'https://api.logup.co/1_0/actor/{id_actor}/db',
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


r = requests.put('https://api.logup.co/1_0/actor/{id_actor}/db', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://api.logup.co/1_0/actor/{id_actor}/db");
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


`PUT /actor/{id_actor}/db`


*Update actor db values*


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


<h3 id="Update_actor_db_values-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id_actor|path|string|true|Actor's id you want to manage|
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


<h3 id="Update_actor_db_values-responses">Return</h3>
Return actor db values updated


<h1 id="LogUp-Documentation-verification">Verification</h1>


Endpoint to be used to verify logup tokens received


## Verify Logup Token


<a id="opIdVerify Logup Token"></a>


> Code samples


```shell
# You can also use wget
curl -X POST https://api.logup.co/1_0/verification \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'
  -H 'Authorization: Bearer authToken_test_vuNeT21HiKDPRuhzQwcDSvSS'
```


```http
POST https://api.logup.co/1_0/verification HTTP/1.1
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
  url: 'https://api.logup.co/1_0/verification',
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


fetch('https://api.logup.co/1_0/verification',
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


result = RestClient.post 'https://api.logup.co/1_0/verification',
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


r = requests.post('https://api.logup.co/1_0/verification', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://api.logup.co/1_0/verification");
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


*Verify logup token received*


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
  "idActor": "string",
  "idSubscription": "string",
  "db": {
    "keyName": true
  }
}
```


<h3 id="Verify_logup_token_received-responses">Return</h3>
User which has completed the logup procedure.