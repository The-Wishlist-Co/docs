
# **Price API**
The Price resource stores information about a particular product variant price details.


## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.


<details>
 <summary><font size="4">Price </font></summary>

```id``` - string -The unique ID of the price.It will auotmatically generate while creating the location.

```priceRef``` - string -The unique reference of the price.

```active``` - boolean -to indicate the price is active or not

```deleted``` - boolean -to indicate the price is deleted or not

```currencyCode``` - string -currency code as per ISO 4217

```offlineDate``` - Datetime 

```onlineDate``` - Datetime 

```price``` - number -The price of the product variant

```productVariantId``` - string -The unique id of the product variant

```sale``` - boolean 

```salePrice``` - number -item sale price

</details>


## Create A Price

Method: ``` POST ``` 

Endpoint: ```/api/prices```

OAuth 2.0 Scopes: `Tenant authentication`

Sample Request :
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


## Update A Price

Method: ``` PUT ``` 

Endpoint: ```/api/prices```

OAuth 2.0 Scopes: `Tenant authentication`

Sample Request :
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Delete A Price

Endpoint: ```/api/prices/{id}```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication`

Request Parameters: `id  : Price Id`

Response : `200 OK ,204	No Content, 401 Unauthorized, 403 Forbidden`



### Find Price by id and priceRef

Endpoint: ```/api/prices```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication`

Request Parameters: `id  : Price Id, priceRef : Price reference`

Response : `200 OK , 401 Unauthorized, 403 Forbidden, 404 Not Found`


## Validate an price

Method: ``` POST ``` 

Endpoint: ```​/api/prices/validate```

OAuth 2.0 Scopes: `Tenant authentication`

Sample Request :
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Find All Prices

Endpoint: ```/api/prices/all```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication`

Response : `200 OK , 401 Unauthorized, 403 Forbidden, 404 Not Found`

***[Back to Index](index.md)
