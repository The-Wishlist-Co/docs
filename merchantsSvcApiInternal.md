
[Back to Home](index.md#welcome-to-the-wishlist)


# **Merchants API**
The Merchants API is used to store information about a merchant (retailer), their stores and their staff.  This functionality is useful for defining inventory locations and for when The Wishlist Platform is extended into the stores, as retailers can attribute actions to particular stores and staff and analyse performance of stores and staff.

### Index

***

- [**Merchants API**](#merchants-api)
    - [Index](#index)
  - [**Representations**](#representations)
  - [**REST Endpoints**](#rest-endpoints)
  - [**Plan Resource**](#plan-resource)
  - [Create a Plan](#create-a-plan)
  - [Update a Plan](#update-a-plan)
  - [Delete a Plan](#delete-a-plan)
  - [Get Plan](#get-plan)
  - [Find All Plans](#find-all-plans)
  - [**Store Resource**](#store-resource)
  - [Create Subscription plan](#create-subscription-plan)
  - [Update Subscription plan](#update-subscription-plan)
  - [Cancel Subscription plan](#cancel-subscription-plan)

## **Representations**

All requests or responses are JSON objects.


<!-- <details> -->
 <summary><font size="4">Merchant </font></summary>
 
```activated_date``` - Datetime

```active``` - boolean - to indicate the merchant is active or not

```admin_email``` - string - admin email details

```company_code``` - string

```billing_address``` - string

```contact_address``` - string

```contact_person``` - string

```created_at``` - Datetime

```deleted``` - boolean

```deleted_date``` - Datetime

```id``` - string

```merchant_name``` - string

```modified_by``` - string

```trading_as``` - string

```updated_at``` - Datetime

<!-- </details> -->

<!-- <details> -->

 <summary><font size="4">Plan </font></summary>

```plan_name``` - string

```id``` - string

<!-- <details> -->
 <summary><font size="4">plan_type </font></summary>

  ```name``` - string

  ```id``` - string

  ```request_limit``` -number -admin email details

 <!-- </details> -->
 <!-- <details> -->
 <summary><font size="4">subscription_price </font></summary>

  ```amount``` -number

  ```currency_code``` - string  

 <!-- </details> -->
<!-- </details> -->

<!-- <details> -->
 <summary><font size="4">Store </font></summary>

```deactivated_at``` - Datetime

```deactivated``` - boolean - to indicate the merchant is active or not

```default_country``` - string 

```media_url``` - string

```merchant_id``` - string

```plan_id``` - string

```store_key``` - string

```created_at``` - Datetime

```deleted``` - boolean

```deleted_date``` - Datetime

```id``` - string

```store_name``` - string

```modified_by``` - string

```store_state``` - string

```store_url``` - string

```targeted_countries``` - string

```updated_at``` - Datetime

`backInStockThreshold` - Minimum stock level valve where a product or variant is considered to be back in stock at store level.

`lowStockThreshold` - Minimum stock level valve where a product or variant is considered to be in low stock at store level.

<!-- </details> -->


## **REST Endpoints**

## **Plan Resource**

## Create a Plan

Create a subscription plan for The Wishlist platform

Endpoint: ```​/api​/v1​/plan​/```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Sample Request:
<!-- <details> -->
```json
{
  "id": "string",
  "plan_name": "string",
  "plan_type": {
    "id": "string",
    "name": "string",
    "request_limit": 0
  },
  "subscription_price": {
    "amount": 0,
    "currency_code": "string"
  }
}
```

<!-- </details> -->

<summary>Response - 201 (created)</summary> 

```json
{
  "id": "string",
  "plan_name": "string",
  "plan_type": {
    "id": "string",
    "name": "string",
    "request_limit": 0
  },
  "subscription_price": {
    "amount": 0,
    "currency_code": "string"
  }
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


## Update a Plan

Update the subscription plan for The Wishlist platform

Endpoint: ```​/api​/v1​/plan​/```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Sample Request:
<!-- <details> -->

```json
{
  "id": "string",
  "plan_name": "string",
  "plan_type": {
    "id": "string",
    "name": "string",
    "request_limit": 0
  },
  "subscription_price": {
    "amount": 0,
    "currency_code": "string"
  }
}
```

<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary>

```json
{
  "id": "string",
  "plan_name": "string",
  "plan_type": {
    "id": "string",
    "name": "string",
    "request_limit": 0
  },
  "subscription_price": {
    "amount": 0,
    "currency_code": "string"
  }
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


## Delete a Plan

Delete a subscription plan 

Endpoint: ```/api/v1/plan/{planId}/```

Method: ``` DELETE ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `planId  : unique Plan Id`

<summary>Response - 204 (Deleted)</summary>  

```json
{
  "id": "string",
  "plan_name": "string",
  "plan_type": {
    "id": "string",
    "name": "string",
    "request_limit": 0
  },
  "subscription_price": {
    "amount": 0,
    "currency_code": "string"
  }
}
```
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



## Get Plan

Find a subscription plan in The Wishlist platform

Endpoint: ```/api/v1/plan/{planId}/```

Method: ``` GET ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `planId  : Unique plan Id`

<summary>Response - 200 (OK)</summary> 

```json

{
  "id": "string",
  "plan_name": "string",
  "plan_type": {
    "id": "string",
    "name": "string",
    "request_limit": 0
  },
  "subscription_price": {
    "amount": 0,
    "currency_code": "string"
  }
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


## Find All Plans

Returns an array of all subscription plans in the TWC platform.

Endpoint: ```/api/v1/plans/```

Method: ``` GET ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<summary>Response - 200 (OK)</summary> 

```json
[
  {
    "id": "string",
    "plan_name": "string",
    "plan_type": {
      "id": "string",
      "name": "string",
      "request_limit": 0
    },
    "subscription_price": {
      "amount": 0,
      "currency_code": "string"
    }
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


## **Store Resource**

## Create Subscription plan

Create a subscription plan for a given merchant.

Endpoint: ```/api/v1/merchant/{merchantId}/store/{storeId}/plan/{planId}/```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `merchantId  : Unique Merchant Id,storeId: Unique store id,planId: Unique plan id `

<summary>Response - 201 (created)</summary>

```json
{
  "created_at": "2022-06-27T09:32:18.709Z",
  "deactivated": true,
  "deactivated_at": "2022-06-27T09:32:18.709Z",
  "default_country": {
    "code": "string",
    "is_default_country": true,
    "language_isocode": "string",
    "name": "string"
  },
  "deleted": true,
  "deleted_date": "2022-06-27T09:32:18.709Z",
  "id": "string",
  "media_url": "string",
  "merchant_id": "string",
  "modified_by": "string",
  "plan_id": "string",
  "store_key": "string",
  "store_name": "string",
  "backInStockThreshold":0,
  "lowStockThreshold": 0,
  "store_state": "CREATED",
  "store_url": "string",
  "targeted_countries": [
    {
      "code": "string",
      "is_default_country": true,
      "language_isocode": "string",
      "name": "string"
    }
  ],
  "updated_at": "2022-06-27T09:32:18.709Z"
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


## Update Subscription plan

Update a subscription plan for a given merchant in the TWC platform.

Endpoint: ```/api/v1/merchant/{merchantId}/store/{storeId}/plan/{planId}```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `merchantId  : Unique Merchant Id,storeId: Unique store id,planId: Unique plan id `

<summary>Response - 200 (OK Updated)</summary>

```json
{
  "created_at": "2022-06-27T09:33:59.429Z",
  "deactivated": true,
  "deactivated_at": "2022-06-27T09:33:59.429Z",
  "default_country": {
    "code": "string",
    "is_default_country": true,
    "language_isocode": "string",
    "name": "string"
  },
  "deleted": true,
  "deleted_date": "2022-06-27T09:33:59.429Z",
  "id": "string",
  "media_url": "string",
  "merchant_id": "string",
  "modified_by": "string",
  "plan_id": "string",
  "store_key": "string",
  "store_name": "string",
  "backInStockThreshold":0,
  "lowStockThreshold": 0,
  "store_state": "CREATED",
  "store_url": "string",
  "targeted_countries": [
    {
      "code": "string",
      "is_default_country": true,
      "language_isocode": "string",
      "name": "string"
    }
  ],
  "updated_at": "2022-06-27T09:33:59.429Z"
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


## Cancel Subscription plan

Cancel a subscription plan for a given merchant.

Endpoint: ```/api/v1/merchant/{merchantId}/store/{storeId}```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `merchantId  : Unique Merchant Id,storeId: Unique store id `

<summary>Response - 201 (deleted)</summary> 

```json
{
  "created_at": "2022-06-27T09:34:38.716Z",
  "deactivated": true,
  "deactivated_at": "2022-06-27T09:34:38.716Z",
  "default_country": {
    "code": "string",
    "is_default_country": true,
    "language_isocode": "string",
    "name": "string"
  },
  "deleted": true,
  "deleted_date": "2022-06-27T09:34:38.716Z",
  "id": "string",
  "media_url": "string",
  "merchant_id": "string",
  "modified_by": "string",
  "plan_id": "string",
  "store_key": "string",
  "store_name": "string",
  "backInStockThreshold":0,
  "lowStockThreshold": 0,
  "store_state": "CREATED",
  "store_url": "string",
  "targeted_countries": [
    {
      "code": "string",
      "is_default_country": true,
      "language_isocode": "string",
      "name": "string"
    }
  ],
  "updated_at": "2022-06-27T09:34:38.716Z"
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

***
[Back to Top](#merchants-api)

[Back to Home](index.md#welcome-to-the-wishlist)



