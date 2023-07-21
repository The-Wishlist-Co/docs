
[Back to Home](index.md#welcome-to-the-wishlist)

# **Customer API**
The Customer API is used to create and manage information about a retailer's customers, such as their contact details, and whether they've agreed to receive email marketing.  The Customer resource doesn't store any credit card information. 

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
    - [Validate](#validate)
    - [Delete](#delete)
    - [Get](#get)


## **General Notes**
Customer endpoints must be prefixed with ```services/customerservice``` for example create customer endpoint is ```/api/v2/customers```, when you invoke the api it will be ```/services/customerservice/api/v2/customers```

Production api endpoint ```https://api.au-aws.thewishlist.io/services/customerservice/api/v2/customers```



## **Representations**

All requests or responses are JSON objects

### Customer Request

| Field | Type | Description |
|---|---|---|
| *customerRef* | string | Retailer assigned customer reference ID. This is not a mandatory field. If provided it must be unique across your tenant. |
| *customer_state* | list | One of the following values : *disabled*, *invited*, *enabled* OR *declined* |
| *dob* | date | Date of birth of customer in *dd-mm-yyy* format. for example: 28-11-1999|
| *firstName* | string | First name |
| *lastName* | string | Last name |
| *email* | string | Customers email address. Email is a mandatory field and must be unique within your tenant. |
| *verified_email* | boolean | Indicates that the customer email is verified by the retailer. TWC does not verify customer emails. |
| *mobile* | string | Mobile phone number |
| *phone* | string | Phone number |
| *taxExempt* | boolean | Indicates if a customer is tax excempt. |
| *taxExemptions* | List<string> | List of tax exemptions. This is an information only field. |
| *location* | string | TWC generated location id.  This field indicates the default store the customer is associated with. |
| *accepts_marketing* | boolean | This field is used when the retailer only requires a simple marketing acceptance. Further deteail may be included in using the optin_preferences|
| *marketing_preferences_updated_at* | date | Last date at which marketing optin details were updated. |
| *addresses* | array of [Address](#customeraddress) | An array of the Customer's addresses. A customer can have more than one address. |
| *optin_preferences* | [OptinPreferences](#optinpreferences) | This object indicates marketing preferences for email and SMS |
| *attributeGroups* |[AttributeGroups](#attributegroups)| This field may be used to add additional attributes to entities in TWC and in general is available on most entities in The Wishlist Company platform.<br> "attributeGroups":&nbsp;{<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"customer_origin":&nbsp;"social_media",<br>&emsp;&emsp;"category_affinity":&nbsp;"electronics,&nbsp;cameras,&nbsp;gaming",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;entities"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>}<br> |


### Customer Response

| Field | Type | Description |
|---|---|---|
| *id* | string | TWC generated ID (internal identifier) of the customer entity. for example: *47235561-a5fe-43d1-a0ff-00b635208abe* |
| *customerRef* | string | Retailer assigned customer identifier. This is not a mandatory field, but if provided it must be unique across your tenant. |
| *customer_state* | list | One of the following values: *disabled*, *invited*, *enabled* OR *declined* |
| *dob* | string | Date of birth |
| *firstName* | string | First name |
| *lastName* | string | Last name |
| *email* | string | Customers email address.  Email must be unique across your tenant |
| *verified_email* | boolean | Indicates the customer email is verified by retailer. TWC does not verify customer emails. |
| *mobile* | string | Mobile phone number |
| *phone* | string | Phone number |
| *taxExempt* | boolean | Indicates if a customer is tax excempt. |
| *taxExemptions* | List<string> | List of tax exemptions. This is only information only field. |
| *location* | string | TWC generated location identifier.  This field indicates the default store the customer is associated with. |
| *accepts_marketing* | boolean | This field is used when retailers only require simple marketing acceptance. optin_preferences can be used for more detailed preference management.|
| *marketing_preferences_updated_at* | date | Last date at which marketing optin levels were updated. |
| *defaultAddress* | [Address](#customer-address) | Customer's default address. |
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
### CREATE
Creates a new Customer in the Wishlist platform. Fields 'email' and 'customerRef' are unique fields. 

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

*THIS API IS NOW DEPRICATED.  FOR UPLOADING MULTIPLE RECORDS PLEASE USE THE IMPEX API* 

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


### UPDATE

#### Update Customer By ID
    
    Update a customer using the TWC customer identifier. TWC will lookup customer by its given customer ID.

| Endpoint| ```/api/v2/customers/id={id}```|
|-----------|---------------|
| Method    | PUT          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```id``` This is the TWC generated unique identifier of the customer being updated. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
 <summary>Sample Customer Request: </summary>

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


#### Update a customer by reference ID

Update a customer by customer reference ID. TWC will lookup customer by the given reference ID

| Endpoint| ```/api/v2/customers/customerRef={customerRef}```|
|-----------|---------------|
| Method    | PUT          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```customerRef``` This is the retailer assigned unique ID of the customer being updated. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
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
<!-- </details>  -->

HTTP Status Code: 
```json 
- 201 Created
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
```

#### Add address to Existing Customer

Add a customer address using The Wishlist generated customer identifier.

*NOTE THIS CAN ALSO BE DONE DIRECTLY USING THE UPDATE CUSTOMER APIs*

| Endpoint| ```/api/v2/customers/{id}/address```|
|-----------|---------------|
| Method    | POST          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```id``` This is the TWC generated unique ID of the customer being updated. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->
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

<!-- <details> -->
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

```
<!-- <details> -->

HTTP Status Code: 
```
- 201 Created
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


### Validate

#### Validate Customer Payload

This API is used to validate a payload format.  It is primarily an internal API and typically not required/used by customers, but we do make it available to developers if required.

| Endpoint| ```/api/v2/customers/validate```|
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
          "opted_in": true
      }
  }
}
```

If customer payload is valid, it will respond with an HTTP 200

<!-- </details>  -->

HTTP Status Code: 
```
- 200 OK
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
```

### DELETE

#### Delete customer address

Delete a customer address requires both the The Wishlist generated customer ID and The Wishlist generated address ID

| Endpoint| ```/api/v2/customers/{id}/address/{addressId}```|
|-----------|---------------|
| Method    | DELETE          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```id``` This is the TWC generated unique ID of the customer whose address is being deleted. |
| url path variable |```addressId``` This is the TWC generated unique ID of the customer whose address being deleted. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| X-TWC-Tenant  | {Tenant Name}    |

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
```
- 200 OK
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

    
#### Delete Customer

| Endpoint| ```/api/v2/customers/{id}```|
|-----------|---------------|
| Method    | DELETE          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```id``` This is the TWC generated unique ID of the customer being deleted. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<!-- <details> -->
<summary>Response - 204 (No Content)</summary>


## GET

#### Get Customer by Id
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

#### Get Customer by CustomerRef
Returns a customer using the retailers's own unique customer identifier CustomerRef.

| Endpoint| ```/api/v2/customers/{customerRef}/ref```|
|-----------|---------------|
| Method    | GET          |
| Headers   | X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```customerRef``` This is the retailer assigned ID of the customer. |
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


#### Retrieve Customers by email/mobile/phone/firstName/lastName

    Returns a list of customers based on email/mobile/phone/firstName/lastName.  A record is returned only if all of the given criteria are matched.   If no customers exist, this method returns a empty list.

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

## Delete Customer by ID

    Deletes a customer using the TWC unique identifier.  The customer's wishlists are not deleted as they are required for reporting purposes.  (Note.  A customer cannot be identified from a wishlist record).*

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

***
[Back to Top](#customer-api)
  
[Back to Home](index.md#welcome-to-the-wishlist)
