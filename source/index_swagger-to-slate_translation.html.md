--- 

title: LogUp Documentation 

language_tabs: 
   - shell 

toc_footers: 
   - <a href='#'>Sign Up for a Developer Key</a> 
   - <a href='https://github.com/lavkumarv'>Documentation Powered by lav</a> 

includes: 
   - errors 

search: true 

--- 

# Introduction 

LogUp Public API documentation 

**Version:** 1.0.0 

# /ACTOR/{ID_ACTOR}/DB
## ***DELETE*** 

**Summary:** Delete actor db values

**Description:** 

### HTTP Request 
`***DELETE*** /actor/{id_actor}/db` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id_actor | path | Actor's id you want to manage | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Actor db values deleted |

## ***GET*** 

**Summary:** Get actor values saved into db

**Description:** If you want to get some specific values, use query string parameter keys

### HTTP Request 
`***GET*** /actor/{id_actor}/db` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id_actor | path | Actor's id you want to manage | Yes |  |
| keys | query | You've to set this parameter if you want to receive some specific keys and associated values. Example: name,age,{other_keys},... | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Actor db values served |

## ***PUT*** 

**Summary:** Update actor db values

**Description:** 

### HTTP Request 
`***PUT*** /actor/{id_actor}/db` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id_actor | path | Actor's id you want to manage | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Actors db values updated.  |

# /OAUTH/TOKEN
## ***POST*** 

**Summary:** Create an authentication token

**Description:** 

### HTTP Request 
`***POST*** /oauth/token` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Authentication token created |

# /VERIFICATION
## ***POST*** 

**Summary:** Verify logup token received

### HTTP Request 
`***POST*** /verification` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | EndPoint called correctly |

<!-- Converted with the swagger-to-slate https://github.com/lavkumarv/swagger-to-slate -->
