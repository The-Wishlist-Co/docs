
[Back to Home](index.md#welcome-to-the-wishlist)

# **Reports API**
Reporting APIs  is a guide for customers on how to use an API to generate and deliver reports. The documentation typically provides details on supported report types, data sources, parameters.


### Index

***

- [**Reports API**](#report-api)
    <!-- - [Index](#index) -->
  - [**Representations**](#representations)
  - [**REST Endpoints**](#rest-endpoints)
    - [Top Products Report](#top-wishlisted-product)
    - [Customer Report](#customer-report)
    - [Wishlist Report](#wishlist-report)
    - [Product Conversion Report](#product-conversion-report)
	- [Product Conversion Summary Report](#product-conversion-summary-report)

## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.

<!-- 
<details>
 <summary>Expand for details</summary> -->

```startDate``` - date - start date(yyyy-mm-dd)

```endDate``` - date - end date(yyyy-mm-dd)

```pageNumber``` - integer - page number 

```pageSize``` - integer - page size

```reportType``` - String - to generate the report on product, product-color,product-color-size basis. P for product,
                 PC for product-color and PCS for product-color-size



<!-- </details> -->

[Back to Index](#index)

## **REST Endpoints**

- ##  **Reports**

## Top Wishlisted Product
This report will generate the list of products and the number of times they have been added to wishlists. 


Endpoint: ```/api/analytics```

Method: ``` GET ```

Method Name: `topwishlistproduct`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

<<!-- <details> -->
 Query Parameters : 
 ```
 - startDate
 - endDate
 - pageNumber
 - pageSize
 - reportType
```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response  - 200 (OK)</summary>
 
 ```json
 {
  "data": [
    {
      "description": "string",
      "imageLink": "string",
      "numberOftimes": 0,
      "productRef": "string",
      "productTitle": "string",
      "variantColor": "string",
      "variantSize": "string"
    }
  ],
  "pageNumber": "string",
  "pageSize": "string"
}

```
<!-- </details>  -->

HTTP Status Code: 
```json 
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

## Customer  Report
This report will generate the list of  of all customers with wishlists.    


Endpoint: ```/api/analytics```

Method: ``` GET ```

Method Name: `customerreport`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

<<!-- <details> -->
 Query Parameters : 
 ```
 - startDate
 - endDate
 - pageNumber
 - pageSize
```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response  - 200 (OK)</summary>
 
 ```json
 {
  "data": [
    {
      "add_to_wishlist": "string",
      "back_in_stock": "string",
      "conversions": "string",
      "createdDate": "string",
      "customerName": "string",
      "email": "string",
      "interactions": "string",
      "lastInteractionDate": "string",
      "low_stock": "string",
      "phone": "string",
      "post_store_visit": "string",
      "price_Drop": "string",
      "reminder": "string",
      "staff": "string",
      "store": "string",
      "totalConverionRevenue": "string",
      "totalWishlist": "string",
      "totalWishlistItems": "string",
      "valueOfproducts": "string"
    }
  ],
  "pageNumber": "string",
  "pageSize": "string"
}

```
<!-- </details>  -->

HTTP Status Code: 
```json 
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

## Wishlist Report
This report will generate the list  all wishlists created between certain given dates.


Endpoint: ```/api/analytics```

Method: ``` GET ```

Method Name: `wishlistreport`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

<<!-- <details> -->
 Query Parameters : 
 ```
 - startDate
 - endDate
 - pageNumber
 - pageSize
```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response  - 200 (OK)</summary>
 
 ```json
 {
  "data": [
    {
      "createdDate": "string",
      "customerName": "string",
      "email": "string",
      "lastInteractionDate": "string",
      "phone": "string",
      "staff": "string",
      "store": "string",
      "totalItemValue": "string",
      "totalProducts": "string",
      "wishId": "string"
    }
  ],
  "pageNumber": "string",
  "pageSize": "string"
}

```
<!-- </details>  -->

HTTP Status Code: 
```json 
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

## Product Conversion Report
This report will generate the list  of all conversions over a given time period.

Endpoint: ```/api/analytics```

Method: ``` GET ```

Method Name: `product-conversion`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

<<!-- <details> -->
 Query Parameters : 
 ```
 - startDate
 - endDate
 - pageNumber
 - pageSize
```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response  - 200 (OK)</summary>
 
 ```json
 {
  "data": [
    {
      "email": "string",
      "imageLink": "string",
      "orderRef": "string",
      "productName": "string",
      "productRef": "string",
      "purchasedDate": "string",
      "salePrice": "string",
      "storeId": "string",
      "totalOrderValue": "string",
      "variantColour": "string",
      "variantSize": "string"
    }
  ],
  "pageNumber": "string",
  "pageSize": "string"
}

```
<!-- </details>  -->

HTTP Status Code: 
```json 
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

## Product Conversion Summary Report
This report will generate the list of products and the number of times they have been added to wishlists. 


Endpoint: ```/api/analytics```

Method: ``` GET ```

Method Name: `product-conversion-summary`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

<<!-- <details> -->
 Query Parameters : 
 ```
 - startDate
 - endDate
 - pageNumber
 - pageSize
 - reportType
```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response  - 200 (OK)</summary>
 
 ```json
 {
  "data": [
    {
      "description": "string",
      "generatedRevenue": "string",
      "imageLink": "string",
      "numberOftimes": 0,
      "productRef": "string",
      "productTitle": "string",
      "variantColor": "string",
      "variantSize": "string"
    }
  ],
  "pageNumber": "string",
  "pageSize": "string"
}
```
<!-- </details>  -->

HTTP Status Code: 
```json 
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

***
[Back to Top](#reports-api)
  
[Back to Home](index.md#welcome-to-the-wishlist)