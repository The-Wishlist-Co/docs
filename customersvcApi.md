
[Back to Home](index.md#welcome-to-the-wishlist)

# **Customer API**
The Customer API is used to create and manage information about a retailer's customers, such as their contact details, and whether they've agreed to receive email marketing.  The Customer resource doesn't store any credit card information. 

### Index

***

- [**Customer API**](#customer-api)
    <!-- - [Index](#index) -->
  - [**Representations**](#representations)
    - [Customer Request](#customer-request)
    - [Customer Response](#customer-response)
    - [Customer Address](#customer-address)
    - [Optin Preferences](#optin-preferences)
    - [Optin Preference](#optin-preference)
    - [Attribute Groups](#attributegroups)
    - [Attribute Group](#attributegroup)
  - [**Endpoints**](#rest-endpoints)
    - [Create a Customer](#create-a-customer)
    - [Upload Customers](#upload-customers)
    - [Validate Customer Input](#validate-customer-input)
    - [Update a Customer](#update-a-customer)
    - [Update a Customer By Customer Id](#update-a-customer-by-customer-id)
    - [Update a Customer By Customer Ref](#update-a-customer-by-customer-ref)
    - [Add address to Existing Customer](#add-address-to-existing-customer)
    - [Delete Customer Address](#delete-customer-address)
    - [Find Customer by Id](#find-customer-by-id)
    - [Find Customer by Ref](#find-customer-by-ref)
    - [Look up  Customers by email/mobile/phone/firstName/lastName](#look-up--customers-by-emailmobilephonefirstnamelastname)
    - [Delete Customer by ID](#delete-customer-by-id)
    - [Delete Customer by Ref](#delete-customer-by-ref)


## **Representations**

All requests or responses are JSON objects

### Customer Request

| Field | Type | Description |
|---|---|---|
| *customerRef* | string | Retailed assigned customer reference ID. This is not a mandatory field. If provided must be unique across tenant. |
| *customer_state* | list | One of the following values in customer state. Allowed values are *disabled*, *invited*, *enabled* OR *declined* |
| *dob* | string | Date of birth |
| *firstName* | string | first name |
| *lastName* | string | last name |
| *email* | string | customers email. Email is a unique across tenant |
| *verified_email* | boolean | field indicating customer email is verified by retailer. TWC does not verify customer email. |
| *mobile* | boolean | mobile phone number |
| *phone* | boolean | phone number |
| *taxExempt* | boolean | field indicating if a customer is tax excempt. |
| *taxExemptions* | List<string> | List of tax exemptions. This is only info only field. |
| *location* | string | TWC generated location id, this field indicates default store customer is associated with. |
| *accepts_marketing* | boolean | This field is used by when retailers only require simple marketing acceptance. |
| *marketing_preferences_updated_at* | date | date at which marketing optin levels are updated. |
| *addresses* | array of [Address](#customeraddress) | Customers addresses go here. A customer can have more than one address. |
| *optin_preferences* | [OptinPreferences](#optinpreferences) | This field indicates marketing preferences for email and sms. When using TWC native marketing, this field will decide if a customer be notified. |
| *attributeGroups* |[AttributeGroups](#attributegroups)| This field may be used to add additional attributes to entities in TWC. This field is in general available on most entities in The Wishlist platform.<br> "attributeGroups":&nbsp;{<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"customer_origin":&nbsp;"social_media",<br>&emsp;&emsp;"category_affinity":&nbsp;"electronics,&nbsp;cameras,&nbsp;gaming",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;entities"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>}<br> |


### Customer Response

| Field | Type | Description |
|---|---|---|
| *id* | string | TWC generated ID of customer entity. for e.g: *47235561-a5fe-43d1-a0ff-00b635208abe* |
| *customerRef* | string | Retailed assigned customer reference ID. This is not a mandatory field. If provided must be unique across tenant. |
| *customer_state* | list | One of the following values in customer state. Allowed values are *disabled*, *invited*, *enabled* OR *declined* |
| *dob* | string | Date of birth |
| *firstName* | string | first name |
| *lastName* | string | last name |
| *email* | string | customers email. Email is a unique across tenant |
| *verified_email* | boolean | field indicating customer email is verified by retailer. TWC does not verify customer email. |
| *mobile* | boolean | mobile phone number |
| *phone* | boolean | phone number |
| *taxExempt* | boolean | field indicating if a customer is tax excempt. |
| *taxExemptions* | List<string> | List of tax exemptions. This is only info only field. |
| *location* | string | TWC generated location id, this field indicates default store customer is associated with. |
| *accepts_marketing* | boolean | This field is used by when retailers only require simple marketing acceptance. |
| *marketing_preferences_updated_at* | date | date at which marketing optin levels are updated. |
| *defaultAddress* | [Address](#customer-address) | Customer's default address. |
| *addresses* | array of [Address](#customer-address) | Customers addresses go here. A customer can have more than one address. |
| *optin_preferences* | [OptinPreferences](#optin-preferences) | This field indicates marketing preferences for email and sms. When using TWC native marketing, this field will decide if a customer be notified. |
| *attributeGroups* |[AttributeGroups](#attributegroups)| This field may be used to add additional attributes to entities in TWC. This field is in general available on most entities in The Wishlist platform.<br> "attributeGroups":&nbsp;{<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"customer_origin":&nbsp;"social_media",<br>&emsp;&emsp;"category_affinity":&nbsp;"electronics,&nbsp;cameras,&nbsp;gaming",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;entities"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>}<br> |


### Customer Address

| Field | Type | Description |
|---|---|---|
| *address1* | string | Address line 1. |
| *address2* | string | Address line 2. |
| *city* | list | One of the following values in customer state. Allowed values are *disabled*, *invited*, *enabled* OR *declined* |
| *province* | string | Date of birth |
| *country* | string | country for e.g: *Australia* |
| *postcode* | string | postal code |
| *phone* | string | address phone number |
| *email* | string | customer email. |
| *provinceCode* | boolean | mobile phone number |
| *countryCode* | string | country codes as per [ISO 3166-1](https://en.wikipedia.org/wiki/ISO_3166-1). for e.g: *AU* for australia |
| *defaultAddress* | boolean | indicating if its the default address of customer. Default address will appear as a separate filed under customer |


### Optin Preferences

| Field | Type | Description |
|---|---|---|
| *email* | [Optin Preference](#optin-preference) | Address line 1. |
| *sms* | [Optin Preference](#optin-preference) | Address line 2. |


### Optin Preference

| Field | Type | Description |
|---|---|---|
| *opt_in_active* | boolean | if customer has opted in |
| *opt_in_updated_at* | date | Date at which optin preferences were updated. |
| *opted_in_at* | date | Date at which optin preferences were first set. |


###  AttributeGroups

| Field | Type| Description |
|---|---|---|
| *attributeGroup* | [AttributeGroup](#attributegroup) | This field holds the groups of attributes as a map of <String, [AttributeGroup](#attributegroup)>. <br> "attributeGroups":&nbsp;{<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"customer_origin":&nbsp;"social_media",<br>&emsp;&emsp;"category_affinity":&nbsp;"electronics,&nbsp;cameras,&nbsp;gaming",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;entities"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>}<br> |


###  AttributeGroup

| Field | Type| Description |
|---|---|---|
| *attributes* | map | This field holds map of attributes as a map of <string, string> <br> e.g.: &nbsp;{<br>&emsp;&emsp;"customer_origin":&nbsp;"social_media",<br>&emsp;&emsp;"category_affinity":&nbsp;"electronics,&nbsp;cameras,&nbsp;gaming",&emsp;&emsp;<br>&emsp;&ensp;}<br> |
| *description* | string | This field is a short description about the attributes captured under field *attributes*. This will only be used in the backoffice tools. |


[Back to Index](#index)

## **REST Endpoints**

- ##  **Customer**

## Create a Customer
Creates a new Customer in the Wishlist platform.  Email and referenceID must be unique or the post will fail.  

CustomerRef is the retailer's own unique customer identifier.  The Wishlist also generates a unique internal system identifier (id).  Either can be used for retrieving customer data.

Endpoint: ```/api/v2/customers```

Method: ``` POST ```

Method Name: `createCustomer`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

<!-- <details> -->
 <summary>Sample Request: </summary>
 
```json
{
  "accepts_marketing": true,
  "active": true,
  "addresses": [
    {
      "address1": "string",
      "address2": "string",
      "addressName": "string",
      "city": "string",
      "company": "string",
      "country": "string",
      "countryCode": "string",
      "customerId": "string",
      "defaultAddress": true,
      "email": "string",
      "firstName": "string",
      "id": "string",
      "lastName": "string",
      "phone": "string",
      "postcode": "string",
      "province": "string",
      "provinceCode": "string"
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "createdDate": "2022-06-20T06:21:32.358Z",
  "customerRef": "string",
  "customer_state": "disabled",
  "defaultAddress": {
    "address1": "string",
    "address2": "string",
    "addressName": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "customerId": "string",
    "defaultAddress": true,
    "email": "string",
    "firstName": "string",
    "id": "string",
    "lastName": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "dob": "25-10-1985",
  "email": "string",
  "firstName": "string",
  "id": "string",
  "lastModifiedDate": "2022-06-20T06:21:32.358Z",
  "lastName": "string",
  "marketing_optin_level": "single_opt_in",
  "marketing_preferences_updated_at": "2022-06-20T06:21:32.358Z",
  "mobile": "string",
  "phone": "string",
  "taxExempt": true,
  "taxExemptions": [
    "string"
  ],
  "optin_preferences": {
    "sms": {
      "opt_in_active": false,
      "opted_in_at": "2022-32-09 07:32:51",
      "opt_in_updated_at": "2022-32-09 07:32:51"
    },
    "email": {
      "opt_in_active": true,
      "opted_in_at": "2022-32-09 07:32:59",
      "opt_in_updated_at": "2022-32-09 07:32:59"

    }
  },  
  "verified_email": true
}

```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response  - 201 (Created)</summary>
 
 ```json
 {
  "accepts_marketing": true,
  "active": true,
  "addresses": [
    {
      "address1": "string",
      "address2": "string",
      "addressName": "string",
      "city": "string",
      "company": "string",
      "country": "string",
      "countryCode": "string",
      "customerId": "string",
      "defaultAddress": true,
      "email": "string",
      "firstName": "string",
      "id": "string",
      "lastName": "string",
      "phone": "string",
      "postcode": "string",
      "province": "string",
      "provinceCode": "string"
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "createdDate": "2022-06-20T09:00:48.098Z",
  "customerRef": "string",
  "customer_state": "disabled",
  "defaultAddress": {
    "address1": "string",
    "address2": "string",
    "addressName": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "customerId": "string",
    "defaultAddress": true,
    "email": "string",
    "firstName": "string",
    "id": "string",
    "lastName": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "dob": "25-10-1985",
  "email": "string",
  "firstName": "string",
  "id": "string",
  "lastModifiedDate": "2022-06-20T09:00:48.098Z",
  "lastName": "string",
  "marketing_optin_level": "single_opt_in",
  "marketing_preferences_updated_at": "2022-06-20T09:00:48.098Z",
  "mobile": "string",
  "phone": "string",
  "taxExempt": true,
  "taxExemptions": [
    "string"
  ],
  "optin_preferences": {
    "sms": {
      "opt_in_active": false,
      "opted_in_at": "2022-32-09 07:32:51",
      "opt_in_updated_at": "2022-32-09 07:32:51"
    },
    "email": {
      "opt_in_active": true,
      "opted_in_at": "2022-32-09 07:32:59",
      "opt_in_updated_at": "2022-32-09 07:32:59"

    }
  },
  "verified_email": true
}

```
<!-- </details>  -->

HTTP Status Code: 
```json 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Upload Customers
This API is used to create an array of customers.

*THIS API IS NOW DEPRICATED.  FOR UPLOADING MULTIPLE RECORDS PLEASE USE THE IMPEX API* 

Endpoint: ```/api/v2/upload-customers```

Method: ``` POST ```

Method Name: `uploadCustomer`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details>-->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->


<!-- <details> -->
 <summary>Request sample</summary>
 
 ```json
  [
  {
    "accepts_marketing": true,
    "active": true,
    "addresses": [
      {
        "address1": "string",
        "address2": "string",
        "addressName": "string",
        "city": "string",
        "company": "string",
        "country": "string",
        "countryCode": "string",
        "customerId": "string",
        "defaultAddress": true,
        "email": "string",
        "firstName": "string",
        "id": "string",
        "lastName": "string",
        "phone": "string",
        "postcode": "string",
        "province": "string",
        "provinceCode": "string"
      }
    ],
   "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
    "createdDate": "2022-06-20T09:21:47.710Z",
    "customerRef": "string",
    "customer_state": "disabled",
    "defaultAddress": {
      "address1": "string",
      "address2": "string",
      "addressName": "string",
      "city": "string",
      "company": "string",
      "country": "string",
      "countryCode": "string",
      "customerId": "string",
      "defaultAddress": true,
      "email": "string",
      "firstName": "string",
      "id": "string",
      "lastName": "string",
      "phone": "string",
      "postcode": "string",
      "province": "string",
      "provinceCode": "string"
    },
    "dob": "25-10-1985",
    "email": "string",
    "firstName": "string",
    "id": "string",
    "lastModifiedDate": "2022-06-20T09:21:47.710Z",
    "lastName": "string",
    "marketing_optin_level": "single_opt_in",
    "marketing_preferences_updated_at": "2022-06-20T09:21:47.710Z",
    "mobile": "string",
    "phone": "string",
    "taxExempt": true,
    "taxExemptions": [
      "string"
    ],
    "optin_preferences": {
      "sms": {
        "opt_in_active": false,
        "opted_in_at": "2022-32-09 07:32:51",
        "opt_in_updated_at": "2022-32-09 07:32:51"
      },
      "email": {
        "opt_in_active": true,
        "opted_in_at": "2022-32-09 07:32:59",
        "opt_in_updated_at": "2022-32-09 07:32:59"

      }
    },
    "verified_email": true
  }
]

```
<!-- </details> -->

<summary>Response - 200 (OK)</summary>

HTTP Status Code: 
``` json
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Validate Customer Payload
This API is used to validate a payload format.  It is primarily an internal API and typically not required/used by customers, but we do make it available to developers if required.

Endpoint: ```/api/v2/customers/validate```

Method: ``` POST ```

Method Name: `validateCustomerRequest`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!--<details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!--</details> 


<details> -->
 <summary>Sample Request</summary>

```json
{
  "accepts_marketing": true,
  "active": true,
  "addresses": [
    {
      "address1": "string",
      "address2": "string",
      "addressName": "string",
      "city": "string",
      "company": "string",
      "country": "string",
      "countryCode": "string",
      "customerId": "string",
      "defaultAddress": true,
      "email": "string",
      "firstName": "string",
      "id": "string",
      "lastName": "string",
      "phone": "string",
      "postcode": "string",
      "province": "string",
      "provinceCode": "string"
    }
  ],
 "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "createdDate": "2022-06-20T09:26:27.726Z",
  "customerRef": "string",
  "customer_state": "disabled",
  "defaultAddress": {
    "address1": "string",
    "address2": "string",
    "addressName": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "customerId": "string",
    "defaultAddress": true,
    "email": "string",
    "firstName": "string",
    "id": "string",
    "lastName": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "dob": "25-10-1985",
  "email": "string",
  "firstName": "string",
  "id": "string",
  "lastModifiedDate": "2022-06-20T09:26:27.726Z",
  "lastName": "string",
  "marketing_optin_level": "single_opt_in",
  "marketing_preferences_updated_at": "2022-06-20T09:26:27.726Z",
  "mobile": "string",
  "phone": "string",
  "taxExempt": true,
  "taxExemptions": [
    "string"
  ],
  "optin_preferences": {
    "sms": {
      "opt_in_active": false,
      "opted_in_at": "2022-32-09 07:32:51",
      "opt_in_updated_at": "2022-32-09 07:32:51"
    },
    "email": {
      "opt_in_active": true,
      "opted_in_at": "2022-32-09 07:32:59",
      "opt_in_updated_at": "2022-32-09 07:32:59"

    }
  },
  "verified_email": true
}

```
<!-- </details> -->

<summary>Response - 200 (OK)</summary>

HTTP Status Code: 
``` json
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Update a Customer
Updates Customer fields.  

The updateCustomer API determines which customer to update by comparing the unique customer identifiers, in the priorithy of id, CustomerRef, then email. 

*Note: There are two additional APIs to update customer using specifically the id or CustomerRef, which will work more efficiently than this API.*

Endpoint: ```/api/v2/customers```

Method: ``` PUT ```

Method Name: `updateCustomer`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->


<!-- <details> -->
 <summary>Sample Request</summary>

```json
{
  "accepts_marketing": true,
  "active": true,
  "addresses": [
    {
      "address1": "string",
      "address2": "string",
      "addressName": "string",
      "city": "string",
      "company": "string",
      "country": "string",
      "countryCode": "string",
      "customerId": "string",
      "defaultAddress": true,
      "email": "string",
      "firstName": "string",
      "id": "string",
      "lastName": "string",
      "phone": "string",
      "postcode": "string",
      "province": "string",
      "provinceCode": "string"
    }
  ],
"attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "createdDate": "2022-06-20T09:26:58.918Z",
  "customerRef": "string",
  "customer_state": "disabled",
  "defaultAddress": {
    "address1": "string",
    "address2": "string",
    "addressName": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "customerId": "string",
    "defaultAddress": true,
    "email": "string",
    "firstName": "string",
    "id": "string",
    "lastName": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "dob": "25-10-1985",
  "email": "string",
  "firstName": "string",
  "id": "string",
  "lastModifiedDate": "2022-06-20T09:26:58.919Z",
  "lastName": "string",
  "marketing_optin_level": "single_opt_in",
  "marketing_preferences_updated_at": "2022-06-20T09:26:58.919Z",
  "mobile": "string",
  "phone": "string",
  "taxExempt": true,
  "taxExemptions": [
    "string"
  ],
  "optin_preferences": {
    "sms": {
      "opt_in_active": false,
      "opted_in_at": "2022-32-09 07:32:51",
      "opt_in_updated_at": "2022-32-09 07:32:51"
    },
    "email": {
      "opt_in_active": true,
      "opted_in_at": "2022-32-09 07:32:59",
      "opt_in_updated_at": "2022-32-09 07:32:59"

    }
  },
  "verified_email": true
}

```
<!-- </details> -->

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "accepts_marketing": true,
  "active": true,
  "addresses": [
    {
      "address1": "string",
      "address2": "string",
      "addressName": "string",
      "city": "string",
      "company": "string",
      "country": "string",
      "countryCode": "string",
      "customerId": "string",
      "defaultAddress": true,
      "email": "string",
      "firstName": "string",
      "id": "string",
      "lastName": "string",
      "phone": "string",
      "postcode": "string",
      "province": "string",
      "provinceCode": "string"
    }
  ],
 "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "createdDate": "2022-06-20T09:26:58.956Z",
  "customerRef": "string",
  "customer_state": "disabled",
  "defaultAddress": {
    "address1": "string",
    "address2": "string",
    "addressName": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "customerId": "string",
    "defaultAddress": true,
    "email": "string",
    "firstName": "string",
    "id": "string",
    "lastName": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "dob": "25-10-1985",
  "email": "string",
  "firstName": "string",
  "id": "string",
  "lastModifiedDate": "2022-06-20T09:26:58.956Z",
  "lastName": "string",
  "marketing_optin_level": "single_opt_in",
  "marketing_preferences_updated_at": "2022-06-20T09:26:58.956Z",
  "mobile": "string",
  "phone": "string",
  "taxExempt": true,
  "taxExemptions": [
    "string"
  ],
  "optin_preferences": {
    "sms": {
      "opt_in_active": false,
      "opted_in_at": "2022-32-09 07:32:51",
      "opt_in_updated_at": "2022-32-09 07:32:51"
    },
    "email": {
      "opt_in_active": true,
      "opted_in_at": "2022-32-09 07:32:59",
      "opt_in_updated_at": "2022-32-09 07:32:59"

    }
  },
  "verified_email": true
}

```
<!-- </details> -->

HTTP Status Code: 
``` json
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Update a Customer By Customer Id
Updates Customer based on The Wishlist system generated unique ID.

Endpoint: ```/api/v2/customers/id={id:.*}"```

Method: ``` PUT ```

Method Name: `updateCustomer`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

 Path Variable: `id: customer Id`
 
<!-- <details> -->
 <summary>Sample Request</summary>

```json
{
  "accepts_marketing": true,
  "active": true,
  "addresses": [
    {
      "address1": "string",
      "address2": "string",
      "addressName": "string",
      "city": "string",
      "company": "string",
      "country": "string",
      "countryCode": "string",
      "customerId": "string",
      "defaultAddress": true,
      "email": "string",
      "firstName": "string",
      "id": "string",
      "lastName": "string",
      "phone": "string",
      "postcode": "string",
      "province": "string",
      "provinceCode": "string"
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "createdDate": "2022-06-20T09:26:58.918Z",
  "customer_state": "disabled",
  "defaultAddress": {
    "address1": "string",
    "address2": "string",
    "addressName": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "customerId": "string",
    "defaultAddress": true,
    "email": "string",
    "firstName": "string",
    "id": "string",
    "lastName": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "dob": "25-10-1985",
  "email": "string",
  "firstName": "string",
  "lastModifiedDate": "2022-06-20T09:26:58.919Z",
  "lastName": "string",
  "marketing_optin_level": "single_opt_in",
  "marketing_preferences_updated_at": "2022-06-20T09:26:58.919Z",
  "mobile": "string",
  "phone": "string",
  "taxExempt": true,
  "taxExemptions": [
    "string"
  ],
  "optin_preferences": {
    "sms": {
      "opt_in_active": false,
      "opted_in_at": "2022-32-09 07:32:51",
      "opt_in_updated_at": "2022-32-09 07:32:51"
    },
    "email": {
      "opt_in_active": true,
      "opted_in_at": "2022-32-09 07:32:59",
      "opt_in_updated_at": "2022-32-09 07:32:59"

    }
  },
  "verified_email": true
}

```
<!-- </details> -->

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "accepts_marketing": true,
  "active": true,
  "addresses": [
    {
      "address1": "string",
      "address2": "string",
      "addressName": "string",
      "city": "string",
      "company": "string",
      "country": "string",
      "countryCode": "string",
      "customerId": "string",
      "defaultAddress": true,
      "email": "string",
      "firstName": "string",
      "id": "string",
      "lastName": "string",
      "phone": "string",
      "postcode": "string",
      "province": "string",
      "provinceCode": "string"
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "createdDate": "2022-06-20T09:26:58.956Z",
  "customerRef": "string",
  "customer_state": "disabled",
  "defaultAddress": {
    "address1": "string",
    "address2": "string",
    "addressName": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "customerId": "string",
    "defaultAddress": true,
    "email": "string",
    "firstName": "string",
    "id": "string",
    "lastName": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "dob": "25-10-1985",
  "email": "string",
  "firstName": "string",
  "id": "string",
  "lastModifiedDate": "2022-06-20T09:26:58.956Z",
  "lastName": "string",
  "marketing_optin_level": "single_opt_in",
  "marketing_preferences_updated_at": "2022-06-20T09:26:58.956Z",
  "mobile": "string",
  "phone": "string",
  "taxExempt": true,
  "taxExemptions": [
    "string"
  ],
  "optin_preferences": {
    "sms": {
      "opt_in_active": false,
      "opted_in_at": "2022-32-09 07:32:51",
      "opt_in_updated_at": "2022-32-09 07:32:51"
    },
    "email": {
      "opt_in_active": true,
      "opted_in_at": "2022-32-09 07:32:59",
      "opt_in_updated_at": "2022-32-09 07:32:59"

    }
  },
  "verified_email": true
}

```
<!-- </details> -->

HTTP Status Code: 
``` json
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Update a Customer By Customer Ref
Updates Customer matching the retailer's own unique identifier- CustomerRef.

Endpoint: ```/api/v2/customers/customerRef={customerRef:.*}```

Method: ``` PUT ```

Method Name: `updateCustomer`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

 Path Variable: `customerRef : customer Ref`

<!-- <details> -->
 <summary>Sample Request</summary>

```json
{
  "accepts_marketing": true,
  "active": true,
  "addresses": [
    {
      "address1": "string",
      "address2": "string",
      "addressName": "string",
      "city": "string",
      "company": "string",
      "country": "string",
      "countryCode": "string",
      "customerId": "string",
      "defaultAddress": true,
      "email": "string",
      "firstName": "string",
      "id": "string",
      "lastName": "string",
      "phone": "string",
      "postcode": "string",
      "province": "string",
      "provinceCode": "string"
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "createdDate": "2022-06-20T09:26:58.918Z",  
  "customer_state": "disabled",
  "defaultAddress": {
    "address1": "string",
    "address2": "string",
    "addressName": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "customerId": "string",
    "defaultAddress": true,
    "email": "string",
    "firstName": "string",
    "id": "string",
    "lastName": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "dob": "25-10-1985",
  "email": "string",
  "firstName": "string",  
  "lastModifiedDate": "2022-06-20T09:26:58.919Z",
  "lastName": "string",
  "marketing_optin_level": "single_opt_in",
  "marketing_preferences_updated_at": "2022-06-20T09:26:58.919Z",
  "mobile": "string",
  "phone": "string",
  "taxExempt": true,
  "taxExemptions": [
    "string"
  ],
  "optin_preferences": {
    "sms": {
      "opt_in_active": false,
      "opted_in_at": "2022-32-09 07:32:51",
      "opt_in_updated_at": "2022-32-09 07:32:51"
    },
    "email": {
      "opt_in_active": true,
      "opted_in_at": "2022-32-09 07:32:59",
      "opt_in_updated_at": "2022-32-09 07:32:59"

    }
  },
  "verified_email": true
}

```
<!-- </details> -->

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "accepts_marketing": true,
  "active": true,
  "addresses": [
    {
      "address1": "string",
      "address2": "string",
      "addressName": "string",
      "city": "string",
      "company": "string",
      "country": "string",
      "countryCode": "string",
      "customerId": "string",
      "defaultAddress": true,
      "email": "string",
      "firstName": "string",
      "id": "string",
      "lastName": "string",
      "phone": "string",
      "postcode": "string",
      "province": "string",
      "provinceCode": "string"
    }
  ],
 "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "createdDate": "2022-06-20T09:26:58.956Z",
  "customerRef": "string",
  "customer_state": "disabled",
  "defaultAddress": {
    "address1": "string",
    "address2": "string",
    "addressName": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "customerId": "string",
    "defaultAddress": true,
    "email": "string",
    "firstName": "string",
    "id": "string",
    "lastName": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "dob": "25-10-1985",
  "email": "string",
  "firstName": "string",
  "id": "string",
  "lastModifiedDate": "2022-06-20T09:26:58.956Z",
  "lastName": "string",
  "marketing_optin_level": "single_opt_in",
  "marketing_preferences_updated_at": "2022-06-20T09:26:58.956Z",
  "mobile": "string",
  "phone": "string",
  "taxExempt": true,
  "taxExemptions": [
    "string"
  ],
  "optin_preferences": {
    "sms": {
      "opt_in_active": false,
      "opted_in_at": "2022-32-09 07:32:51",
      "opt_in_updated_at": "2022-32-09 07:32:51"
    },
    "email": {
      "opt_in_active": true,
      "opted_in_at": "2022-32-09 07:32:59",
      "opt_in_updated_at": "2022-32-09 07:32:59"

    }
  },
  "verified_email": true
}

```
<!-- </details> -->

HTTP Status Code: 
``` json
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```



## Add address to Existing Customer
Add a customer address using The Wishlist generated customer ID.

*NOTE THIS CAN ALSO BE DONE DIRECTLY USING THE UPDATE CUSTOMER APIs*


Endpoint: ```/api/v2/customers/{id}/address```

Method: ``` POST ```

Method Name: `addCustomerAddress`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!--<details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- <details> -->


<!-- </details> -->
 <summary>Sample Request</summary>

```json
{
  "address1": "string",
  "address2": "string",
  "addressName": "string",
  "city": "string",
  "company": "string",
  "country": "string",
  "countryCode": "string",
  "customerId": "string",
  "defaultAddress": true,
  "email": "string",
  "firstName": "string",
  "id": "string",
  "lastName": "string",
  "phone": "string",
  "postcode": "string",
  "province": "string",
  "provinceCode": "string"
}

```
<!-- </details> -->

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "accepts_marketing": true,
  "active": true,
  "addresses": [
    {
      "address1": "string",
      "address2": "string",
      "addressName": "string",
      "city": "string",
      "company": "string",
      "country": "string",
      "countryCode": "string",
      "customerId": "string",
      "defaultAddress": true,
      "email": "string",
      "firstName": "string",
      "id": "string",
      "lastName": "string",
      "phone": "string",
      "postcode": "string",
      "province": "string",
      "provinceCode": "string"
    }
  ],
 "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "createdDate": "2022-06-20T09:27:37.333Z",
  "customerRef": "string",
  "customer_state": "disabled",
  "defaultAddress": {
    "address1": "string",
    "address2": "string",
    "addressName": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "customerId": "string",
    "defaultAddress": true,
    "email": "string",
    "firstName": "string",
    "id": "string",
    "lastName": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "dob": "25-10-1985",
  "email": "string",
  "firstName": "string",
  "id": "string",
  "lastModifiedDate": "2022-06-20T09:27:37.333Z",
  "lastName": "string",
  "marketing_optin_level": "single_opt_in",
  "marketing_preferences_updated_at": "2022-06-20T09:27:37.333Z",
  "mobile": "string",
  "phone": "string",
  "taxExempt": true,
  "taxExemptions": [
    "string"
  ],
  "optin_preferences": {
    "sms": {
      "opt_in_active": false,
      "opted_in_at": "2022-32-09 07:32:51",
      "opt_in_updated_at": "2022-32-09 07:32:51"
    },
    "email": {
      "opt_in_active": true,
      "opted_in_at": "2022-32-09 07:32:59",
      "opt_in_updated_at": "2022-32-09 07:32:59"

    }
  },
  "verified_email": true
}

```
<!-- <details> -->

HTTP Status Code: 
``` json
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Delete Customer Address

Delete a customer address using either The Wishlist generated customer id and The Wishlist generated address id

Endpoint: ```/api/v2/customers/{id}/address/{addressId}```

Method: ``` DELETE ```

Method Name: `deleteCustomerAddress`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!--<details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Path Variable: 

```
id - customer id
addressId - Customer Address Id
```

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "accepts_marketing": true,
  "active": true,
  "addresses": [
    {
      "address1": "string",
      "address2": "string",
      "addressName": "string",
      "city": "string",
      "company": "string",
      "country": "string",
      "countryCode": "string",
      "customerId": "string",
      "defaultAddress": true,
      "email": "string",
      "firstName": "string",
      "id": "string",
      "lastName": "string",
      "phone": "string",
      "postcode": "string",
      "province": "string",
      "provinceCode": "string"
    }
  ],
 "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "createdDate": "2022-06-20T09:27:37.333Z",
  "customerRef": "string",
  "customer_state": "disabled",
  "defaultAddress": {
    "address1": "string",
    "address2": "string",
    "addressName": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "customerId": "string",
    "defaultAddress": true,
    "email": "string",
    "firstName": "string",
    "id": "string",
    "lastName": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "dob": "25-10-1985",
  "email": "string",
  "firstName": "string",
  "id": "string",
  "lastModifiedDate": "2022-06-20T09:27:37.333Z",
  "lastName": "string",
  "marketing_optin_level": "single_opt_in",
  "marketing_preferences_updated_at": "2022-06-20T09:27:37.333Z",
  "mobile": "string",
  "phone": "string",
  "taxExempt": true,
  "taxExemptions": [
    "string"
  ],

  "optin_preferences": {
    "sms": {
      "opt_in_active": false,
      "opted_in_at": "2022-32-09 07:32:51",
      "opt_in_updated_at": "2022-32-09 07:32:51"
    },
    "email": {
      "opt_in_active": true,
      "opted_in_at": "2022-32-09 07:32:59",
      "opt_in_updated_at": "2022-32-09 07:32:59"

    }
  },
  "verified_email": true
}

```
<!-- <details> -->

HTTP Status Code: 
``` json
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Get Customer by Id
Returns a customer using The Wishlist platform system generated customer ID. 

Endpoint: ```/api/v2/customers/{id}```

Method: ``` GET ``` 

Method Name: `getCustomer`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!--<details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->


<!-- <details> -->
 Path variable: `{id} : customer ID`
<!-- </details> -->

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "accepts_marketing": true,
  "active": true,
  "addresses": [
    {
      "address1": "string",
      "address2": "string",
      "addressName": "string",
      "city": "string",
      "company": "string",
      "country": "string",
      "countryCode": "string",
      "customerId": "string",
      "defaultAddress": true,
      "email": "string",
      "firstName": "string",
      "id": "string",
      "lastName": "string",
      "phone": "string",
      "postcode": "string",
      "province": "string",
      "provinceCode": "string"
    }
  ],
"attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "createdDate": "2022-06-20T09:28:14.926Z",
  "customerRef": "string",
  "customer_state": "disabled",
  "defaultAddress": {
    "address1": "string",
    "address2": "string",
    "addressName": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "customerId": "string",
    "defaultAddress": true,
    "email": "string",
    "firstName": "string",
    "id": "string",
    "lastName": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "dob": "25-10-1985",
  "email": "string",
  "firstName": "string",
  "id": "string",
  "lastModifiedDate": "2022-06-20T09:28:14.926Z",
  "lastName": "string",
  "marketing_optin_level": "single_opt_in",
  "marketing_preferences_updated_at": "2022-06-20T09:28:14.926Z",
  "mobile": "string",
  "phone": "string",
  "taxExempt": true,
  "taxExemptions": [
    "string"
  ],
  "optin_preferences": {
    "sms": {
      "opt_in_active": false,
      "opted_in_at": "2022-32-09 07:32:51",
      "opt_in_updated_at": "2022-32-09 07:32:51"
    },
    "email": {
      "opt_in_active": true,
      "opted_in_at": "2022-32-09 07:32:59",
      "opt_in_updated_at": "2022-32-09 07:32:59"

    }
  },
  "verified_email": true
}

```

<!-- </details> -->

HTTP Status Code: 
``` json
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Get Customer by CustomerRef
Returns a customer using the retailers's own unique customer identifier CustomerRef.

Endpoint: ```/api/v2/customers/{customerRef}/ref```

Method: ``` GET ``` 

Method Name: `getCustomerByRef`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->


<!-- <details> -->
 Path Variable: `customerRef : customer Ref`
	
<!-- </details> -->

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "accepts_marketing": true,
  "active": true,
  "addresses": [
    {
      "address1": "string",
      "address2": "string",
      "addressName": "string",
      "city": "string",
      "company": "string",
      "country": "string",
      "countryCode": "string",
      "customerId": "string",
      "defaultAddress": true,
      "email": "string",
      "firstName": "string",
      "id": "string",
      "lastName": "string",
      "phone": "string",
      "postcode": "string",
      "province": "string",
      "provinceCode": "string"
    }
  ],
 "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "createdDate": "2022-06-20T09:29:37.721Z",
  "customerRef": "string",
  "customer_state": "disabled",
  "defaultAddress": {
    "address1": "string",
    "address2": "string",
    "addressName": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "customerId": "string",
    "defaultAddress": true,
    "email": "string",
    "firstName": "string",
    "id": "string",
    "lastName": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "dob": "25-10-1985",
  "email": "string",
  "firstName": "string",
  "id": "string",
  "lastModifiedDate": "2022-06-20T09:29:37.721Z",
  "lastName": "string",
  "marketing_optin_level": "single_opt_in",
  "marketing_preferences_updated_at": "2022-06-20T09:29:37.721Z",
  "mobile": "string",
  "phone": "string",
  "taxExempt": true,
  "taxExemptions": [
    "string"
  ],
  "optin_preferences": {
    "sms": {
      "opt_in_active": false,
      "opted_in_at": "2022-32-09 07:32:51",
      "opt_in_updated_at": "2022-32-09 07:32:51"
    },
    "email": {
      "opt_in_active": true,
      "opted_in_at": "2022-32-09 07:32:59",
      "opt_in_updated_at": "2022-32-09 07:32:59"

    }
  },
  "verified_email": true
}

```
<!-- <details> -->

HTTP Status Code: 
``` json
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Retrieve Customers by email/mobile/phone/firstName/lastName
Returns a list of customers based on email/mobile/phone/firstName/lastName.  A record is returned only if all of the given criteria are matched.  

If no customers exist, this method returns a empty list.

Endpoint: ```/api/v2/customers/search```

Method: ``` GET ``` 

Method Name: `lookupCustomer`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->


<!-- <details> -->
 Query Parameters : 
 ```
 - email
 - firstName
 - lastName
 - mobile
 - phone
```
<!-- </details> -->

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 [
  {
    "accepts_marketing": true,
    "active": true,
    "addresses": [
      {
        "address1": "string",
        "address2": "string",
        "addressName": "string",
        "city": "string",
        "company": "string",
        "country": "string",
        "countryCode": "string",
        "customerId": "string",
        "defaultAddress": true,
        "email": "string",
        "firstName": "string",
        "id": "string",
        "lastName": "string",
        "phone": "string",
        "postcode": "string",
        "province": "string",
        "provinceCode": "string"
      }
    ],
   "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
    "createdDate": "2022-06-20T09:30:38.997Z",
    "customerRef": "string",
    "customer_state": "disabled",
    "defaultAddress": {
      "address1": "string",
      "address2": "string",
      "addressName": "string",
      "city": "string",
      "company": "string",
      "country": "string",
      "countryCode": "string",
      "customerId": "string",
      "defaultAddress": true,
      "email": "string",
      "firstName": "string",
      "id": "string",
      "lastName": "string",
      "phone": "string",
      "postcode": "string",
      "province": "string",
      "provinceCode": "string"
    },
    "dob": "25-10-1985",
    "email": "string",
    "firstName": "string",
    "id": "string",
    "lastModifiedDate": "2022-06-20T09:30:38.997Z",
    "lastName": "string",
    "marketing_optin_level": "single_opt_in",
    "marketing_preferences_updated_at": "2022-06-20T09:30:38.997Z",
    "mobile": "string",
    "phone": "string",
    "taxExempt": true,
    "taxExemptions": [
      "string"
    ],
    "optin_preferences": {
      "sms": {
        "opt_in_active": false,
        "opted_in_at": "2022-32-09 07:32:51",
        "opt_in_updated_at": "2022-32-09 07:32:51"
      },
      "email": {
        "opt_in_active": true,
        "opted_in_at": "2022-32-09 07:32:59",
        "opt_in_updated_at": "2022-32-09 07:32:59"

      }
    },
    "verified_email": true
  }
]

```
<!-- </details> -->

HTTP Status Code: 
``` json
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Delete Customer by ID
Deletes a customer.  

*NOTE, A CUSTOMERS'S WISHLISTS ARE NOT DELETED.  (A CUSTOMER CANNOT BE IDENTIFIED FROM A WISHLIST RECORD).*

Endpoint: ```/api/v2/customers/{id}```

Method: ``` DELETE ```

Method Name: `deleteCustomer`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->


<!-- <details> -->
 Path Variable: ` id : customer id `
<!-- </details> -->

<!-- <details> -->
<summary>Response - 204 (Deleted)</summary>

<!-- </details> -->

HTTP Status Code: 
``` json
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Delete Customer by CustomerRef
Deletes a customer based on the retailer's unique customer identifier CustomerRef.

Endpoint: ```/api/v2/customers/{customerRef}/ref```

Method: ``` DELETE ``` 

Method Name: `deleteCustomerByRef`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->


<!-- <details> -->
 Query Paramters : ` customerRef : customer Ref , id : Customer ID`

<!-- </details> -->

<!-- <details> -->
<summary>Response - 204 (Deleted)</summary>
<!-- </details> -->

HTTP Status Code: 
``` json
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
[Back to Top](#customer-api)
  
[Back to Home](index.md#welcome-to-the-wishlist)
