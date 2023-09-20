
[Back to Home](index.md#welcome-to-the-wishlist)

# **Reports API**
Reporting APIs  is a guide for customers on how to use an API to generate and deliver reports. The documentation typically provides details on supported report types, data sources, parameters.


### Index

***

- [**Reports API**](#report-api)
    <!-- - [Index](#index) -->
  - [**Representations**](#representations)
  - [**REST Endpoints**](#rest-endpoints)
    - [Top Wishlist Product](#top-wishlisted-product)
    - [Customer Report](#customer-report)
    - [Wishlist Report](#wishlist-report)
    - [Product Conversion Report](#product-conversion-report)
    - [Product Conversion Summary Report](#product-conversion-summary-report)
    - [Customer Conversion  Report](#customer-conversion-report)
    - [Interaction Report](#interaction-report)
    - [Get Wishlist Item Count](#get-wishlist-item-count)
    - [Get Raw Entity Counts](#get-raw-entity-counts)
    - [Key Wishlist Metrics](#key-wishlist-metrics)
    - [Get Daily WL Customer Counts](#get-daily-wl-customer-counts)
    - [Get Daily WL Products Counts](#get-daily-wl-products-counts)
    - [Get Daily Wishlist Conversion Revenue](#get-daily-wl-conversion-revenue)
    - [Get Daily WL Interaction Count](#get-daily-wl-interaction-count)
    

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


Endpoint: ```/api/analytics/top-wishlist-product```

Method: ``` GET ```

Method Name: `getTopWishlistProduct`

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


Endpoint: ```/api/analytics/customer-report```

Method: ``` GET ```

Method Name: `getCustomerReport`

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


Endpoint: ```/api/analytics/wishlist-report```

Method: ``` GET ```

Method Name: `getWishlistReport`

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

Endpoint: ```/api/analytics/product-conversion-report```

Method: ``` GET ```

Method Name: `getProductConversionReport`

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
This report will generate the list of products and the number of times they have been converted into order. 


Endpoint: ```/api/analytics/product-conversion-summary-report```

Method: ``` GET ```

Method Name: `getProductConversionSummaryReport`

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

## Customer Conversion  Report
This report will generate the list of customers and the number of times they have been converted an item to order 


Endpoint: ```/api/analytics/customer-conversion-report```

Method: ``` GET ```

Method Name: `getCustomerConversionReport`

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
      "customerName": "string",
      "email": "string",
      "numberOfconversion": "string",
      "phone": "string",
      "totalRevenue": "string"
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

## Interaction Report
This report will generate the list of all the interactions made on the given period


Endpoint: ```/api/analytics/interaction-report```

Method: ``` GET ```

Method Name: `getInteractionReport`

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
      "createdAt": "string",
      "customerEmail": "string",
      "customerId": "string",
      "customerRef": "string",
      "entityType": "string",
      "interactionType": "string",
      "itemId": "string",
      "productId": "string",
      "productRef": "string",
      "salePrice": "string",
      "source": "string",
      "staffName": "string",
      "storeId": "string",
      "variantAttributes": "string",
      "variantId": "string",
      "wishlistId": "string"
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

## Get Wishlist Item Count
This API will return the number of items which are added by the customer into their wishlist


Endpoint: ```/api/analytics/wishlist-item-count/{customerId}```

Method: ``` GET ```

Method Name: `getWishlistItemCount`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

<<!-- <details> -->
 Path Parameters : 
 ```
 - customerId
```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response  - 200 (OK)</summary>
 
 ```
 return the count as integer
```
<!-- </details>  -->

HTTP Status Code: 
```json 
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

## Get Raw Entity Counts
This API will return the total number of records available in the twc system for the given entity

Entity name should be like this InventoryLevel,Customer,Products,Variants,Wishlist,Order


Endpoint: ```/api/analytics/raw-entity-counts```

Method: ``` GET ```

Method Name: `getRawEntityCounts`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

<<!-- <details> -->
 Path Parameters : 
 ```
 - entityName
```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response  - 200 (OK)</summary>
 
 ```
 return the count as integer
```
<!-- </details>  -->

HTTP Status Code: 
```json 
- 200 OK
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
```

## Key Wishlist Metrics
This API will return the details required for the dashboard such as total customer , wishlist , revenue etc


Endpoint: ```/api/analytics/key-wl-metrics```

Method: ``` GET ```

Method Name: `getKeyWLMetrics`

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

<<!-- <details> -->
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response  - 200 (OK)</summary>
 
 ```json
 {
  "avgInteractionsOrCustomer": "string",
  "avgOrderValue": "string",
  "avgProductsPerWL": "string",
  "avgWLPerCustomer": "string",
  "avgWLValue": "string",
  "totalCustomers": "string",
  "totalProducts": "string",
  "totalRevenue": "string",
  "totalWishlists": "string"
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

## Get Daily WL Customer Counts
This report will generate the list of customers count for each date for the given period to display in the dashboard chart.


Endpoint: ```/api/analytics/daily-wl-customer-counts```

Method: ``` GET ```

Method Name: `getDailyWLCustomerCounts`

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
```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response  - 200 (OK)</summary>
 
 ```json
 {
  "data": [
    {
      "xValue": "string",
      "yValue": {
        "label": "string",
        "value": 0
      }
    }
  ],
  "horizontalTitle": "string",
  "totalValue": "string",
  "verticalTitle": "string"
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



## Get Daily WL Products Counts
This report will generate the list of products counts for each date for the given period to display in the dashboard chart.


Endpoint: ```/api/analytics/daily-wl-products-counts```

Method: ``` GET ```

Method Name: `getDailyWLProductCounts`

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
```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response  - 200 (OK)</summary>
 
 ```json
 {
  "data": [
    {
      "xValue": "string",
      "yValue": {
        "label": "string",
        "value": 0
      }
    }
  ],
  "horizontalTitle": "string",
  "totalValue": "string",
  "verticalTitle": "string"
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



## Get Daily WL Conversion Revenue
This report will generate the list of sum of revenue for each date for the given period to display in the dashboard chart.


Endpoint: ```/api/analytics/daily-wl-conversion-revenue```

Method: ``` GET ```

Method Name: `getDailyWLConversionRevenue`

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
```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response  - 200 (OK)</summary>
 
 ```json
 {
  "data": [
    {
      "xValue": "string",
      "yValue": {
        "label": "string",
        "value": 0
      }
    }
  ],
  "horizontalTitle": "string",
  "totalValue": "string",
  "verticalTitle": "string"
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



## Get Daily WL Interaction Count
This report will generate the list of interaction count for each date for the given period to display in the dashboard chart.


Endpoint: ```/api/analytics/daily-wl-interaction-counts```

Method: ``` GET ```

Method Name: `getDailyWLInteractionCounts`

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
```
<!-- </details> -->

<!-- <details> -->
 <summary>Sample Response  - 200 (OK)</summary>
 
 ```json
 {
  "data": [
    {
      "xValue": "string",
      "yValue": {
        "label": "string",
        "value": 0
      }
    }
  ],
  "horizontalTitle": "string",
  "totalValue": "string",
  "verticalTitle": "string"
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