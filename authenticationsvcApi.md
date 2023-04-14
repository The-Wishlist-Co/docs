
[Back to Home](index.md#welcome-to-the-wishlist)


# **Authentication API**
The Authentication API is used to get the access token for invoking The Wishlist APIs.  The default credentials to get the access token are created when a tennant is registered with The Wishlist.  These will be available in the Store Owner Portal.   

Any API call must contain the access token in the authorization header. (Field name is "Authorization" and , Format is "Bearer <access_token>".)

 The API call must also contain X-TWC-Tenant, and the value is the unique tennant ID.

 To generate a token, an HTTP post API call should be made to the authentication server.  (For example, https://auth.au-sandbox.thewishlist.io/auth/realms/suresh_shop_in_dev/protocol/openid-connect/token.)  
 
 As part of the POST you should pass the grant type which is always client_credentials, and client_id and client_secret with the value that you received from the tenant configuration.
 
 The content type of the POST is always 'Content-Type: application/x-www-form-urlencoded'

 Here is an example:  
 ```
 curl --location 'https://auth.au-sandbox.thewishlist.io/auth/realms/dev-tenant-id/protocol/openid-connect/token' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'grant_type=client_credentials' \
--data-urlencode 'client_id=a_client_id' \
--data-urlencode 'client_secret=Gxxxxxxxx'
```

### Index

***
- [**Authentication API**](#authentication-api)
    - [Index](#index)
  - [**Representations**](#representations)
  - [**REST Endpoints**](#rest-endpoints)
  - [Generate Token](#generate-token)
    
  - [**Representations**](#representations)
  - [**REST Endpoints**](#rest-endpoints)
	- [Generate Token](#generate-token)

## **Representations**




| Key           | Value              | Description                                    				  |
|---------------|--------------------|----------------------------------------------------------------|
| grant_type    | client_credentials | constant: client_credentials                                   |
| client_id     | {Client Id}        | Replace {Client Id} with original value                        |
| client_secret | {client_secret}    | Replace {client_secret} with original value                    |

## **REST Endpoints**


## Generate Token

This API generates the bearer token.

Method: ``` POST ``` 

Endpoint: ```​​auth/realms/{tenentid}/protocol/openid-connect/token```

OAuth 2.0 Scopes: `Tenant authentication`

Request Headers :

| Key           | Value            						|
|---------------|---------------------------------------|
| Content-Type  | `application/x-www-form-urlencoded` 	|
| Accept		| `*/*`			   						| 

Request Parameter: `tenentid  - Tenent Id`

Sample Request Form url encoded objects :

| Key           | Value              |
|---------------|--------------------|
| grant_type    | client_credentials |
| client_id     | {Client Id}        |
| client_secret | {client_secret}    |

Response - 200 (OK):

```json
{
  "access_token": "string",
  "expires_in": 0,
  "refresh_expires_in": 0,
  "token_type": "Bearer",
  "not-before-policy": 0,
  "scope": "email profile"
}
```

HTTP Status Code: 
``` 
- 200 OK
- 400 Bad Request
- 403 Forbidden 
- 404 Not Found
```
  
***
[Back to Top](#authentication-api)  

[Back to Home](index.md#welcome-to-the-wishlist)


 
