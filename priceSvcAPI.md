
# **Price API**
The Price resource stores information about price details of  particular product variant.

### Index

***

- [**Price API**](#price-api)
    <!-- - [Index](#index) -->
  - [**Representations**](#representations)
    - [Create A Price](#create-a-price)
    - [Update A Price](#update-a-price)
    - [Delete A Price](#delete-a-price)
    - [Find Price by id and priceRef](#find-price-by-id-and-priceref)
    - [Validate an price](#validate-an-price)
    - [Find All Prices](#find-all-prices)


## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.


<!-- <details> -->
 <summary><font size="4">Price </font></summary>

```id``` - string - The unique ID of the price.It will auotmatically generate while creating the location.

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

OAuth 2.0 Scopes: `Tenant authentication`

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

Sample Response : 
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
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

## Update A Price

Method: ``` PUT ``` 

Endpoint: ```/api/prices```

OAuth 2.0 Scopes: `Tenant authentication`

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

Sample Response : 
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
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

### Delete A Price

Endpoint: ```/api/prices/{id}```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication`

 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `id  : Price Id`



HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 401 Unauthorized
- 403 Forbidden 

```

### Find Price by id and priceRef

Endpoint: ```/api/prices```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication`

 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `id  : Price Id, priceRef : Price reference`

Sample Response : 

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
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

## Validate an price

Method: ``` POST ``` 

Endpoint: ```​/api/prices/validate```

OAuth 2.0 Scopes: `Tenant authentication`

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


HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

### Find All Prices

Endpoint: ```/api/prices/all```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication`

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Sample Response : 

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
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

***[Back to Index](index.md)
