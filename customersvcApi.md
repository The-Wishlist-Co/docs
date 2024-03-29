
[Back to Home](index.md#welcome-to-the-wishlist)

# **Customer API**
The Customer API is used to create and manage information about a retailer's customers, such as their contact details, and whether they've agreed to receive email marketing.  The Customer resource doesn't store any credit card information. 

A customer must be created before a wishlist can be created for that customer (we currently don't support anonymous wishlists, although this may be added in the future)

There are 4 customer identifiers supported:
- customerID is TWCs internal unique customer identifier
- customerRef is typically the main identifier assigned to the customer by the retailer (e.g. loyalty number)
- alternateCustomerRef is a secondary customer identifier optionally assigned to the customer by the retailer
- customer email is used in many of TWC's APIs, and must be unique

The only mandatory field when creating a customer is email, although we recommend you also assign the retailers customer identifier (customerRef) and firstName, lastName.

### Index

***

[**Customer API**](#customer-api)
- [**General Notes**](#general-notes)
- [**Representations**](#representations)
  - [Customer Request](#customer-request)
  - [Customer Response](#customer-response)
  - [Customer Address](#customer-address)
  - [Optin Preferences](#optin-preferences)
  - [Optin Preference](#optin-preference)
  - [Attribute Groups](#attributegroups)
  - [Attribute Group](#attributegroup)
- [**Endpoints**](#rest-endpoints)
  - [Customer](#customer)
    - [Create](#create)
    - [Update](#update)
    - [Delete](#delete)
    - [Get](#get)
    - [Notes](#notes)


## **General Notes**
Customer endpoints must be prefixed with ```services/customerservice``` for example create customer endpoint is ```/api/v2/customers```, when you invoke the api it will be ```/services/customerservice/api/v2/customers```

Production api endpoint ```https://api.au-aws.thewishlist.io/services/customerservice/api/v2/customers```


## **Representations**

All requests or responses are JSON objects

### Customer Request

| Field | Type | Description |
|---|---|---|
| *customerRef* | string | Retailer assigned customer reference number. This is not a mandatory field. If provided it must be unique across your tenant. |
| *alternateCustomerRef* | string | Retailer assigned optional customer reference number. This is not a mandatory field. If provided it must be unique. |
| *dob* | date | Date of birth of customer in *dd-mm-yyy* format. for example: 28-11-1999|
| *firstName* | string | First name |
| *lastName* | string | Last name |
| *email* | string | Customers email address. Email is a mandatory field and must be unique within your tenant. |
| *mobile* | string | Mobile phone number |
| *phone* | string | Phone number |
| *vipStatus* | Boolean | Indicates if the customer is a VIP |
| *loyaltyTier* | string | Customer's loyalty tier |
| *spendToNextTier* | string | Amount customer has to spend to reach next loyalty tier |
| *joinedStoreId* | string | Retailer's store reference code for location customer was first created.  This should equate to a locationRef in TWC |
| *memberSince* | date | Date the customer joined the retailer's loyalty program|
| *addresses* | array of [Address](#customeraddress) | An array of the Customer's addresses. A customer can have more than one address, but we recommend only storing the primary address |
| *optin_preferences* | [OptinPreferences](#optinpreferences) | This object indicates marketing preferences for email and SMS |
| *attributeGroups* |[AttributeGroups](#attributegroups)| This field may be used to add additional attributes to entities in TWC and in general is available on most entities in The Wishlist Company platform.<br> "attributeGroups":&nbsp;{<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"customer_origin":&nbsp;"social_media",<br>&emsp;&emsp;"category_affinity":&nbsp;"electronics,&nbsp;cameras,&nbsp;gaming",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;entities"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>}<br> |


### Customer Response

Note:  The following list shows the primary response fields.  The actual response may include additional internal or depreciated fields

| Field | Type | Description |
|---|---|---|
| *id* | string | TWC generated unique ID (internal identifier) of the customer entity. for example: *47235561-a5fe-43d1-a0ff-00b635208abe* |
| *customerRef* | string | Retailer assigned customer identifier. This is not a mandatory field, but if provided it must be unique across your tenant. |
| *alternateCustomerRef* | string | Retailer assigned optional customer reference number. This is not a mandatory field. If provided it must be unique. |
| *dob* | string | Date of birth |
| *firstName* | string | First name |
| *lastName* | string | Last name |
| *email* | string | Customers email address.  Email must be unique across your tenant |
| *mobile* | string | Mobile phone number |
| *phone* | string | Phone number |
| *deleted* | string | Indicates if the customer has been deleted |
| *lifetimeOrderValue* | string | Total value of orders for this customer since joining.  Calculated by TWC |
| *averageSpendPerAnnum* | string | Customer's average spend per year.  Calculated by TWC |
| *running12monthSpend* | string | Customer's spend in the last 12 months.  Calculated by TWC |
| *totalOrders* | string | Number of orders customer has placed.  Calculated by TWC |
| *totalSpend* | string | Customer's total spend.  Calculated by TWC |
| *lastOrderDate* | date | Date and time of the customer's last order. Determined by TWC |
| *lastOrderRef* | string | Reference number of the customer's last order. Determined by TWC |
| *createdDate* | string | Time and date that the customer was created in TWC |
| *joinedStoreId* | string | Reference number of the store where the customer joined.  Equates to a locationRef in TWC |
| *loyaltyTier* | string | Customer's loyalty tier.  Note this is not managed by TWC |
| *spendToNextTier* | string | Amount customer has to spend to reach next loyalty tier.  Note this is NOT calculated by TWC. |
| *memberSince* | string | Date customer joined any loyalty program.  Note this is not managed by TWC |
| *vipStatus* | Boolean | Indicates customer is a VIP|
| *lastModified* | date | Time and date the customer record was last modified |
| *addresses* | array of [Address](#customer-address) | Customers addresses array. A customer can have more than one address. |
| *optin_preferences* | [OptinPreferences](#optin-preferences) | Indicates marketing preferences for email and SMS. |
| *attributeGroups* |[AttributeGroups](#attributegroups)| This field may be used to add additional attributes to entities in TWC. This field is generally available on most entities in The Wishlist platform.<br> "attributeGroups":&nbsp;{<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"customer_origin":&nbsp;"social_media",<br>&emsp;&emsp;"category_affinity":&nbsp;"electronics,&nbsp;cameras,&nbsp;gaming",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;entities"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>}<br> |


### Customer Address

| Field | Type | Description |
|---|---|---|
| *address1* | string | Address line 1 |
| *address2* | string | Address line 2 |
| *addressID* | string | Internal TWC identifier|
| *addressRef* | string | Retailer's Address identifier if one exists|
| *city* | string | City|
| *company* | string | Company|
| *email* | string | The email address associated with the address|
| *firstName* | string | The first name of the person associated with the address|
| *lastName* | string | The last name of the person associated with the address|
| *name* | string | The name of the person associated with the address|
| *postcode* | string | Postal code |
| *phone* | string | Address phone number |
| *province* | string | The state or province for the address |
| *provinceCode* | string | Abbreviation for the customer's province or state|
| *country* | string | Country for example: *Australia* |
| *countryCode* | string | Country codes as per [ISO 3166-1](https://en.wikipedia.org/wiki/ISO_3166-1). e.g: *AU* for australia |


### Optin Preferences

| Field | Type | Description |
|---|---|---|
| *email* | [Optin Preference](#optin-preference) | Opt In preference for email |
| *sms* | [Optin Preference](#optin-preference) | Opt-in preference for SMS |


### Optin Preference

| Field | Type | Description |
|---|---|---|
| *opt_in_active* | boolean | Indicates if a customer has opted in |
| *opt_in_updated_at* | date | Date at which optin preferences were updated |
| *opted_in_at* | date | Date at which optin preferences were first set |


###  AttributeGroups

| Field | Type| Description |
|---|---|---|
| *attributeGroup* | [AttributeGroup](#attributegroup) | This field holds the groups of attributes as a map of <String, [AttributeGroup](#attributegroup)>. <br> "attributeGroups":&nbsp;{<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"customer_origin":&nbsp;"social_media",<br>&emsp;&emsp;"category_affinity":&nbsp;"electronics,&nbsp;cameras,&nbsp;gaming",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;entities"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>}<br> |


###  AttributeGroup

| Field | Type| Description |
|---|---|---|
| *attributes* | map | This field holds map of attributes as a map of <string, string> <br> e.g.: &nbsp;{<br>&emsp;&emsp;"customer_origin":&nbsp;"social_media",<br>&emsp;&emsp;"category_affinity":&nbsp;"electronics,&nbsp;cameras,&nbsp;gaming",&emsp;&emsp;<br>&emsp;&ensp;}<br> |
| *description* | string | This field is a short description about the attributes captured under field *attributes*. This is only  used in the TWC backoffice tools. |


[Back to Index](#index)

# **Endpoints**
## **Customer**

## Create a customer
Creates a new customer in The Wishlist.  Fields 'email' and 'customerRef' are unique fields.  email is a mandatory field.

| Endpoint| ```/api/v2/customers```|
|-----------|---------------|
| Method    | POST          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

<!-- <details> -->
 <summary>Sample Customer Request: </summary>

```json
{
  "email": "test@customer.com",
  "customerRef": "CUST11959",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "addresses": [
    {
      "address1": "Wish Street 3",
      "address2": "Corner of Wish Street and List Crescent",
      "city": "Wishlist City",
      "country": "Australia",
      "countryCode": "AU",
      "email": "cust@email.com",
      "firstName": "Cust",
      "lastName": "Test",
      "phone": "0151 7445 6927",
      "postcode": "10000",
      "province": "New South Wales",
      "provinceCode": "NSW"
    }
  ],
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "optin_preferences" : {
      "email": {
          "opt_in_active": true
      }
  }
}
```

Sample HTTP 201 response

 ```json
 {
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "CUST11959",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "addresses": [
    {
      "address1": "Wish Street 3",
      "address2": "Corner of Wish Street and List Crescent",
      "city": "Wishlist City",
      "country": "Australia",
      "countryCode": "AU",
      "email": "cust@email.com",
      "firstName": "Cust",
      "lastName": "Test",
      "phone": "0151 7445 6927",
      "postcode": "10000",
      "province": "New South Wales",
      "provinceCode": "NSW"
    }
  ],
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

```
<!-- </details>  -->

HTTP Status Code: 
```json 
- 201 Created
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
```

## Create Multiple Customers
This API is used to create an array of customers.

| Endpoint| ```/api/v2/upload-customers```|
|-----------|---------------|
| Method    | POST          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

 <summary>Request sample</summary>
 
 ```json
  [
    {
    "email": "test@customer.com",
    "customerRef": "CUST11959",
    "firstName": "FirstName",
    "lastName": "LastName",
    "mobile": "623362386238",
    "phone": "623362386238",
    "dob": "25-10-1900",
    "addresses": [
      {
        "address1": "Wish Street 3",
        "address2": "Corner of Wish Street and List Crescent",
        "city": "Wishlist City",
        "country": "Australia",
        "countryCode": "AU",
        "email": "cust@email.com",
        "firstName": "Cust",
        "lastName": "Test",
        "phone": "0151 7445 6927",
        "postcode": "10000",
        "province": "New South Wales",
        "provinceCode": "NSW"
      }
    ],
    "attributeGroups": {
        "retailer_additional_info": {
            "attributes": {
                "crm_default_account_id": "1234",
                "triquestra_person_code": "TQ1234"
            },
            "description": "CRM and Triquestra extra attributes"
        }
    },
    "optin_preferences" : {
        "email": {
            "opt_in_active": true
        }
    }
  }
]

```
<!-- </details> -->
<summary>Response - 202 (Accepted)</summary>

HTTP Status Code: 
```
- 202 OK
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
```

## UPDATE

### Update customer by customer ID or customerRef
    
  Update a customer using the TWC customer identifier, or using the retailer's customerRef.

| Endpoint| ```/api/v2/customers```|
|-----------|---------------|
| Method    | PUT          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```id``` This is the TWC generated unique identifier for the customer being updated. |
| url path variable |```customerRef``` This is the retailer's identifier for the customer being updated. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
<!--
<summary>Sample Customer Request: </summary>
-->
```json
{
   "email": "updated-email@customerportal.com",
   "customerRef": "new-customer-ref",
   "mobile": "623362386238",
    "phone": "623362386250",
    "attributeGroups": {
        "retailer_additional_info": {
            "attributes": {
                "crm_default_account_id": "1234",
                "triquestra_person_code": "TQ1234"
            },
            "description": "CRM and Triquestra extra attributes updated"
        }
    }
}
```

Sample HTTP 200 response

 ```json
 {
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "new-customer-ref",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "addresses": [
    {
      "address1": "Wish Street 3",
      "address2": "Corner of Wish Street and List Crescent",
      "city": "Wishlist City",
      "country": "Australia",
      "countryCode": "AU",
      "email": "cust@email.com",
      "firstName": "Cust",
      "lastName": "Test",
      "phone": "0151 7445 6927",
      "postcode": "10000",
      "province": "New South Wales",
      "provinceCode": "NSW"
    }
  ],
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "active": true,
  "accepts_marketing": false,
  "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
  "customer_state": "enabled",
  "taxExempt": false,
  "taxExemptions": [],
  "verified_email": false,
  "createdDate": "2023-05-19T03:14:32.181Z",
  "lastModifiedDate": "2023-05-19T03:45:02.530Z",
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

```
<!-- </details>  -->

HTTP Status Code: 
```json 
- 201 Created
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
```

<!--

#### Update a customer by reference number

Update a customer by customer reference number. TWC will lookup customer by the given reference number

| Endpoint| ```/api/v2/customers/customerRef={customerRef}```|
|-----------|---------------|
| Method    | PUT          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```customerRef``` This is the retailer assigned unique number of the customer being updated. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|


 <summary>Sample Customer Request: </summary>

```json
{
    "email": "updated-email@customerportal.com",
    "mobile": "623362386238",
    "phone": "623362386250",
    "attributeGroups": {
        "retailer_additional_info": {
            "attributes": {
                "crm_default_account_id": "1234",
                "triquestra_person_code": "TQ1234"
            },
            "description": "CRM and Triquestra extra attributes updated"
        }
    }
}
```

Sample HTTP 200 response

 ```json
 {
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "CUST11959",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "addresses": [
    {
      "address1": "Wish Street 3",
      "address2": "Corner of Wish Street and List Crescent",
      "city": "Wishlist City",
      "country": "Australia",
      "countryCode": "AU",
      "email": "cust@email.com",
      "firstName": "Cust",
      "lastName": "Test",
      "phone": "0151 7445 6927",
      "postcode": "10000",
      "province": "New South Wales",
      "provinceCode": "NSW"
    }
  ],
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "active": true,
  "accepts_marketing": false,
  "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
  "customer_state": "enabled",
  "taxExempt": false,
  "taxExemptions": [],
  "verified_email": false,
  "createdDate": "2023-05-19T03:14:32.181Z",
  "lastModifiedDate": "2023-05-19T03:45:02.530Z",
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

```

HTTP Status Code: 
```json 
- 201 Created
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
```
-->
### Update customer by email
    
  Update a customer using the customer's email address

| Endpoint| ```/api/v2/customers/email={email:.*}```|
|-----------|---------------|
| Method    | PUT          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```email``` This is the email of the customer being updated. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
<!--
<summary>Sample Customer Request: </summary>
-->
```json
{
   "email": "updated-email@customerportal.com",
   "customerRef": "new-customer-ref",
   "mobile": "623362386238",
    "phone": "623362386250",
    "attributeGroups": {
        "retailer_additional_info": {
            "attributes": {
                "crm_default_account_id": "1234",
                "triquestra_person_code": "TQ1234"
            },
            "description": "CRM and Triquestra extra attributes updated"
        }
    }
}
```

Sample HTTP 200 response

 ```json
 {
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "new-customer-ref",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "addresses": [
    {
      "address1": "Wish Street 3",
      "address2": "Corner of Wish Street and List Crescent",
      "city": "Wishlist City",
      "country": "Australia",
      "countryCode": "AU",
      "email": "cust@email.com",
      "firstName": "Cust",
      "lastName": "Test",
      "phone": "0151 7445 6927",
      "postcode": "10000",
      "province": "New South Wales",
      "provinceCode": "NSW"
    }
  ],
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "active": true,
  "accepts_marketing": false,
  "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
  "customer_state": "enabled",
  "taxExempt": false,
  "taxExemptions": [],
  "verified_email": false,
  "createdDate": "2023-05-19T03:14:32.181Z",
  "lastModifiedDate": "2023-05-19T03:45:02.530Z",
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

```
<!-- </details>  -->

HTTP Status Code: 
```json 
- 201 Created
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
```

<!--

#### Add address to Existing Customer

Add a customer address using The Wishlist generated customer identifier.

*NOTE THIS CAN ALSO BE DONE DIRECTLY USING THE UPDATE CUSTOMER APIs*

| Endpoint| ```/api/v2/customers/{id}/address```|
|-----------|---------------|
| Method    | POST          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```id``` This is the TWC generated unique ID of the customer being updated. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|


 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


 <summary>Sample Request</summary>

```json
{
  "address1": "Wish Street 3",
  "address2": "Corner of Wish Street and List Crescent",
  "city": "Wishlist City",
  "country": "Australia",
  "countryCode": "AU",
  "email": "cust@email.com",
  "firstName": "Cust",
  "lastName": "Test",
  "phone": "0151 7445 6927",
  "postcode": "10000",
  "province": "New South Wales",
  "provinceCode": "NSW"
}

```

<summary>Response - 200 (OK)</summary>

``` json
{
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "new-customer-ref",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "addresses": [
    {
      "address1": "Wish Street 3",
      "address2": "Corner of Wish Street and List Crescent",
      "city": "Wishlist City",
      "country": "Australia",
      "countryCode": "AU",
      "email": "cust@email.com",
      "firstName": "Cust",
      "lastName": "Test",
      "phone": "0151 7445 6927",
      "postcode": "10000",
      "province": "New South Wales",
      "provinceCode": "NSW"
    }
  ],
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "active": true,
  "accepts_marketing": false,
  "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
  "customer_state": "enabled",
  "taxExempt": false,
  "taxExemptions": [],
  "verified_email": false,
  "createdDate": "2023-05-19T03:14:32.181Z",
  "lastModifiedDate": "2023-05-19T03:45:02.530Z",
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

``

HTTP Status Code: 
```
- 201 Created
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

<!--
### Validate

#### Validate Customer Payload

This API is used to validate a payload format.  It is primarily an internal API and typically not required/used by customers, but we do make it available to developers if required.

| Endpoint| ```/api/v2/customers/validate```|
|-----------|---------------|
| Method    | POST          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|


 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

 <summary>Sample Customer Request: </summary>

```json
{
  "email": "test@customer.com",
  "customerRef": "CUST11959",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "addresses": [
    {
      "address1": "Wish Street 3",
      "address2": "Corner of Wish Street and List Crescent",
      "city": "Wishlist City",
      "country": "Australia",
      "countryCode": "AU",
      "email": "cust@email.com",
      "firstName": "Cust",
      "lastName": "Test",
      "phone": "0151 7445 6927",
      "postcode": "10000",
      "province": "New South Wales",
      "provinceCode": "NSW"
    }
  ],
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "optin_preferences" : {
      "email": {
          "opted_in": true
      }
  }
}
```

If customer payload is valid, it will respond with an HTTP 200

HTTP Status Code: 
```
- 200 OK
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
```
-->

## DELETE
<!--
#### Delete customer address

Delete a customer address requires both the The Wishlist generated customer ID and The Wishlist generated address ID

| Endpoint| ```/api/v2/customers/{id}/address/{addressId}```|
|-----------|---------------|
| Method    | DELETE          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```id``` This is the TWC generated unique ID of the customer whose address is being deleted. |
| url path variable |```addressId``` This is the TWC generated unique ID of the customer whose address being deleted. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| X-TWC-Tenant  | {Tenant Name}    |

<summary>Response - 200 (OK)</summary>

```json
 {
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "new-customer-ref",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "active": true,
  "accepts_marketing": false,
  "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
  "customer_state": "enabled",
  "taxExempt": false,
  "taxExemptions": [],
  "verified_email": false,
  "createdDate": "2023-05-19T03:14:32.181Z",
  "lastModifiedDate": "2023-05-19T03:45:02.530Z",
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

```

HTTP Status Code: 
```
- 200 OK
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```
-->
    
### Delete Customer using customer ID or customerRef
Delete a customer using the internal TWC customer identifier, or the retailer's identifier.  Note that the customer's wishlists are not deleted as they are required for reporting purposes, but they are deidentified.

| Endpoint| ```/api/v2/customers```|
|-----------|---------------|
| Method    | DELETE          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```id``` This is the TWC generated unique ID of the customer being deleted. |
| url path variable |```customerRef``` This is the retailer's identifier of the customer being deleted. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
<summary>Response - 204 (No Content)</summary>


## GET

### Get Customer by Id
Returns a customer using The Wishlist platform system generated customer identifier. 

| Endpoint| ```/api/v2/customers/{id}```|
|-----------|---------------|
| Method    | GET          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```id``` This is the TWC generated unique ID of the customer. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "new-customer-ref",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "active": true,
  "accepts_marketing": false,
  "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
  "customer_state": "enabled",
  "taxExempt": false,
  "taxExemptions": [],
  "verified_email": false,
  "createdDate": "2023-05-19T03:14:32.181Z",
  "lastModifiedDate": "2023-05-19T03:45:02.530Z",
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

```

<!-- </details> -->

HTTP Status Code: 
``` json
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

### Get Customer by CustomerRef
Returns a customer using the retailers's own unique customer number.

| Endpoint| ```/api/v2/customers/{customerRef}/ref```|
|-----------|---------------|
| Method    | GET          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```customerRef``` This is the retailer assigned number of the customer. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "new-customer-ref",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "active": true,
  "accepts_marketing": false,
  "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
  "customer_state": "enabled",
  "taxExempt": false,
  "taxExemptions": [],
  "verified_email": false,
  "createdDate": "2023-05-19T03:14:32.181Z",
  "lastModifiedDate": "2023-05-19T03:45:02.530Z",
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

```
<!-- <details> -->

HTTP Status Code: 
``` json
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

### Get Customer by Email
Returns a customer using the retailers's customer email.

| Endpoint| ```/api/v2/customers/{email}/email```|
|-----------|---------------|
| Method    | GET          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```email``` This is the retailer customer email. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "new-customer-ref",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "active": true,
  "accepts_marketing": false,
  "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
  "customer_state": "enabled",
  "taxExempt": false,
  "taxExemptions": [],
  "verified_email": false,
  "createdDate": "2023-05-19T03:14:32.181Z",
  "lastModifiedDate": "2023-05-19T03:45:02.530Z",
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

```
<!-- <details> -->

HTTP Status Code: 
``` json
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

### Get Customer using Alternate Customer Reference
Returns a customer using the retailers's alternateCustomerRef.

| Endpoint| ```/api/v2/customers/{alternateCustomerRef}/alternateCustomerRef```|
|-----------|---------------|
| Method    | GET          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```alternateCustomerRef``` This is the retailer alternate customer identifier (where used) |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "new-customer-ref",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "active": true,
  "accepts_marketing": false,
  "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
  "customer_state": "enabled",
  "taxExempt": false,
  "taxExemptions": [],
  "verified_email": false,
  "createdDate": "2023-05-19T03:14:32.181Z",
  "lastModifiedDate": "2023-05-19T03:45:02.530Z",
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

```
<!-- <details> -->

HTTP Status Code: 
``` json
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

### GET all customers by email/mobile/phone/firstName/lastName

Returns a list of customers with a matching email/mobile/phone/firstName/lastName.  A record is returned only if all of the given criteria are matched.   If no customers exist, this method returns a empty list.

| Endpoint| ```/api/v2/customers/search```|
|-----------|---------------|
| Method    | GET          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| query parameters |```email``` Email being searched. |
| query parameters |```firstName``` First name to search. |
| query parameters |```lastName``` Last name to search |
| query parameters |```mobile``` Mobile number to search. |
| query parameters |```phone``` Phone to search. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 [
    {
    "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
    "email": "test@customer.com",
    "customerRef": "new-customer-ref",
    "firstName": "FirstName",
    "lastName": "LastName",
    "mobile": "623362386238",
    "phone": "623362386238",
    "dob": "25-10-1900",
    "attributeGroups": {
        "retailer_additional_info": {
            "attributes": {
                "crm_default_account_id": "1234",
                "triquestra_person_code": "TQ1234"
            },
            "description": "CRM and Triquestra extra attributes"
        }
    },
    "active": true,
    "accepts_marketing": false,
    "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
    "customer_state": "enabled",
    "taxExempt": false,
    "taxExemptions": [],
    "verified_email": false,
    "createdDate": "2023-05-19T03:14:32.181Z",
    "lastModifiedDate": "2023-05-19T03:45:02.530Z",
    "optin_preferences": {
      "sms": {
          "opt_in_active": false
      },
      "email": {
          "opt_in_active": false,
          "opted_in_at": "2023-05-19T03:48:22.075Z",
          "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
      }
    }
  },
  {
    "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
    "email": "test@customer.com",
    "customerRef": "new-customer-ref",
    "firstName": "FirstName",
    "lastName": "LastName",
    "mobile": "623362386238",
    "phone": "623362386238",
    "dob": "25-10-1900",
    "attributeGroups": {
        "retailer_additional_info": {
            "attributes": {
                "crm_default_account_id": "1234",
                "triquestra_person_code": "TQ1234"
            },
            "description": "CRM and Triquestra extra attributes"
        }
    },
    "active": true,
    "accepts_marketing": false,
    "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
    "customer_state": "enabled",
    "taxExempt": false,
    "taxExemptions": [],
    "verified_email": false,
    "createdDate": "2023-05-19T03:14:32.181Z",
    "lastModifiedDate": "2023-05-19T03:45:02.530Z",
    "optin_preferences": {
      "sms": {
          "opt_in_active": false
      },
      "email": {
          "opt_in_active": false,
          "opted_in_at": "2023-05-19T03:48:22.075Z",
          "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
      }
    }
  }
]

```
<!-- </details> -->

HTTP Status Code: 
``` json
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

## Notes

### Create a customer note
Create a note against a customer.

| Endpoint| ```/api/v2/customer/note```|
|-----------|---------------|
| Method    | POST          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "new-customer-ref",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "active": true,
  "accepts_marketing": false,
  "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
  "customer_state": "enabled",
  "taxExempt": false,
  "taxExemptions": [],
  "verified_email": false,
  "createdDate": "2023-05-19T03:14:32.181Z",
  "lastModifiedDate": "2023-05-19T03:45:02.530Z",
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

```
<!-- <details> -->

HTTP Status Code: 
``` json
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

### Update a customer note using note ID
Update an existing customer note

| Endpoint| ```/api/v2/customer/note```|
|-----------|---------------|
| Method    | PUT          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "new-customer-ref",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "active": true,
  "accepts_marketing": false,
  "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
  "customer_state": "enabled",
  "taxExempt": false,
  "taxExemptions": [],
  "verified_email": false,
  "createdDate": "2023-05-19T03:14:32.181Z",
  "lastModifiedDate": "2023-05-19T03:45:02.530Z",
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

```
<!-- <details> -->

HTTP Status Code: 
``` json
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

### Get all notes for a customer using customer ID or customerRef
Retrieve all notes for a given customer

| Endpoint| ```/api/v2/customer/notes```|
|-----------|---------------|
| Method    | GET          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable  |```id``` TWC unique customer identifier. |
| url path variable  |```customerRef``` Retailer's unique customer identifier. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "new-customer-ref",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "active": true,
  "accepts_marketing": false,
  "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
  "customer_state": "enabled",
  "taxExempt": false,
  "taxExemptions": [],
  "verified_email": false,
  "createdDate": "2023-05-19T03:14:32.181Z",
  "lastModifiedDate": "2023-05-19T03:45:02.530Z",
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

```
<!-- <details> -->

HTTP Status Code: 
``` json
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

### Get a specific customer note
Retrieve a specific customer note by note ID

| Endpoint| ```/api/v2/customer/note/{id}```|
|-----------|---------------|
| Method    | GET          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| URL path parameter |```id``` TWC unique note identifier. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "new-customer-ref",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "active": true,
  "accepts_marketing": false,
  "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
  "customer_state": "enabled",
  "taxExempt": false,
  "taxExemptions": [],
  "verified_email": false,
  "createdDate": "2023-05-19T03:14:32.181Z",
  "lastModifiedDate": "2023-05-19T03:45:02.530Z",
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

```
<!-- <details> -->

HTTP Status Code: 
``` json
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

### Delete a specific customer note
Delete a specific customer note by note ID

| Endpoint| ```/api/v2/customer/note/{id}```|
|-----------|---------------|
| Method    | DELETE          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| URL path parameter |```id``` TWC unique note identifier. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "new-customer-ref",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "active": true,
  "accepts_marketing": false,
  "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
  "customer_state": "enabled",
  "taxExempt": false,
  "taxExemptions": [],
  "verified_email": false,
  "createdDate": "2023-05-19T03:14:32.181Z",
  "lastModifiedDate": "2023-05-19T03:45:02.530Z",
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

```
<!-- <details> -->

HTTP Status Code: 
``` json
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

### DELETE all notes for a specific customer, by customer ID or customerRef
Delete all notes a specific customer 

| Endpoint| ```/api/v2/customer/notes```|
|-----------|---------------|
| Method    | DELETE          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```id``` TWC unique customer identifier. |
| url path variable  |```customerRef``` Retailer's unique customer identifier. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "id": "7c14445d-c9fb-457d-90ec-114a04e57bc3",
  "email": "test@customer.com",
  "customerRef": "new-customer-ref",
  "firstName": "FirstName",
  "lastName": "LastName",
  "mobile": "623362386238",
  "phone": "623362386238",
  "dob": "25-10-1900",
  "attributeGroups": {
      "retailer_additional_info": {
          "attributes": {
              "crm_default_account_id": "1234",
              "triquestra_person_code": "TQ1234"
          },
          "description": "CRM and Triquestra extra attributes"
      }
  },
  "active": true,
  "accepts_marketing": false,
  "marketing_preferences_updated_at": "2023-05-19T03:45:02.530Z",
  "customer_state": "enabled",
  "taxExempt": false,
  "taxExemptions": [],
  "verified_email": false,
  "createdDate": "2023-05-19T03:14:32.181Z",
  "lastModifiedDate": "2023-05-19T03:45:02.530Z",
  "optin_preferences": {
    "sms": {
        "opt_in_active": false
    },
    "email": {
        "opt_in_active": false,
        "opted_in_at": "2023-05-19T03:48:22.075Z",
        "opt_in_updated_at": "2023-05-19T03:48:22.075Z"
    }
  }
}

```
<!-- <details> -->

HTTP Status Code: 
``` json
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```


***
[Back to Top](#customer-api)
  
[Back to Home](index.md#welcome-to-the-wishlist)
