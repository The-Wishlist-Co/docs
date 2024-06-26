
[Back to Home](index.md#welcome-to-the-wishlist)

# **Price API**
The price APIs allow developers to manage information about product and variant prices.  Normally these APIs are not used by retailers, as products and pricing are typically synchronised through other means (e.g. overnight batch).  However, these APIs are provided if required and may be useful if real-time price-drop notifications are required.

### Index

***

- [**Price API**](#price-api)
    <!-- - [Index](#index) -->
  - [**Representations**](#representations)
    - [Create A Price](#create-a-price)
    - [Update A Price](#update-a-price)
	- [Update A Price By ID](#update-a-price-by-id)
	- [Update A Price By Ref](#update-a-price-by-ref)
    - [Delete A Price](#delete-a-price)
    - [Find Price by id and priceRef](#find-price-by-id-and-priceref)
    - [Validate an price](#validate-an-price)
    <!-- - [Find All Prices](#find-all-prices) -->


## **Representations**

All requests or responses are JSON objects.


<!-- <details> -->
 <summary><font size="4">Price </font></summary>

```id``` - string - The TWC unique ID of the price item.  This will auotmatically generate while creating the location.

```priceRef``` - string - The unique reference of the price.

```active``` - boolean - To indicate the price is active or not

```deleted``` - boolean - To indicate the price is deleted or not

```currencyCode``` - string - Currency code as per ISO 4217

```offlineDate``` - Datetime 

```onlineDate``` - Datetime 

```price``` - number - The price of the product variant

```productVariantId``` - string - The unique id of the product variant

```sale``` - boolean 

```salePrice``` - number - Item sale price

<!-- </details> -->


## Create A Price

Method: ``` POST ``` 

Endpoint: ```/api/prices```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Sample Request :
<!-- <details> -->
```json
{
  "active": true,
  "currencyCode": "string",
  "deleted": true,
  "id": "string",
  "offlineDate": "2022-06-20T11:46:30.265Z",
  "onlineDate": "2022-06-20T11:46:30.265Z",
  "price": 0,
  "priceRef": "string",
  "productVariantId": "string",
  "sale": true,
  "salePrice": 0
}
```

<!-- </details> -->

<summary>Response - 201 (created)</summary>

```json
{
  "active": true,
  "currencyCode": "string",
  "deleted": true,
  "id": "string",
  "offlineDate": "2022-06-27T13:18:59.461Z",
  "onlineDate": "2022-06-27T13:18:59.461Z",
  "price": 0,
  "priceRef": "string",
  "productVariantId": "string",
  "sale": true,
  "salePrice": 0
}
```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Update A Price

Method: ``` PUT ``` 

Endpoint: ```/api/prices```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Sample Request :
<!-- <details> -->
```json
{
  "active": true,
  "currencyCode": "string",
  "deleted": true,
  "id": "string",
  "offlineDate": "2022-06-20T11:58:06.885Z",
  "onlineDate": "2022-06-20T11:58:06.885Z",
  "price": 0,
  "priceRef": "string",
  "sale": true,
  "salePrice": 0
}
```
<!-- </details> -->

<summary>Response - 200 (OK)</summary> 

```json
{
  "active": true,
  "currencyCode": "string",
  "deleted": true,
  "id": "string",
  "offlineDate": "2022-06-27T13:18:59.465Z",
  "onlineDate": "2022-06-27T13:18:59.465Z",
  "price": 0,
  "priceRef": "string",
  "productVariantId": "string",
  "sale": true,
  "salePrice": 0
}
```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Update A Variant Price By Variant ID

Method: ``` PUT ``` 

Endpoint: ```/api/prices/id={id}```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable

```
id - price ID
```

Sample Request :
<!-- <details> -->
```json
{
  "active": true,
  "currencyCode": "string",
  "deleted": true,
  "offlineDate": "2022-06-20T11:58:06.885Z",
  "onlineDate": "2022-06-20T11:58:06.885Z",
  "price": 0,
  "sale": true,
  "salePrice": 0
}
```
<!-- </details> -->

<summary>Response - 200 (OK)</summary> 

```json
{
  "active": true,
  "currencyCode": "string",
  "deleted": true,
  "id": "string",
  "offlineDate": "2022-06-27T13:18:59.465Z",
  "onlineDate": "2022-06-27T13:18:59.465Z",
  "price": 0,
  "priceRef": "string",
  "productVariantId": "string",
  "sale": true,
  "salePrice": 0
}
```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Update A Price By Variant Ref

Method: ``` PUT ``` 

Endpoint: ```/api/prices/ref={ref}```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable:

```
ref - Price Ref
```

Sample Request :
<!-- <details> -->
```json
{
  "active": true,
  "currencyCode": "string",
  "deleted": true,  
  "offlineDate": "2022-06-20T11:58:06.885Z",
  "onlineDate": "2022-06-20T11:58:06.885Z",
  "price": 0,  
  "sale": true,
  "salePrice": 0
}
```
<!-- </details> -->

<summary>Response - 200 (OK)</summary> 

```json
{
  "active": true,
  "currencyCode": "string",
  "deleted": true,
  "id": "string",
  "offlineDate": "2022-06-27T13:18:59.465Z",
  "onlineDate": "2022-06-27T13:18:59.465Z",
  "price": 0,
  "priceRef": "string",
  "productVariantId": "string",
  "sale": true,
  "salePrice": 0
}
```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


### Delete A Price

Endpoint: ```/api/prices/{id}```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `id  : Price Id`

<summary>Response - 204 (Deleted)</summary> 

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

### Find Price by id and priceRef

Endpoint: ```/api/prices```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `id  : Price Id, priceRef : Price reference`

<summary>Response - 200 (OK)</summary> 

```json
{
  "active": true,
  "currencyCode": "string",
  "deleted": true,
  "id": "string",
  "offlineDate": "2022-06-27T13:20:21.692Z",
  "onlineDate": "2022-06-27T13:20:21.692Z",
  "price": 0,
  "priceRef": "string",
  "productVariantId": "string",
  "sale": true,
  "salePrice": 0
}
```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Validate an price

Method: ``` POST ``` 

Endpoint: ```​/api/prices/validate```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Sample Request :
<!-- <details> -->
```json
{
  "active": true,
  "currencyCode": "string",
  "deleted": true,
  "id": "string",
  "offlineDate": "2022-06-20T12:03:25.422Z",
  "onlineDate": "2022-06-20T12:03:25.422Z",
  "price": 0,
  "priceRef": "string",
  "productVariantId": "string",
  "sale": true,
  "salePrice": 0
}
```
<!-- </details> -->
<summary>Response - 200 (OK)</summary>

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

### Find All Prices

Endpoint: ```/api/prices/all```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<summary>Response - 200 (OK)</summary> 

```json
[
  {
    "active": true,
    "currencyCode": "string",
    "deleted": true,
    "id": "string",
    "offlineDate": "2022-06-27T13:21:10.650Z",
    "onlineDate": "2022-06-27T13:21:10.650Z",
    "price": 0,
    "priceRef": "string",
    "productVariantId": "string",
    "sale": true,
    "salePrice": 0
  }
]
```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


***
[Back to Top](#order-svc-api)

[Back to Home](index.md#welcome-to-the-wishlist)


