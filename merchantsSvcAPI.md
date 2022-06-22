
# **Merchants API**
The Merchants resource stores information about a merchant and their stores.


## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.


<details>
 <summary><font size="4">Merchant </font></summary>

```activated_date```--Datetime

```active```-- boolean-- to indicate the merchant is active or not

```admin_email```--string--admin email details

```company_code```--string

```billing_address```--string

```contact_address```--string

```contact_person```--string

```created_at```--Datetime

```deleted```--boolean

```deleted_date```--Datetime

```id```--string

```merchant_name```--string

```modified_by```--string

```trading_as```--string

```updated_at```--Datetime

</details>

<details>
 <summary><font size="4">Plan </font></summary>

```plan_name```--string

```id```--string

<details>
 <summary><font size="4">plan_type </font></summary>

  ```name```--string

  ```id```--string

  ```request_limit```--number--admin email details

 </details>
 <details>
 <summary><font size="4">subscription_price </font></summary>

  ```amount```--number

  ```currency_code```--string  

 </details>
</details>

<details>
 <summary><font size="4">Store </font></summary>

```deactivated_at```--Datetime

```deactivated```-- boolean-- to indicate the merchant is active or not

```default_country```--string--

```media_url```--string

```merchant_id```--string

```plan_id```--string

```store_key```--string

```created_at```--Datetime

```deleted```--boolean

```deleted_date```--Datetime

```id```--string

```store_name```--string

```modified_by```--string

```store_state```--string

```store_url```-string

```targeted_countries```-string

```updated_at```--Datetime

</details>



## Register Merchant

Method: ``` POST ``` 

Endpoint: ```​/api​/v1​/merchant```

OAuth 2.0 Scopes: 

Sample Request :
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


## Update Merchant

Method: ``` PUT ``` 

Endpoint: ```​/api​/v1​/merchant```

OAuth 2.0 Scopes: 

Sample Request :
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Deactivate Merchant

Endpoint: ```/api/v1/merchant/{id}/deactivate```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `id  : Merchant Id`

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`



### Find Merchant

Endpoint: ```/api/v1/merchant/{id}```

Method: ``` GET ```

OAuth 2.0 Scopes: 

Request Parameters: `id  : Mechant Id`

Response : `200 OK , 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Create a Plan

Endpoint: ```​/api​/v1​/plan​/```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Update a Plan

Endpoint: ```​/api​/v1​/plan​/```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Delete a Plan

Endpoint: ```/api/v1/plan/{planId}/```

Method: ``` DELETE ```

OAuth 2.0 Scopes: 

Request Parameters: `planId  : unique Plan Id`

Response : `200 OK ,204	No Content, 401 Unauthorized, 403 Forbidden`


### Find Plan

Endpoint: ```/api/v1/plan/{planId}/```

Method: ``` GET ```

OAuth 2.0 Scopes: 

Request Parameters: `planId  : Unique plan Id`

Response : `200 OK , 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Find All Plans

Endpoint: ```/api/v1/plans/```

Method: ``` GET ```

OAuth 2.0 Scopes: 

Response : `200 OK , 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Create a Store

Endpoint: ```​/api/v1/store```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`



### Update a Store

Endpoint: ```/api/v1/store/{id}```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Find a Store

Endpoint: ```/api/v1/store```

Method: ``` GET ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,storeKey: store key`

Response : `200 OK , 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Find a Store

Endpoint: ```/api/v1/store/{storeId}```

Method: ``` GET ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id`

Response : `200 OK , 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Deactivate Store

Endpoint: ```/api/v1/stores/{storeId}/deactivate```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique Store Id`

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Create Subscription plan

Endpoint: ```/api/v1/merchant/{merchantId}/store/{storeId}/plan/{planId}/```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `merchantId  : Unique Merchant Id,storeId: Unique store id,planId: Unique plan id `

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update Subscription plan

Endpoint: ```/api/v1/merchant/{merchantId}/store/{storeId}/plan/{planId}```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `merchantId  : Unique Merchant Id,storeId: Unique store id,planId: Unique plan id `

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Cancel Subscription plan

Endpoint: ```/api/v1/merchant/{merchantId}/store/{storeId}```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `merchantId  : Unique Merchant Id,storeId: Unique store id `

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Get Additional Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/additionalConfigs```

Method: ``` GET ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Response : `200 OK , 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Get All Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/allConfig```

Method: ``` GET ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Response : `200 OK , 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Get Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityConfig```

Method: ``` GET ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Response : `200 OK , 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Get Store Tenant Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/tenantConfig```

Method: ``` GET ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Response : `200 OK , 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Create Additional Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/additionalConfigs```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update Additional Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/additionalConfigs```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Create App Config Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/appconfig```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update App Config Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/appconfig```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Create Customer Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/customer```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update Customer Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/customer```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Create Email Template Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/emailtemplate```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update Email Template Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/emailtemplate```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Create Inventory Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/inventory```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update Inventory Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/inventory```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Create Location Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/location```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update Location Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/location```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Create Order Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/order```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update Order Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/order```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Create Price Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/price```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update Price Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/price```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Create Product Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/product```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update Product Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/product```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Create Store Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/store```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update Store Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/store```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Create Wishlist Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/wishlist```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update Wishlist Entity Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/entityconfig/wishlist```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Get Notification Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification```

Method: ``` GET ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Response : `200 OK , 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Create Notification Config

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
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
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Create BackInStock Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/backInStock```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update BackInStock Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/backInStock```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Delete BackInStock Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/backInStock```

Method: ``` DELETE ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Response : `200 OK ,204	No Content, 401 Unauthorized, 403 Forbidden`


### Create LowInStock Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/lowInStock```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update LowInStock Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/lowInStock```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Delete LowInStock Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/lowInStock```

Method: ``` DELETE ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Response : `200 OK ,204	No Content, 401 Unauthorized, 403 Forbidden`


### Create PriceDrop Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/priceDrop```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update PriceDrop Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/priceDrop```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Delete PriceDrop Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/priceDrop```

Method: ``` DELETE ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Response : `200 OK ,204	No Content, 401 Unauthorized, 403 Forbidden`


### Create ReminderEmail Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/reminderEmail```

Method: ``` POST ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Update ReminderEmail Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/reminderEmail```

Method: ``` PUT ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Sample Request:
<details>
{
  "deActivated": true,
  "emailTemplate": "string",
  "frequency": "string",
  "realtime": "string"
}
</details>

Response : `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Delete ReminderEmail Notification Settings

Endpoint: ```/api/v1/merchant/{merchId}/store/{storeId}/notification/reminderEmail```

Method: ``` DELETE ```

OAuth 2.0 Scopes: 

Request Parameters: `storeId  : Unique store Id,merchId: Unique merchant Id`

Response : `200 OK ,204	No Content, 401 Unauthorized, 403 Forbidden`

***
[Back to Index](index.md)
