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


<h1 id="LogUp-Documentation">LogUp Documentation v1.0.0</h1>


> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.


LogUp Public API documentation


Base URLs:


* <a href="https://api.logup.co/dev">https://api.logup.co/dev</a>


# Authentication


- oAuth2 authentication. 


    - Flow: clientCredentials


    - Token URL = [https://api.logup.co/oauth/token](https://api.logup.co/oauth/token)


- HTTP Authentication, scheme: Bearer 


<h1 id="LogUp-Documentation-actor">actor</h1>


Endpoint to be used to manage actors


## Delete actor db values


<a id="opIdDelete actor db values"></a>


> Code samples


```shell
# You can also use wget
curl -X DELETE https://api.logup.co/dev/actor/{id_actor}/db \
  -H 'Content-Type: application/json'


```


```http
DELETE https://api.logup.co/dev/actor/{id_actor}/db HTTP/1.1
Host: api.logup.co
Content-Type: application/json


```


```javascript
var headers = {
  'Content-Type':'application/json'


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
  'Content-Type':'application/json'


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
  'Content-Type' => 'application/json'
}


result = RestClient.delete 'https://api.logup.co/dev/actor/{id_actor}/db',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Content-Type': 'application/json'
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
|body|body|object|true|No description|
|» keys|body|[string]|false|List of keys you want to delete|
|id_actor|path|string|true|Actor's id you want to manage|


<h3 id="Delete_actor_db_values-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Actor db values deleted|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
accessToken
</aside>


## Get_actor_values_saved_into_db


<a id="opIdGet actor values saved into db"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://api.logup.co/dev/actor/{id_actor}/db \
  -H 'Accept: application/json'


```


```http
GET https://api.logup.co/dev/actor/{id_actor}/db HTTP/1.1
Host: api.logup.co


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: 'https://api.logup.co/dev/actor/{id_actor}/db',
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
  'Accept':'application/json'


};


fetch('https://api.logup.co/dev/actor/{id_actor}/db',
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
  'Accept' => 'application/json'
}


result = RestClient.get 'https://api.logup.co/dev/actor/{id_actor}/db',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('https://api.logup.co/dev/actor/{id_actor}/db', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://api.logup.co/dev/actor/{id_actor}/db");
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
|keys|query|array[string]|false|You've to set this parameter if you want to receive some specific keys and associated values. Example: name,age,{other_keys},...|
|id_actor|path|string|true|Actor's id you want to manage|


> Example responses


```json
{
  "alreadySubscribed": false,
  "country": "italy",
  "age": 20
}
```


<h3 id="Get_actor_values_saved_into_db-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Actor db values served|[ActorDbs](#schemaactordbs)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
accessToken
</aside>


## Update_actor_db_values


<a id="opIdUpdate actor db values"></a>


> Code samples


```shell
# You can also use wget
curl -X PUT https://api.logup.co/dev/actor/{id_actor}/db \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'


```


```http
PUT https://api.logup.co/dev/actor/{id_actor}/db HTTP/1.1
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
  url: 'https://api.logup.co/dev/actor/{id_actor}/db',
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
  'Accept':'application/json'


};


fetch('https://api.logup.co/dev/actor/{id_actor}/db',
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
  'Accept' => 'application/json'
}


result = RestClient.put 'https://api.logup.co/dev/actor/{id_actor}/db',
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


