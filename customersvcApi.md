
[Back to Index](index.md)
***

# **Customer API**
The Customer resource stores information about a shop's customers, such as their contact details, their order history, and whether they've agreed to receive email marketing.

The Customer resource also holds information on the status of a customer's account. Customers with accounts save time at checkout when they're logged in because they don't need to enter their contact information. You can use the Customer API to check whether a customer has an active account, and then invite them to create one if they don't.

For security reasons, the Customer resource doesn't store credit card information. Customers always need to enter this information at checkout.

### Index

***

- [**Customer API**](#customer-api)
    <!-- - [Index](#index) -->
  - [**Representations**](#representations)
  - [**REST Endpoints**](#rest-endpoints)
    - [Create a Customer](#create-a-customer)
    - [Upload Customers](#upload-customers)
    - [Validate Customer Input](#validate-customer-input)
    - [Update a Customer](#update-a-customer)
    - [Add address to Existing Customer](#add-address-to-existing-customer)
    - [Find Customer by Id](#find-customer-by-id)
    - [Find Customer by Ref](#find-customer-by-ref)
    - [Look up  Customers by email/mobile/phone/firstName/lastName](#look-up--customers-by-emailmobilephonefirstnamelastname)
    - [Delete Customer by ID](#delete-customer-by-id)
    - [Delete Customer by Ref](#delete-customer-by-ref)

## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.
Represents a customer. If a store field is defined in a store, then the customer account is specific to the store.

<!-- 
<details>
 <summary>Expand for details</summary> -->

```accepts_marketing``` - boolean - To enable marketing for a customer.

```active``` - boolean - To enable  a customer.

```addresses``` - [Address](Common_Fields/address.md) - The address is saved as an array. The Address of the customer will be set to the ID of that address.

```attributeGroups``` - [AttributeGroup](Common_Fields/attributeGroup.md) - The grup of attibute values stored under as a object in group of atributeGroups.

```createdDate``` - The date and time (ISO 8601 format) when the customer was created.

```customerRef``` - string - User generated refernce number.

```customerState``` - string - Represents the customer current active status.
- disabled
- invited
- enabled
- declined 

```default_address``` - [Address](Common_Fields/address.md) - The default address for the customer. The address is saved as an array. The defaultShippingAddress of the customer will be set to the ID of that address.

```dob``` - string - The Customer's Date of Birth .

```email``` - string -
The customer's email address and the main identifier of uniqueness for a customer account. Attempting to assign the same email address to multiple customers returns an error.


```firstName``` - string -The customer's first name.

```id``` - string -A unique identifier for the customer.

```lastModifiedDate``` - The date and time (ISO 8601 format) when the customer information was last updated.

```lastName``` - string - The customer's last name.

```marketing_optin_level``` - string  - Optional - The marketing subscription opt-in level, as described in the Sender Best Common Practices, that the customer gave when they consented to receive marketing material by email. If the customer does not accept email marketing, then this property will be set to null. Valid values:
- single_opt_in
- confirmed_opt_in
- unknown

```marketing_preferences_updated_at``` - DateTime - The date and time (ISO 8601 format) when customer preferences updated at.

```mobile``` - string -The unique phone number (E.164 format) for this customer. Attempting to assign the same phone number to multiple customers returns an error. The property can be set using different formats, but each format must represent a number that can be dialed from anywhere in the world.

```phone``` - string -The unique phone number (E.164 format) for this customer. Attempting to assign the same phone number to multiple customers returns an error. The property can be set using different formats, but each format must represent a number that can be dialed from anywhere in the world.

```taxExempt``` - boolean -Whether the customer is exempt from paying taxes on their order. If true, then taxes won't be applied to an order at checkout. If false, then taxes will be applied at checkout.

```taxExemptions``` string - Whether the customer is exempt from paying specific taxes on their order. Canadian taxes only.

```verified_email``` - boolean -Whether the customer has verified their email address.

<!-- </details> -->

[Back to Index](#index)

## **REST Endpoints**

- ##  **Customer**

## Create a Customer
Creates a new Customer data set in the TWC system, then the wishlist is assigned to the created customer. All wishlists and orders will be assigned to the created customer.

Endpoint: ```/api/v2/customers```

Method: ``` POST ```

Method Name: `createCustomer`

OAuth 2.0 Scopes: `Tenant authentication`

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
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
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
  "dob": "2022-06-20T06:21:32.358Z",
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
  "verified_email": true
}

```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response</summary>
 
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
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
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
  "dob": "2022-06-20T09:00:48.098Z",
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
  "verified_email": true
}

```
<!-- </details>  -->

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Upload Customers
Creates an array of new Customers in the TWC system.

Endpoint: ```/api/v2/upload-customers```

Method: ``` POST ```

Method Name: `createCustomer`

OAuth 2.0 Scopes: `Tenant authentication`

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
        "attribute_group": "string",
        "attributes": {
          "additionalProp1": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp2": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp3": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          }
        },
        "is_obsolete": true
      },
      "additionalProp2": {
        "attribute_group": "string",
        "attributes": {
          "additionalProp1": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp2": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp3": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          }
        },
        "is_obsolete": true
      },
      "additionalProp3": {
        "attribute_group": "string",
        "attributes": {
          "additionalProp1": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp2": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp3": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          }
        },
        "is_obsolete": true
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
    "dob": "2022-06-20T09:21:47.710Z",
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
    "verified_email": true
  }
]

```
<!-- </details> -->



HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Validate Customer Input
Validates the customer input

Endpoint: ```/api/v2/customers/validate```

Method: ``` POST ```

Method Name: `validateCustomerRequest`

OAuth 2.0 Scopes: `Tenant authentication`

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
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
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
  "dob": "2022-06-20T09:26:27.726Z",
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
  "verified_email": true
}

```
<!-- </details> -->

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Update a Customer
Updates Customer data set in the TWC system.

Endpoint: ```/api/v2/customers```

Method: ``` PUT ```

Method Name: `updateCustomer`

OAuth 2.0 Scopes: `Tenant authentication`

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
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
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
  "dob": "2022-06-20T09:26:58.919Z",
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
  "verified_email": true
}

```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response</summary>

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
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
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
  "dob": "2022-06-20T09:26:58.956Z",
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
  "verified_email": true
}

```
<!-- </details> -->

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Add address to Existing Customer
Update the Customer data by adding the new address details.

Endpoint: ```/api/v2/customers/{id}/address```

Method: ``` POST ```

Method Name: `addCustomerAddress`

OAuth 2.0 Scopes: `Tenant authentication`

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
 <summary>Sample Response</summary>

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
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
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
  "dob": "2022-06-20T09:27:37.333Z",
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
  "verified_email": true
}

```
<!-- <details> -->

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Find Customer by Id
Returns a customer by its ID from a specific Store while passing the respective ID as a path param in the endpoint. The Tenant authentication maps to a Store.
If the customer does not exist, this method returns a Blank.

Endpoint: ```/api/v2/customers/{id}```

Method: ``` GET ``` 

Method Name: `getCustomer`

OAuth 2.0 Scopes: `Tenant authentication`

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
 <summary>Sample Response</summary>

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
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
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
  "dob": "2022-06-20T09:28:14.926Z",
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
  "verified_email": true
}

```

<!-- </details> -->

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Find Customer by Ref
Returns a customer by its Ref from a specific Store while passing the respective Ref as a path param in the endpoint. The Tenant authentication maps to a Store.
If the customer does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/v2/customers/{customerRef}/ref```

Method: ``` GET ``` 

Method Name: `getCustomerByRef`

OAuth 2.0 Scopes: `Tenant authentication`

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
 <summary>Sample Response</summary>

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
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
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
  "dob": "2022-06-20T09:29:37.721Z",
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
  "verified_email": true
}

```
<!-- <details> -->

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Look up  Customers by email/mobile/phone/firstName/lastName
Returns a list of  customers  from a specific Store while passing the email/mobile/phone/firstName/lastName as a Query params in the endpoint. The Tenant authentication maps to a Store.
If the customers does not exist, this method returns a empty list.

Endpoint: ```/api/v2/customers/search```

Method: ``` GET ``` 

Method Name: `lookupCustomer`

OAuth 2.0 Scopes: `Tenant authentication`

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
 <summary>Sample Response</summary>

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
        "attribute_group": "string",
        "attributes": {
          "additionalProp1": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp2": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp3": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          }
        },
        "is_obsolete": true
      },
      "additionalProp2": {
        "attribute_group": "string",
        "attributes": {
          "additionalProp1": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp2": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp3": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          }
        },
        "is_obsolete": true
      },
      "additionalProp3": {
        "attribute_group": "string",
        "attributes": {
          "additionalProp1": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp2": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp3": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          }
        },
        "is_obsolete": true
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
    "dob": "2022-06-20T09:30:38.997Z",
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
    "verified_email": true
  }
]

```
<!-- </details> -->

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Delete Customer by ID
Deleting a Customer marks the customer as deleted and produces the HTTP response confirming the action.
If the customer does not exist, this method returns a empty response.

Endpoint: ```/api/v2/customers/{id}```

Method: ``` DELETE ```

Method Name: `deleteCustomer`

OAuth 2.0 Scopes: `Tenant authentication`

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
 <summary>Sample Response</summary>
 OK
<!-- </details> -->

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Delete Customer by Ref
Deleting a Customer by ref marks the customer as deleted and produces the HTTP response confirming the action.
If the customer does not exist, this method returns a empty response.

Endpoint: ```/api/v2/customers/{customerRef}/ref```

Method: ``` DELETE ``` 

Method Name: `deleteCustomerByRef`

OAuth 2.0 Scopes: `Tenant authentication`

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
 <summary>Sample Response</summary>
 OK
<!-- </details> -->

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```



***
[Back to Index](#index)
  
[Back to Home](index.md)