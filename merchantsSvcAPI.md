
[Back to Home](index.md#welcome-to-the-wishlist)


# **Merchants API**
The Merchants resource stores information about a merchant and their stores.

### Index

***

- [**Merchants API**](#merchants-api)
    <!-- - [Index](#index) -->
  - [**Representations**](#representations)
  - [**REST Endpoints**](#rest-endpoints)
    - [**Merchant Resource**](#merchant-resource)
      - [Register Merchant](#register-merchant)
      - [Update Merchant](#update-merchant)
      - [Deactivate Merchant](#deactivate-merchant)
      - [Find Merchant](#find-merchant)
    - [**Plan Resource**](#plan-resource)
      - [Create a Plan](#create-a-plan)
      - [Update a Plan](#update-a-plan)
      - [Delete a Plan](#delete-a-plan)
      - [Find Plan](#find-plan)
      - [Find All Plans](#find-all-plans)
    - [**Store Resource**](#store-resource)
      - [Create a Store](#create-a-store)
      - [Update a Store](#update-a-store)
      - [Find a Store](#find-a-store)
      - [Find a Store](#find-a-store-1)
      - [Deactivate Store](#deactivate-store)
      - [Create Subscription plan](#create-subscription-plan)
      - [Update Subscription plan](#update-subscription-plan)
      - [Cancel Subscription plan](#cancel-subscription-plan)
    - [**Store Config Resource**](#store-config-resource)
      - [Get Additional Config](#get-additional-config)
      - [Get All Config](#get-all-config)
      - [Get Entity Config](#get-entity-config)
      - [Get Store Tenant Config](#get-store-tenant-config)
      - [Create Additional Config](#create-additional-config)
      - [Update Additional Config](#update-additional-config)
      - [Create App Config Entity Config](#create-app-config-entity-config)
      - [Update App Config Entity Config](#update-app-config-entity-config)
      - [Create Customer Entity Config](#create-customer-entity-config)
      - [Update Customer Entity Config](#update-customer-entity-config)
      - [Create Email Template Entity Config](#create-email-template-entity-config)
      - [Update Email Template Entity Config](#update-email-template-entity-config)
      - [Create Inventory Entity Config](#create-inventory-entity-config)
      - [Update Inventory Entity Config](#update-inventory-entity-config)
      - [Create Location Entity Config](#create-location-entity-config)
      - [Update Location Entity Config](#update-location-entity-config)
      - [Create Order Entity Config](#create-order-entity-config)
      - [Update Order Entity Config](#update-order-entity-config)
      - [Create Price Entity Config](#create-price-entity-config)
      - [Update Price Entity Config](#update-price-entity-config)
      - [Create Product Entity Config](#create-product-entity-config)
      - [Update Product Entity Config](#update-product-entity-config)
      - [Create Store Entity Config](#create-store-entity-config)
      - [Update Store Entity Config](#update-store-entity-config)
      - [Create Wishlist Entity Config](#create-wishlist-entity-config)
      - [Update Wishlist Entity Config](#update-wishlist-entity-config)
      - [Get Notification Config](#get-notification-config)
      - [Create Notification Config](#create-notification-config)
      - [Create BackInStock Notification Settings](#create-backinstock-notification-settings)
      - [Update BackInStock Notification Settings](#update-backinstock-notification-settings)
      - [Delete BackInStock Notification Settings](#delete-backinstock-notification-settings)
      - [Create LowInStock Notification Settings](#create-lowinstock-notification-settings)
      - [Update LowInStock Notification Settings](#update-lowinstock-notification-settings)
      - [Delete LowInStock Notification Settings](#delete-lowinstock-notification-settings)
      - [Create PriceDrop Notification Settings](#create-pricedrop-notification-settings)
      - [Update PriceDrop Notification Settings](#update-pricedrop-notification-settings)
      - [Delete PriceDrop Notification Settings](#delete-pricedrop-notification-settings)
      - [Create ReminderEmail Notification Settings](#create-reminderemail-notification-settings)
      - [Update ReminderEmail Notification Settings](#update-reminderemail-notification-settings)
      - [Delete ReminderEmail Notification Settings](#delete-reminderemail-notification-settings)

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

<!-- </details> -->


## **REST Endpoints**

## **Merchant Resource**

## Register Merchant

Method: ``` POST ``` 

Endpoint: ```​/api​/v1​/merchant```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Sample Request :
<!-- <details> -->

```json
{
  "activated_date": "2022-06-20T15:40:14.465Z",
  "active": true,
  "admin_email": "string",
  "attributes": [
    {
      "attribute_group": "string",
      "attributes": [
        {
          "attribute_name": "string",
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      ],
      "is_obsolete": true
    }
  ],
  "billing_address": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "country_code": "string",
    "email": "string",
    "is_address": true,
    "is_default_address": true,
    "phone": "string",
    "postal_code": "string",
    "state_or_province_code": "string",
    "state_or_province_name": "string",
    "street": "string",
    "street_number": "string",
    "unit": "string"
  },
  "company_code": "string",
  "contact_address": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "country_code": "string",
    "email": "string",
    "is_address": true,
    "is_default_address": true,
    "phone": "string",
    "postal_code": "string",
    "state_or_province_code": "string",
    "state_or_province_name": "string",
    "street": "string",
    "street_number": "string",
    "unit": "string"
  },
  "contact_person": {
    "additional_notes": "string",
    "email": "string",
    "firstName": "string",
    "lastName": "string",
    "phone": "string"
  },
  "created_at": "2022-06-20T15:40:14.465Z",
  "deleted": true,
  "deleted_date": "2022-06-20T15:40:14.465Z",
  "id": "string",
  "merchant_name": "string",
  "modified_by": "string",
  "trading_as": "string",
  "updated_at": "2022-06-20T15:40:14.465Z"
}

```
<!-- </details> -->

<summary>Response - 201 (Created)</summary>

```json
{
  "activated_date": "2022-06-27T09:02:43.112Z",
  "active": true,
  "admin_email": "string",
  "attributes": [
    {
      "attribute_group": "string",
      "attributes": [
        {
          "attribute_name": "string",
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      ],
      "is_obsolete": true
    }
  ],
  "billing_address": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "country_code": "string",
    "email": "string",
    "is_address": true,
    "is_default_address": true,
    "phone": "string",
    "postal_code": "string",
    "state_or_province_code": "string",
    "state_or_province_name": "string",
    "street": "string",
    "street_number": "string",
    "unit": "string"
  },
  "company_code": "string",
  "contact_address": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "country_code": "string",
    "email": "string",
    "is_address": true,
    "is_default_address": true,
    "phone": "string",
    "postal_code": "string",
    "state_or_province_code": "string",
    "state_or_province_name": "string",
    "street": "string",
    "street_number": "string",
    "unit": "string"
  },
  "contact_person": {
    "additional_notes": "string",
    "email": "string",
    "firstName": "string",
    "lastName": "string",
    "phone": "string"
  },
  "created_at": "2022-06-27T09:02:43.112Z",
  "deleted": true,
  "deleted_date": "2022-06-27T09:02:43.112Z",
  "id": "string",
  "merchant_name": "string",
  "modified_by": "string",
  "trading_as": "string",
  "updated_at": "2022-06-27T09:02:43.112Z"
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



## Update Merchant

Method: ``` PUT ``` 

Endpoint: ```​/api​/v1​/merchant```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Sample Request :
<!-- <details> -->

```json
{
  "activated_date": "2022-06-20T16:04:31.656Z",
  "active": true,
  "admin_email": "string",
  "attributes": [
    {
      "attribute_group": "string",
      "attributes": [
        {
          "attribute_name": "string",
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      ],
      "is_obsolete": true
    }
  ],
  "billing_address": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "country_code": "string",
    "email": "string",
    "is_address": true,
    "is_default_address": true,
    "phone": "string",
    "postal_code": "string",
    "state_or_province_code": "string",
    "state_or_province_name": "string",
    "street": "string",
    "street_number": "string",
    "unit": "string"
  },
  "company_code": "string",
  "contact_address": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "country_code": "string",
    "email": "string",
    "is_address": true,
    "is_default_address": true,
    "phone": "string",
    "postal_code": "string",
    "state_or_province_code": "string",
    "state_or_province_name": "string",
    "street": "string",
    "street_number": "string",
    "unit": "string"
  },
  "contact_person": {
    "additional_notes": "string",
    "email": "string",
    "firstName": "string",
    "lastName": "string",
    "phone": "string"
  },
  "created_at": "2022-06-20T16:04:31.656Z",
  "deleted": true,
  "deleted_date": "2022-06-20T16:04:31.656Z",
  "id": "string",
  "merchant_name": "string",
  "modified_by": "string",
  "trading_as": "string",
  "updated_at": "2022-06-20T16:04:31.656Z"
}
```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary> 

```json
{
  "activated_date": "2022-06-27T09:15:10.775Z",
  "active": true,
  "admin_email": "string",
  "attributes": [
    {
      "attribute_group": "string",
      "attributes": [
        {
          "attribute_name": "string",
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      ],
      "is_obsolete": true
    }
  ],
  "billing_address": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "country_code": "string",
    "email": "string",
    "is_address": true,
    "is_default_address": true,
    "phone": "string",
    "postal_code": "string",
    "state_or_province_code": "string",
    "state_or_province_name": "string",
    "street": "string",
    "street_number": "string",
    "unit": "string"
  },
  "company_code": "string",
  "contact_address": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "country_code": "string",
    "email": "string",
    "is_address": true,
    "is_default_address": true,
    "phone": "string",
    "postal_code": "string",
    "state_or_province_code": "string",
    "state_or_province_name": "string",
    "street": "string",
    "street_number": "string",
    "unit": "string"
  },
  "contact_person": {
    "additional_notes": "string",
    "email": "string",
    "firstName": "string",
    "lastName": "string",
    "phone": "string"
  },
  "created_at": "2022-06-27T09:15:10.775Z",
  "deleted": true,
  "deleted_date": "2022-06-27T09:15:10.775Z",
  "id": "string",
  "merchant_name": "string",
  "modified_by": "string",
  "trading_as": "string",
  "updated_at": "2022-06-27T09:15:10.775Z"
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



## Deactivate Merchant

Endpoint: ```/api/v1/merchant/{id}/deactivate```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `id  : Merchant Id`

<summary>Response - 200 (OK Updated)</summary>

```json
{
  "activated_date": "2022-06-27T09:16:52.246Z",
  "active": true,
  "admin_email": "string",
  "attributes": [
    {
      "attribute_group": "string",
      "attributes": [
        {
          "attribute_name": "string",
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      ],
      "is_obsolete": true
    }
  ],
  "billing_address": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "country_code": "string",
    "email": "string",
    "is_address": true,
    "is_default_address": true,
    "phone": "string",
    "postal_code": "string",
    "state_or_province_code": "string",
    "state_or_province_name": "string",
    "street": "string",
    "street_number": "string",
    "unit": "string"
  },
  "company_code": "string",
  "contact_address": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "country_code": "string",
    "email": "string",
    "is_address": true,
    "is_default_address": true,
    "phone": "string",
    "postal_code": "string",
    "state_or_province_code": "string",
    "state_or_province_name": "string",
    "street": "string",
    "street_number": "string",
    "unit": "string"
  },
  "contact_person": {
    "additional_notes": "string",
    "email": "string",
    "firstName": "string",
    "lastName": "string",
    "phone": "string"
  },
  "created_at": "2022-06-27T09:16:52.246Z",
  "deleted": true,
  "deleted_date": "2022-06-27T09:16:52.246Z",
  "id": "string",
  "merchant_name": "string",
  "modified_by": "string",
  "trading_as": "string",
  "updated_at": "2022-06-27T09:16:52.246Z"
}
```
<summary>Response - 200 (OK Updated)</summary>


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



## Find Merchant

Endpoint: ```/api/v1/merchant/{id}```

Method: ``` GET ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request Parameters: `id  : Mechant Id`

<summary>Response - 200 (OK)</summary> 

```json
{
  "activated_date": "2022-06-27T09:18:12.280Z",
  "active": true,
  "admin_email": "string",
  "attributes": [
    {
      "attribute_group": "string",
      "attributes": [
        {
          "attribute_name": "string",
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      ],
      "is_obsolete": true
    }
  ],
  "billing_address": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "country_code": "string",
    "email": "string",
    "is_address": true,
    "is_default_address": true,
    "phone": "string",
    "postal_code": "string",
    "state_or_province_code": "string",
    "state_or_province_name": "string",
    "street": "string",
    "street_number": "string",
    "unit": "string"
  },
  "company_code": "string",
  "contact_address": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "country_code": "string",
    "email": "string",
    "is_address": true,
    "is_default_address": true,
    "phone": "string",
    "postal_code": "string",
    "state_or_province_code": "string",
    "state_or_province_name": "string",
    "street": "string",
    "street_number": "string",
    "unit": "string"
  },
  "contact_person": {
    "additional_notes": "string",
    "email": "string",
    "firstName": "string",
    "lastName": "string",
    "phone": "string"
  },
  "created_at": "2022-06-27T09:18:12.280Z",
  "deleted": true,
  "deleted_date": "2022-06-27T09:18:12.280Z",
  "id": "string",
  "merchant_name": "string",
  "modified_by": "string",
  "trading_as": "string",
  "updated_at": "2022-06-27T09:18:12.280Z"
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


## **Plan Resource**


## Create a Plan

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



## Find Plan

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
## Create a Store

Endpoint: ```​/api/v1/store```

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
  "created_at": "2022-06-20T15:55:58.309Z",
  "deactivated": true,
  "deactivated_at": "2022-06-20T15:55:58.309Z",
  "default_country": {
    "code": "string",
    "is_default_country": true,
    "language_isocode": "string",
    "name": "string"
  },
  "deleted": true,
  "deleted_date": "2022-06-20T15:55:58.309Z",
  "id": "string",
  "media_url": "string",
  "merchant_id": "string",
  "modified_by": "string",
  "plan_id": "string",
  "store_key": "string",
  "store_name": "string",
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
  "updated_at": "2022-06-20T15:55:58.309Z"
}
```

<!-- </details> -->

<summary>Response - 201 (created)</summary> 

```json
{
  "created_at": "2022-06-27T09:27:20.501Z",
  "deactivated": true,
  "deactivated_at": "2022-06-27T09:27:20.501Z",
  "default_country": {
    "code": "string",
    "is_default_country": true,
    "language_isocode": "string",
    "name": "string"
  },
  "deleted": true,
  "deleted_date": "2022-06-27T09:27:20.501Z",
  "id": "string",
  "media_url": "string",
  "merchant_id": "string",
  "modified_by": "string",
  "plan_id": "string",
  "store_key": "string",
  "store_name": "string",
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
  "updated_at": "2022-06-27T09:27:20.501Z"
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


## Update a Store

Endpoint: ```/api/v1/store/{id}```

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
  "created_at": "2022-06-20T16:26:50.951Z",
  "deactivated": true,
  "deactivated_at": "2022-06-20T16:26:50.951Z",
  "default_country": {
    "code": "string",
    "is_default_country": true,
    "language_isocode": "string",
    "name": "string"
  },
  "deleted": true,
  "deleted_date": "2022-06-20T16:26:50.951Z",
  "id": "string",
  "media_url": "string",
  "merchant_id": "string",
  "modified_by": "string",
  "plan_id": "string",
  "store_key": "string",
  "store_name": "string",
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
  "updated_at": "2022-06-20T16:26:50.951Z"
}

```

<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary>

```json
{
  "created_at": "2022-06-27T09:29:01.615Z",
  "deactivated": true,
  "deactivated_at": "2022-06-27T09:29:01.615Z",
  "default_country": {
    "code": "string",
    "is_default_country": true,
    "language_isocode": "string",
    "name": "string"
  },
  "deleted": true,
  "deleted_date": "2022-06-27T09:29:01.615Z",
  "id": "string",
  "media_url": "string",
  "merchant_id": "string",
  "modified_by": "string",
  "plan_id": "string",
  "store_key": "string",
  "store_name": "string",
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
  "updated_at": "2022-06-27T09:29:01.615Z"
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




## Find a Store

Endpoint: ```/api/v1/store```

Method: ``` GET ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,storeKey: store key`

<summary>Response - 200 (OK)</summary>

```json
{
  "created_at": "2022-06-27T09:29:40.889Z",
  "deactivated": true,
  "deactivated_at": "2022-06-27T09:29:40.889Z",
  "default_country": {
    "code": "string",
    "is_default_country": true,
    "language_isocode": "string",
    "name": "string"
  },
  "deleted": true,
  "deleted_date": "2022-06-27T09:29:40.889Z",
  "id": "string",
  "media_url": "string",
  "merchant_id": "string",
  "modified_by": "string",
  "plan_id": "string",
  "store_key": "string",
  "store_name": "string",
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
  "updated_at": "2022-06-27T09:29:40.889Z"
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



## Find a Store

Endpoint: ```/api/v1/store/{storeId}```

Method: ``` GET ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id`

<summary>Response - 200 (OK)</summary> 

```json
{
  "created_at": "2022-06-27T09:30:48.827Z",
  "deactivated": true,
  "deactivated_at": "2022-06-27T09:30:48.827Z",
  "default_country": {
    "code": "string",
    "is_default_country": true,
    "language_isocode": "string",
    "name": "string"
  },
  "deleted": true,
  "deleted_date": "2022-06-27T09:30:48.827Z",
  "id": "string",
  "media_url": "string",
  "merchant_id": "string",
  "modified_by": "string",
  "plan_id": "string",
  "store_key": "string",
  "store_name": "string",
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
  "updated_at": "2022-06-27T09:30:48.827Z"
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


## Deactivate Store

Endpoint: ```/api/v1/stores/{storeId}/deactivate```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique Store Id`

<summary>Response - 200 (OK Updated)</summary>

```json
{
  "created_at": "2022-06-27T09:31:20.371Z",
  "deactivated": true,
  "deactivated_at": "2022-06-27T09:31:20.371Z",
  "default_country": {
    "code": "string",
    "is_default_country": true,
    "language_isocode": "string",
    "name": "string"
  },
  "deleted": true,
  "deleted_date": "2022-06-27T09:31:20.371Z",
  "id": "string",
  "media_url": "string",
  "merchant_id": "string",
  "modified_by": "string",
  "plan_id": "string",
  "store_key": "string",
  "store_name": "string",
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
  "updated_at": "2022-06-27T09:31:20.371Z"
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


## Create Subscription plan

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

## **Store Config Resource**

## Get Additional Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/additionalConfigs```

Method: ``` GET ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

<summary>Response - 200 (OK)</summary> 

```json
{
  "attributes": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "wishlistConfigs": {
    "allowMultipleWishlist": true,
    "allowWishlistSharing": true
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


## Get All Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/allConfig```

Method: ``` GET ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

<summary>Response - 200 (OK)</summary>

```json
{
  "additionalConfigs": {
    "attributes": {
      "additionalProp1": "string",
      "additionalProp2": "string",
      "additionalProp3": "string"
    },
    "wishlistConfigs": {
      "allowMultipleWishlist": true,
      "allowWishlistSharing": true
    }
  },
  "entityConfigurations": {
    "additionalProp1": {
      "active": true,
      "entityName": "string",
      "topics": {
        "additionalProp1": {
          "limit": 0,
          "topic": "string",
          "type": 0,
          "value": "string"
        },
        "additionalProp2": {
          "limit": 0,
          "topic": "string",
          "type": 0,
          "value": "string"
        },
        "additionalProp3": {
          "limit": 0,
          "topic": "string",
          "type": 0,
          "value": "string"
        }
      }
    },
    "additionalProp2": {
      "active": true,
      "entityName": "string",
      "topics": {
        "additionalProp1": {
          "limit": 0,
          "topic": "string",
          "type": 0,
          "value": "string"
        },
        "additionalProp2": {
          "limit": 0,
          "topic": "string",
          "type": 0,
          "value": "string"
        },
        "additionalProp3": {
          "limit": 0,
          "topic": "string",
          "type": 0,
          "value": "string"
        }
      }
    },
    "additionalProp3": {
      "active": true,
      "entityName": "string",
      "topics": {
        "additionalProp1": {
          "limit": 0,
          "topic": "string",
          "type": 0,
          "value": "string"
        },
        "additionalProp2": {
          "limit": 0,
          "topic": "string",
          "type": 0,
          "value": "string"
        },
        "additionalProp3": {
          "limit": 0,
          "topic": "string",
          "type": 0,
          "value": "string"
        }
      }
    }
  },
  "id": "string",
  "notificationConfig": {
    "backInStock": {
      "deActivated": true,
      "emailTemplate": "string",
      "frequency": "string",
      "realtime": "string"
    },
    "lowInStock": {
      "deActivated": true,
      "emailTemplate": "string",
      "frequency": "string",
      "realtime": "string"
    },
    "priceDrop": {
      "deActivated": true,
      "emailTemplate": "string",
      "frequency": "string",
      "realtime": "string"
    },
    "reminderEmail": {
      "deActivated": true,
      "emailTemplate": "string",
      "frequency": "string",
      "realtime": "string"
    }
  },
  "storeId": "string"
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


## Get Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityConfig```

Method: ``` GET ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

<summary>Response - 200 (OK)</summary>

```json
{
  "additionalProp1": {
    "active": true,
    "entityName": "string",
    "topics": {
      "additionalProp1": {
        "limit": 0,
        "topic": "string",
        "type": 0,
        "value": "string"
      },
      "additionalProp2": {
        "limit": 0,
        "topic": "string",
        "type": 0,
        "value": "string"
      },
      "additionalProp3": {
        "limit": 0,
        "topic": "string",
        "type": 0,
        "value": "string"
      }
    }
  },
  "additionalProp2": {
    "active": true,
    "entityName": "string",
    "topics": {
      "additionalProp1": {
        "limit": 0,
        "topic": "string",
        "type": 0,
        "value": "string"
      },
      "additionalProp2": {
        "limit": 0,
        "topic": "string",
        "type": 0,
        "value": "string"
      },
      "additionalProp3": {
        "limit": 0,
        "topic": "string",
        "type": 0,
        "value": "string"
      }
    }
  },
  "additionalProp3": {
    "active": true,
    "entityName": "string",
    "topics": {
      "additionalProp1": {
        "limit": 0,
        "topic": "string",
        "type": 0,
        "value": "string"
      },
      "additionalProp2": {
        "limit": 0,
        "topic": "string",
        "type": 0,
        "value": "string"
      },
      "additionalProp3": {
        "limit": 0,
        "topic": "string",
        "type": 0,
        "value": "string"
      }
    }
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


## Get Store Tenant Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/tenantConfig```

Method: ``` GET ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

<summary>Response - 200 (OK)</summary>

```json
{
  "bucketName": "string",
  "defaultClientGuid": "string",
  "defaultClientId": "string",
  "defaultClientSecret": "string",
  "realmId": "string",
  "realmName": "string",
  "storeId": "string",
  "tenantId": "string"
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



## Create Additional Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/additionalConfigs```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->

```json
{
  "attributes": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "wishlistConfigs": {
    "allowMultipleWishlist": true,
    "allowWishlistSharing": true
  }
}
```

<!-- </details> -->

<summary>Response - 201 (created)</summary> 

```json
{
  "attributes": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "wishlistConfigs": {
    "allowMultipleWishlist": true,
    "allowWishlistSharing": true
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



## Update Additional Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/additionalConfigs```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->
```json
{
  "attributes": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "wishlistConfigs": {
    "allowMultipleWishlist": true,
    "allowWishlistSharing": true
  }
}
```

<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary>

```json
{
  "attributes": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "wishlistConfigs": {
    "allowMultipleWishlist": true,
    "allowWishlistSharing": true
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



## Create App Config Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/appconfig```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}
```
<!-- </details> -->

<summary>Response - 201 (created)</summary>

```json

{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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



## Update App Config Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/appconfig```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:

```json

{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}

```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary>

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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



## Create Customer Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/customer```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->
```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}

```
<!-- </details> -->

<summary>Response - 201 (created)</summary> 

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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


## Update Customer Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/customer```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:

```json

{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}
```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary> 

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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


## Create Email Template Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/emailtemplate```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}
```
<!-- </details> -->

<summary>Response - 201 (created)</summary> 

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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


## Update Email Template Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/emailtemplate```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}
```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary> 

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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


## Create Inventory Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/inventory```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->
```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}
```
<!-- </details> -->

<summary>Response - 201 (created)</summary>

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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



## Update Inventory Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/inventory```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->
```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}
```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary>  

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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



## Create Location Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/location```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->
```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}
```
<!-- </details> -->

<summary>Response - 201 (created)</summary>

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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



## Update Location Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/location```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->
```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}
```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary> 

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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



## Create Order Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/order```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}

```
<!-- </details> -->

<summary>Response - 201 (created)</summary> 

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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



## Update Order Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/order```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->
```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}
```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary> 

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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



## Create Price Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/price```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:

```json

{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}
```
<!-- </details> -->

<summary>Response - 201 (created)</summary>

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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



## Update Price Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/price```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->
```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}
```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary>  

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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



## Create Product Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/product```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}
```
<!-- </details> -->

<summary>Response - 201 (created)</summary>

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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


## Update Product Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/product```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}

```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary> 

```json

{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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


## Create Store Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/store```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}
```
<!-- </details> -->

<summary>Response - 201 (created)</summary>

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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


## Update Store Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/store```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->
```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}
```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary> 

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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


## Create Wishlist Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/wishlist```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}

```

<!-- </details> -->

<summary>Response - 201 (created)</summary>

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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


## Update Wishlist Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/wishlist```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->
```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
  }
}

```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary> 

```json
{
  "active": true,
  "entityName": "string",
  "topics": {
    "additionalProp1": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp2": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    },
    "additionalProp3": {
      "limit": 0,
      "topic": "string",
      "type": 0,
      "value": "string"
    }
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


## Get Notification Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification```

Method: ``` GET ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

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



## Create Notification Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->
```json
{
  "backInStock": {
    "deActivated": true,
    "emailTemplate": "string",
    "frequency": "string",
    "realtime": "string"
  },
  "lowInStock": {
    "deActivated": true,
    "emailTemplate": "string",
    "frequency": "string",
    "realtime": "string"
  },
  "priceDrop": {
    "deActivated": true,
    "emailTemplate": "string",
    "frequency": "string",
    "realtime": "string"
  },
  "reminderEmail": {
    "deActivated": true,
    "emailTemplate": "string",
    "frequency": "string",
    "realtime": "string"
  }
}

```
<!-- </details> -->

<summary>Response - 201 (created)</summary> 

```json

{
  "backInStock": {
    "deActivated": true,
    "emailTemplate": "string",
    "frequency": "string",
    "realtime": "string"
  },
  "lowInStock": {
    "deActivated": true,
    "emailTemplate": "string",
    "frequency": "string",
    "realtime": "string"
  },
  "priceDrop": {
    "deActivated": true,
    "emailTemplate": "string",
    "frequency": "string",
    "realtime": "string"
  },
  "reminderEmail": {
    "deActivated": true,
    "emailTemplate": "string",
    "frequency": "string",
    "realtime": "string"
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



## Create BackInStock Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/backInStock```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->

```json
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}
```
<!-- </details> -->

<summary>Response - 201 (created)</summary> 

```json
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
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



## Update BackInStock Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/backInStock```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->
```json
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}

```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary> 

```json
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
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



## Delete BackInStock Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/backInStock```

Method: ``` DELETE ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

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



## Create LowInStock Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/lowInStock```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->

```json
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}

```
<!-- </details> -->

<summary>Response - 201 (created)</summary>

```json
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
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



## Update LowInStock Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/lowInStock```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->

```json
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}
```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary> 

```json
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
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



## Delete LowInStock Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/lowInStock```

Method: ``` DELETE ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

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


## Create PriceDrop Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/priceDrop```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:

```json

{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}
```
<!-- </details> -->

<summary>Response - 201 (created)</summary> 

```json
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
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



## Update PriceDrop Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/priceDrop```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->
```json
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}
```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary>

```json
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
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


## Delete PriceDrop Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/priceDrop```

Method: ``` DELETE ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

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



## Create ReminderEmail Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/reminderEmail```

Method: ``` POST ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->

```json
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}
```
<!-- </details> -->

<summary>Response - 201 (created)</summary>

```json
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
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


## Update ReminderEmail Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/reminderEmail```

Method: ``` PUT ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<!-- <details> -->

```json
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}
```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary>

```json
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
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


## Delete ReminderEmail Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/reminderEmail```

Method: ``` DELETE ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers : </summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

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


***
[Back to Top](#merchants-api)

[Back to Home](index.md#welcome-to-the-wishlist)