r = requests.put('https://api.logup.co/dev/actor/{id_actor}/db', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://api.logup.co/dev/actor/{id_actor}/db");
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
|body|body|[DBUpdateData](#schemadbupdatedata)|true|No description|
|id_actor|path|string|true|Actor's id you want to manage|


> Example responses


```json
{
  "alreadySubscribed": false,
  "country": "italy",
  "age": 20
}
```


<h3 id="Update_actor_db_values-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Actors db values updated.|[ActorDbs](#schemaactordbs)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
accessToken
</aside>


<h1 id="LogUp-Documentation-oauth">oauth</h1>


Endpoint to be used to create new access token


## Create_an_authentication_token


<a id="opIdCreate an authentication token"></a>


> Code samples


```shell
# You can also use wget
curl -X POST https://api.logup.co/dev/oauth/token \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'


```


```http
POST https://api.logup.co/dev/oauth/token HTTP/1.1
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
  url: 'https://api.logup.co/dev/oauth/token',
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


fetch('https://api.logup.co/dev/oauth/token',
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


result = RestClient.post 'https://api.logup.co/dev/oauth/token',
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


r = requests.post('https://api.logup.co/dev/oauth/token', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://api.logup.co/dev/oauth/token");
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


*Create an authentication token*


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
|body|body|[CreateAccessToken](#schemacreateaccesstoken)|true|No description|


> Example responses


```json
{
  "access_token": "EAWkU7gMdB3BjngA3VFy6mL42TMaThGhS2ceEgnLxA2YhSU9DwAWTJEAIB7umoblKoXk5Y1x3vt8qbudkI8twX23DXou4oc4PwSK9Zgx0dYc9qgqooWMmnnoMd5lTEuj",
  "token_type": "Baerer",
  "expires_in": 3600
}
```


<h3 id="Create_an_authentication_token-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Authentication token created|[AccessToken](#schemaaccesstoken)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiOAuth
</aside>


<h1 id="LogUp-Documentation-verification">verification</h1>


Endpoint to be used to verify logup tokens received


## Verify_logup_token_received


<a id="opIdVerify logup token received"></a>


> Code samples


```shell
# You can also use wget
curl -X POST https://api.logup.co/dev/verification \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'


```


```http
POST https://api.logup.co/dev/verification HTTP/1.1
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
  url: 'https://api.logup.co/dev/verification',
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
  'Accept':'application/json'


};


fetch('https://api.logup.co/dev/verification',
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


result = RestClient.post 'https://api.logup.co/dev/verification',
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


r = requests.post('https://api.logup.co/dev/verification', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://api.logup.co/dev/verification");
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
|body|body|object|true|No description|
|» logupToken|body|string|false|Logup token received after the user redirect. You'll find it after the redirect url into the query string ?logupToken=randomString|


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


<h3 id="Verify_logup_token_received-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|EndPoint called correctly|[Verification](#schemaverification)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
accessToken
</aside>


# Schemas


<h2 id="tocSaccesstoken">AccessToken</h2>


<a id="schemaaccesstoken"></a>


```json
{
  "access_token": "EAWkU7gMdB3BjngA3VFy6mL42TMaThGhS2ceEgnLxA2YhSU9DwAWTJEAIB7umoblKoXk5Y1x3vt8qbudkI8twX23DXou4oc4PwSK9Zgx0dYc9qgqooWMmnnoMd5lTEuj",
  "token_type": "Baerer",
  "expires_in": 3600
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|access_token|string|false|Access token to be used to call APIs|
|token_type|string|false|Token type created|
|expires_in|integer|false|Issued access token TTL (time to live), in seconds|


<h2 id="tocSactordbs">ActorDbs</h2>


<a id="schemaactordbs"></a>


```json
{
  "alreadySubscribed": false,
  "country": "italy",
  "age": 20
}
```


### Properties


*oneOf*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[DbBoolean](#schemadbboolean)|false|No description|


*xor*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[DbInteger](#schemadbinteger)|false|No description|


*xor*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[DbString](#schemadbstring)|false|No description|


<h2 id="tocScreateaccesstoken">CreateAccessToken</h2>


<a id="schemacreateaccesstoken"></a>


```json
{
  "client_id": "string",
  "client_secret": "string",
  "grant_type": "client_credentials"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|client_id|string|false|Gate'd is|
|client_secret|string|false|Secret key|
|grant_type|string|false|Grant type that you're requesting|


#### Enumerated Values


|Property|Value|
|---|---|
|grant_type|client_credentials|


<h2 id="tocSdbstring">DbString</h2>


<a id="schemadbstring"></a>


```json
{
  "keyName": "Italy"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|keyName|string|false|KeyName is the key name you've previously setted|


<h2 id="tocSdbinteger">DbInteger</h2>


<a id="schemadbinteger"></a>


```json
{
  "keyName": 20
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|keyName|integer|false|KeyName is the key name you've previously setted|


<h2 id="tocSdbboolean">DbBoolean</h2>


<a id="schemadbboolean"></a>


```json
{
  "keyName": true
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|keyName|boolean|false|KeyName is the key name you've previously setted|


<h2 id="tocSdbupdatedata">DBUpdateData</h2>


<a id="schemadbupdatedata"></a>


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


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|data|[oneOf]|false|No description|


*oneOf*


|Name|Type|Required|Description|
|---|---|---|---|
|» *anonymous*|[DbUpdateString](#schemadbupdatestring)|false|No description|


*xor*


|Name|Type|Required|Description|
|---|---|---|---|
|» *anonymous*|[DbUpdateInteger](#schemadbupdateinteger)|false|No description|


*xor*


|Name|Type|Required|Description|
|---|---|---|---|
|» *anonymous*|[DbUpdateBoolean](#schemadbupdateboolean)|false|No description|


<h2 id="tocSdbupdatestring">DbUpdateString</h2>


<a id="schemadbupdatestring"></a>


```json
{
  "key": "string",
  "value": "string"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|key|string|false|No description|
|value|string|false|No description|


<h2 id="tocSdbupdateinteger">DbUpdateInteger</h2>


<a id="schemadbupdateinteger"></a>


```json
{
  "key": "string",
  "value": 0
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|key|string|false|No description|
|value|integer|false|No description|


<h2 id="tocSdbupdateboolean">DbUpdateBoolean</h2>


<a id="schemadbupdateboolean"></a>


```json
{
  "key": "string",
  "value": true
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|key|string|false|No description|
|value|boolean|false|No description|


<h2 id="tocSverification">Verification</h2>


<a id="schemaverification"></a>


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


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|verified|boolean|false|True if the logupToken sent has been verified, false otherwise|
|errorMessage|string|false|You'll find this parameter when verified is equals to false. It's the error message|
|idActor|string|false|No description|
|idSubscription|string|false|No description|
|db|[ActorDbs](#schemaactordbs)|false|No description|


#### Enumerated Values


|Property|Value|
|---|---|
|errorMessage|INVALID_LOGUP_TOKEN|


