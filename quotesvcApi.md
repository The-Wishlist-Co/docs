
[Back to Home](index.md#welcome-to-the-wishlist)

# **Quote API**
The Quote APIs allow the developer to manage information about a quote, such as the store details, the quote line items, and price amounts

### Index

***

- [**Quote API**](#quote-api)
    - [Index](#index)
  - [**Representations**](#representations)
  - [Quote](#quote)
  - [Quote line](#quote-line)
  - [**REST Endpoints**](#rest-endpoints)
  - [Create a Quote](#create-a-quote)
  - [Update a Quote](#update-a-quote)
  - [Find Quote](#find-quote)
  - [Find Quotes By Customer Reference/Email](#find-quotes-by-customer-referenceemail)
  - [Delete Quote by ID](#delete-quote-by-id)
  - [Delete Quote by Ref](#delete-quote-by-ref)
  - [Create a Quote Line](#create-a-quote-line)
  - [Update a Quote Line](#update-a-quote-line)
  - [Delete Quote Line](#delete-quote-line)


## **Representations**

All requests or responses are JSON objects.

## Quote
<!-- 
<details>
 <summary>Expand for details</summary> -->

```storeName``` - string - The store name

```salesPerson``` - string - The salespersons name

```address``` - [Address](Common_Fields/address.md) - The address is saved as an array. The Address of the store will be set to the ID of that address.

```customerId``` - string - The TWC internal identifier for the customer who belongs to the quote.

```customerRef``` - string - The retailer's own customer identifier for the customer who belongs to the quote.

```firstName``` - string - The customer's first name.

```lastName``` - string - The customer's last name.

```email``` - string - The customer's email address.

```referenceNo``` - string - The reatiler's refernce number for the quote.

```expiryDate``` - The expiry date of the quote.  The date and time are in ISO 8601 format.

```totalQuoteAmount``` - decimal - Total quote amount.

```totalDiscount``` - decimal - Total discount amount.

```externalNotes``` - string - Quote notes with time stamp.

```createdAt``` - The date and time (ISO 8601 format) for when quote was created.

```id``` - string - TWC's unique identifier for the quote.

```updatedAt``` - The date and time (ISO 8601 format) when the quote information was last updated.

```deleted``` - boolean - Indicates the quote is deleted.

```locationId``` - string - The store location id (TWC identifier).

```locationRef``` - string - The store location ref (retailer's own identifier).

```quoteTax``` - decimal - The quote tax amount.

<!-- </details> -->

## Quote line
<!-- 
<details>
 <summary>Expand for details</summary> -->

```quoteId``` - string - The unique TWC internal quote identifier.

```productCode``` - string - The retailer's code for the product on this line item.

```productDescription``` - string - The description of the product on this line item.

```quantity``` - string - The quantity of the product for this line item.

```unitPrice``` - decimal - The product's unit price

```discountAmount``` - decimal - The discount amount on this line item.

```finalAmount``` - decimal - The final amount after deducting the discount on this line item.

```promotion``` - boolean - Indicates if there is a promotion on this line item.

```createdAt``` - The date and time (ISO 8601 format) when the quote line item was created.

```id``` - string - TWC's unique identifier for the quote line item.

```updatedAt``` - The date and time (ISO 8601 format) when the quote line item information was last updated.

```deleted``` - boolean - Indicates if the quote line is deleted.

<!-- </details> -->


[Back to Index](#index)

## **REST Endpoints**

- ##  **Quote**

## Create a Quote
Creates a new Quote data set in the TWC system.

Endpoint: ```/api/v1/quote```

Method: ``` POST ```

Method Name: `createQuote`

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
  "address": {
    "address": "string",
    "address1": "string",
    "city": "string",
    "contactPerson": "string",
    "countryIsocode": "string",
    "countryName": "string",
    "county": "string",
    "fax": "string",
    "phone": "string",
    "postcode": "string",
    "state": "string",
    "street": "string",
    "streetNumber": "string"
  },
  "customerId": "string",
  "customerRef": "string",
  "expiryDate": "2022-08-31T10:04:35.660Z",
  "externalNotes": {
    "Date": "notes",
    "Date": "notes",
    "Date": "notes"
  },  
  "lineItems": [
    {
      "discountAmount": 0,
      "finalAmount": 0,
      "id": "string",
      "productCode": "string",
      "productDescription": "string",
      "promotion": true,
      "quantity": 0,
      "unitPrice": 0
    }
  ],
  "referenceNo": "string",
  "salesPerson": "string",
  "storeName": "string",
  "totalDiscount": 0,
  "totalQuoteAmount": 0,
  "locationId": "string",
  "locationRef": "string",
  "quoteTax": 0,
}

```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response  - 201 (Created)</summary>
 
 ```json
 {
  "address": {
    "address": "string",
    "address1": "string",
    "city": "string",
    "contactPerson": "string",
    "countryIsocode": "string",
    "countryName": "string",
    "county": "string",
    "fax": "string",
    "phone": "string",
    "postcode": "string",
    "state": "string",
    "street": "string",
    "streetNumber": "string"
  },
  "customerId": "string",
  "customerRef": "string",
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "expiryDate": "2022-08-30T10:04:35.660Z",
  "externalNotes": {
    "Date": "notes",
    "Date": "notes",
    "Date": "notes"
  }, 
  "id": "string",
  "lineItems": [
    {
      "discountAmount": 0,
      "finalAmount": 0,
      "id": "string",
      "productCode": "string",
      "productDescription": "string",
      "promotion": true,
      "quantity": 0,
      "unitPrice": 0,
      "created_at": "2022-08-30T10:07:35.710334200Z",
      "updated_at": "2022-08-30T10:07:35.710334200Z"      
    }
  ],
  "locationId": "string",
  "locationRef": "string",
  "quoteTax": 0,
  "referenceNo": "string",
  "salesPerson": "string",
  "storeName": "string",
  "totalDiscount": 0,
  "totalQuoteAmount": 0,
  "deleted": false,
  "created_at": "2022-08-30T10:07:35.710334200Z",
  "updated_at": "2022-08-30T10:07:35.710334200Z"
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


## Update a Quote
Updates Quote data set in the TWC system.

Endpoint: ```/api/v1/quote```

Method: ``` PUT ```

Method Name: `updateQuote`

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
  "address": {
    "address": "string",
    "address1": "string",
    "city": "string",
    "contactPerson": "string",
    "countryIsocode": "string",
    "countryName": "string",
    "county": "string",
    "fax": "string",
    "phone": "string",
    "postcode": "string",
    "state": "string",
    "street": "string",
    "streetNumber": "string"
  },
  "customerId": "string",
  "customerRef": "string",
  "expiryDate": "2022-08-30T10:04:35.660Z",
  "externalNotes": {
    "Date": "notes",
    "Date": "notes",
    "Date": "notes"
  },  
  "id":"string",  
  "referenceNo": "string",
  "salesPerson": "string",
  "storeName": "string",
  "totalDiscount": 0,
  "totalQuoteAmount": 0,
  "locationId": "string",
  "locationRef": "string",
  "quoteTax": 0,
}

```
<!-- </details> -->

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "address": {
    "address": "string",
    "address1": "string",
    "city": "string",
    "contactPerson": "string",
    "countryIsocode": "string",
    "countryName": "string",
    "county": "string",
    "fax": "string",
    "phone": "string",
    "postcode": "string",
    "state": "string",
    "street": "string",
    "streetNumber": "string"
  },
  "customerId": "string",
  "customerRef": "string",
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "expiryDate": "2022-08-30T10:04:35.660Z",
  "externalNotes": {
    "Date": "notes",
    "Date": "notes",
    "Date": "notes"
  }, 
  "id": "string",
  "lineItems": [
    {
      "discountAmount": 0,
      "finalAmount": 0,
      "id": "string",
      "productCode": "string",
      "productDescription": "string",
      "promotion": true,
      "quantity": 0,
      "unitPrice": 0,
      "created_at": "2022-08-30T10:07:35.710334200Z",
      "updated_at": "2022-08-30T10:07:35.710334200Z"      
    }
  ],
  "locationId": "string",
  "locationRef": "string",
  "quoteTax": 0,
  "referenceNo": "string",
  "salesPerson": "string",
  "storeName": "string",
  "totalDiscount": 0,
  "totalQuoteAmount": 0,
  "deleted": false,
  "created_at": "2022-08-30T10:07:35.710334200Z",
  "updated_at": "2022-08-30T10:07:35.710334200Z"
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

## Find Quote
Returns a quote by its ID from a specific Store while passing the respective ID as a path param in the endpoint. The Tenant authentication maps to a Store.
If the quote does not exist, this method returns a 404.

Endpoint: ```/api/v1/quote```

Method: ``` GET ``` 

Method Name: `getquote`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!--<details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->


<!-- <details> -->
 Request Parameters: `id  : Quote Id ,Ref : Quote Reference `  

<!-- </details> -->

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
  "address": {
    "address": "string",
    "address1": "string",
    "city": "string",
    "contactPerson": "string",
    "countryIsocode": "string",
    "countryName": "string",
    "county": "string",
    "fax": "string",
    "phone": "string",
    "postcode": "string",
    "state": "string",
    "street": "string",
    "streetNumber": "string"
  },
  "customerId": "string",
  "customerRef": "string",
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "expiryDate": "2022-08-30T10:04:35.660Z",
  "externalNotes": {
    "Date": "notes",
    "Date": "notes",
    "Date": "notes"
  }, 
  "id": "string",
  "lineItems": [
    {
      "discountAmount": 0,
      "finalAmount": 0,
      "id": "string",
      "productCode": "string",
      "productDescription": "string",
      "promotion": true,
      "quantity": 0,
      "unitPrice": 0,
      "created_at": "2022-08-30T10:07:35.710334200Z",
      "updated_at": "2022-08-30T10:07:35.710334200Z"
    }
  ],
  "locationId": "string",
  "locationRef": "string",
  "quoteTax": 0,
  "referenceNo": "string",
  "salesPerson": "string",
  "storeName": "string",
  "totalDiscount": 0,
  "totalQuoteAmount": 0,
  "deleted": false,
  "created_at": "2022-08-30T10:07:35.710334200Z",
  "updated_at": "2022-08-30T10:07:35.710334200Z"
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


## Find Quotes By Customer Reference/Email
Returns a list of quote by using cusromer reference or email from the specific store by passing the respective fields as a path param in the endpoint. The Tenant authentication maps to a Store.
If the quote does not exist, this method returns a 404.

Endpoint: ```/api/v1/quote/customer```

Method: ``` GET ``` 

Method Name: `findCustomerQuotes`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!--<details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->


<!-- <details> -->
 Request Parameters: `customer_ref  : Customer reference, customer_email : Customer email,pageSize : no of expected quotes in a page, lastItemId: id of the last customer quote received in the page `  

<!-- </details> -->

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
[
 {
  "address": {
    "address": "string",
    "address1": "string",
    "city": "string",
    "contactPerson": "string",
    "countryIsocode": "string",
    "countryName": "string",
    "county": "string",
    "fax": "string",
    "phone": "string",
    "postcode": "string",
    "state": "string",
    "street": "string",
    "streetNumber": "string"
  },
  "customerId": "string",
  "customerRef": "string",
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "expiryDate": "2022-08-30T10:04:35.660Z",
  "externalNotes": {
    "Date": "notes",
    "Date": "notes",
    "Date": "notes"
  }, 
  "id": "string",
  "lineItems": [
    {
      "discountAmount": 0,
      "finalAmount": 0,
      "id": "string",
      "productCode": "string",
      "productDescription": "string",
      "promotion": true,
      "quantity": 0,
      "unitPrice": 0,
      "created_at": "2022-08-30T10:07:35.710334200Z",
      "updated_at": "2022-08-30T10:07:35.710334200Z"
    }
  ],
  "locationId": "string",
  "locationRef": "string",
  "quoteTax": 0,
  "referenceNo": "string",
  "salesPerson": "string",
  "storeName": "string",
  "totalDiscount": 0,
  "totalQuoteAmount": 0,
  "deleted": false,
  "created_at": "2022-08-30T10:07:35.710334200Z",
  "updated_at": "2022-08-30T10:07:35.710334200Z"
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


## Delete Quote by ID
Deleting a Quote marks the quote as deleted and produces the HTTP response confirming the action.
If the quote does not exist, this method returns 404 response.

Endpoint: ```/api/v1/quote/{id}```

Method: ``` DELETE ```

Method Name: `deleteQuote`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->


<!-- <details> -->
 Path Variable: ` id : quote id `
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

## Delete Quote by Ref
Deleting a Quote by ref marks the quote as deleted and produces an HTTP response confirming the action.
If the quote does not exist, this method returns 404 response.

Endpoint: ```/api/v2/quote/{Ref}/byref```

Method: ``` DELETE ``` 

Method Name: `deleteQuoteByRef`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->


<!-- <details> -->
 Path Variable : ` Ref : quote Ref`

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

- ##  **Quote Line**

## Create a Quote Line
Creates a new Quote line data set in the TWC system.

Endpoint: ```/api/v1/quote/line```

Method: ``` POST ```

Method Name: `createQuoteLine`

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
  "quoteId":"string",
  "discountAmount": 0,
  "finalAmount": 0,  
  "productCode": "string",
  "productDescription": "string",
  "promotion": true,
  "quantity": 0,
  "unitPrice": 0
}

```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response  - 201 (Created)</summary>
 
 ```json
 {  
    "id": "string",
    "discountAmount": 0,
    "finalAmount": 0,
    "id": "string",
    "productCode": "string",
    "productDescription": "string",
    "promotion": true,
    "quantity": 0,
    "unitPrice": 0,
    "created_at": "2022-08-30T05:23:49.908296Z",
    "updated_at": "2022-08-30T05:23:49.908296Z"
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


## Update a Quote Line
Updates Quote line data set in the TWC system.

Endpoint: ```/api/v1/quote/line```

Method: ``` PUT ```

Method Name: `updateQuoteLine`

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
   "id": "string",
    "discountAmount": 0,
    "finalAmount": 0,
    "id": "string",
    "productCode": "string",
    "productDescription": "string",
    "promotion": true,
    "quantity": 0,
    "unitPrice": 0  
}

```
<!-- </details> -->

<!-- <details> -->
<summary>Response - 200 (OK)</summary>

```json
 {
    "id": "string",
    "discountAmount": 0,
    "finalAmount": 0,
    "id": "string",
    "productCode": "string",
    "productDescription": "string",
    "promotion": true,
    "quantity": 0,
    "unitPrice": 0,
    "created_at": "2022-08-30T05:23:49.908296Z",
    "updated_at": "2022-08-30T05:23:49.908296Z"      
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

## Delete Quote Line
Deleting a Quote line marks the quote line as deleted and produces an HTTP response confirming the action.
If the quote line does not exist, this method returns 404 response.

Endpoint: ```/api/v1/quote/line/{id}```

Method: ``` DELETE ```

Method Name: `deleteQuoteLine`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->


<!-- <details> -->
 Path Variable: ` id : quote line id `
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
[Back to Top](#quote-api)
  
[Back to Home](index.md#welcome-to-the-wishlist)
