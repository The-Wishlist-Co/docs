
[Back to Home](index.md#welcome-to-the-wishlist)


# **Order API**
An order is a customer's request to purchase one or more products from a shop. You can create, retrieve, update, and delete orders using the Order APIs.  The Wishlist Platform uses orders to determine if a wishlist item is purchased (a "conversion").
    
### Index

***

- [**Order API**](#order-svc-api)
    <!-- - [Index](#index) -->
  - [**Representations**](#representations)
  - [**REST Endpoints**](#rest-endpoints)
    - [**Order Item Resource**](#order-item-resource)
    - [**Order Resource**](#order-resource)
      - [Create an order](#create-an-order)
      - [Update an order](#updates-an-order)
	  - [Update an order By Order Id](#updates-an-order-by-order-id)
	  - [Update an order By Order Ref](#updates-an-order-by-order-ref)
      - [Find orders](#find-orders)
      - [Search orders](#search-orders)
    - [**Order Item**](#order-item)
      - [Search for all entries (lines) for an order](#search-entries-for-an-order)
      - [Create an order entry/line](#create-an-order-entry)
      - [Update an order entry/line](#update-an-order-entry)
	  - [Update an order entry/line By Order Entry Id](#update-an-order-entry-by-order-entry-id)
	  - [Update an order entry/line By Order Entry Ref](#update-an-order-entry-by-order-entry-ref)
      - [Search an order entry](#search-an-order-entry)
      - [Delete order entry](#delete-entry)

## **Representations**

All requests or responses are JSON objects.

<!-- <details> -->
 <!-- <summary><font size="4">Expand for details</font></summary> -->

`acceptsMarketing` - boolean - Depreciated field.  Do not use.

`appliedDiscounts` - [applied discounts](Common_Fields/appliedDiscounts.md) - array - All discounds and applicable promotional offers etc are enabled here.  This contains:

`appliedTaxes` - array - All applicable taxes are enabled here. This contains:

- `amount` -   
- `amountInCent` -  
- `taxCode` - string
- `taxRate` -
- `id` - string
- `name` - string

`attributeGroups` - array - Additional required properties that are not present by default are enabled here. Refer swagger documentation for more detailed  information on internal structure.

`billingAddress` - [address](Common_Fields/address.md) 

`cancelReason` - string - Reason for order cancellation.

`cancelled`	- boolean

`cancelledAt`	

`cartId` - string - unique id of the cart that contains the order items.

`channel`	string - Enum:
[ MOBILE, OTHER, POS, WEB ]

`confirmed`	- boolean - order confirmation.

`couponDiscounts`	- number - Discount amount in the choosen currency, else in default currency will be applied.

`couponDiscountsInCent`	- number - Discount amount in the choosen currency, else in default currency will be applied.

`created_at`	

`currencyCode` - string -

`customerId` - string - customer id that is genarated when a customer is created through the [customer api.](customersvcApi.md) 

`customerLocale`	string

`customerRef`	- string - customer Ref that is provided when a customer is created through the [customer api.](customersvcApi.md) 

`deliveryStatus` - string - Enum:
[ DELIVERED, IN_PROCESS, PARTIALLY_SHIPPED, READY_TO_SHIP, SHIPPED ]

`email`	- string

`handlingCost` - number - Handling cost.

`handlingCostExTax`	- number - Handling cost excluding tax.

`handlingCostExTaxInCent`	- number - Handling cost excluding tax in cents.

`handlingCostInCent` - integer -  Handling cost in cents

`handlingCostIncTax` - number - Handling cost including tax.

`handlingCostIncTaxInCent` - integer -  Handling cost including taxin cents.

`id`- string - 

`ipAddress`	- string

`ipAddressCountry` -string

`ipAddressCountryIsocode` -	string

`itemsCancelled` -integer - Number of items that are cancelled.

`itemsReturned` - integer - Number of items that are returned.

`itemsShipped` - integer - Number of items that are shipped.

`orderLines` - array - [order Lines](Common_Fields/orderLines.md).

`orderRef` - string - Unique reference of the order.

`orderStatus`- string - Enum:
[ AWAITING_PAYMENT, AWAITING_PICKUP, AWAITING_SHIPMENT, CANCELLED, COMPLETE, CREATED, DECLINED, DISPUTED, IN_PROGRESS, MANUAL_VERIFY, OTHER, PARTIALLY_RETURNED, PARTIALLY_SHIPPED, RETURNED, SHIPPED ]

`paymentMethod`	- string - Mode of payments such as cash, credit etc.

`paymentProvider` - string 

`paymentStatus` - string - Enum:
[ AUTHORIZED, DECLINED, FRAUD_DETECTED, MANUAL_VERIFY, NOT_PAID, OTHER, PAID, PARTIALLY_PAID, PARTIALLY_REFUNDED, REFUNDED, VOIDED ]

`processedAt`	

`promotionalDiscounts` - number

`promotionalDiscountsInCent` - integer

`refundedAmount` - number

`refundedAmountInCent` - integer

`returnReason` - string 

`returned` - boolean

`returnedAt`

`shipmentMode` - [ShipmentMode](Common_Fields/shipmentMode.md)

`shipments` - [Shipment](Common_Fields/shipments.md)

`shippingAddress`	- [address](Common_Fields/address.md)

`shippingCost` - number

`shippingCostBeforeDiscount` - number

`shippingCostBeforeDiscountInCent` - integer

`shippingCostExTax` - number

`shippingCostExTaxInCent` - integer

`shippingCostInCent` - integer

`shippingCostIncTax` - number

`shippingCostIncTaxCent` -integer

`shippingState`	- string - Enum:
[ CREATED, DELIVERED, OTHER, PACKED, PICKED, READY_FOR_SHIPPING, SHIPPED ]

`taxCategoryCode`	string

`taxIncluded`	boolean

`totalAmount`	number

`totalAmountBeforeDiscount`	number

`totalAmountBeforeDiscountInCent`	integer($int64)

`totalAmountExTax`	number

`totalAmountExTaxInCent`	integer($int64)

`totalAmountInCent`	integer($int64)

`totalAmountIncTax`	number

`totalAmountIncTaxInCent`	integer($int64)

`totalDiscounts`	number

`totalDiscountsInCent`	integer($int64)

`totalItems`	integer($int32)

`updated_at`	string($date-time)

`wrappingCost`	number

`wrappingCostExTax`	number

`wrappingCostExTaxInCent`	integer($int64)

`wrappingCostInCent`	integer($int64)

`wrappingCostIncTax`	number

`wrappingCostIncTaxInCent`	integer($int64)
<!-- </details> -->

## **REST Endpoints**
***

## **Order Item Resource**

## Validate Order Entry

Endpoint: ```​/api​/v1​/orders​/entries​/validate```

Method: ```POST ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Sample Request : 

```json
{
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "basePrice": 0,
  "basePriceExTax": 0,
  "basePriceExTaxInCent": 0,
  "basePriceInCent": 0,
  "basePriceIncTax": 0,
  "basePriceIncTaxInCent": 0,
  "cancelledAt": "2022-06-27T14:38:30.765Z",
  "created_at": "2022-06-27T14:38:30.765Z",
  "entryRef": "string",
  "gtin": "string",
  "id": "string",
  "orderId": "string",
  "orderRef": "string",
  "processedAt": "2022-06-27T14:38:30.765Z",
  "productId": "string",
  "productRef": "string",
  "quantity": 0,
  "refundAmount": 0,
  "refundAmountInCent": 0,
  "returnId": 0,
  "returnedAt": "2022-06-27T14:38:30.765Z",
  "returnedQuantity": 0,
  "shippedQuantity": 0,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "updated_at": "2022-06-27T14:38:30.765Z"
}
```

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


## **Order Resource**

## Create an order

Endpoint: ```​/api​/v1​/orders​```

Method: ```POST ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Sample Request : 

```json
{
  "acceptsMarketing": true,
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "appliedTaxes": [
    {
      "amount": 0,
      "amountInCent": 0,
      "id": "string",
      "name": "string",
      "taxCode": "string",
      "taxRate": 0
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    }
  },
  "billingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "cancelReason": "string",
  "cancelled": true,
  "cancelledAt": "2022-06-27T14:39:07.843Z",
  "cartId": "string",
  "channel": "MOBILE",
  "confirmed": true,
  "couponDiscounts": 0,
  "couponDiscountsInCent": 0,
  "created_at": "2022-06-27T14:39:07.843Z",
  "currencyCode": "string",
  "customerId": "string",
  "customerLocale": "string",
  "customerRef": "string",
  "deliveryStatus": "DELIVERED",
  "email": "string",
  "handlingCost": 0,
  "handlingCostExTax": 0,
  "handlingCostExTaxInCent": 0,
  "handlingCostInCent": 0,
  "handlingCostIncTax": 0,
  "handlingCostIncTaxInCent": 0,
  "id": "string",
  "ipAddress": "string",
  "ipAddressCountry": "string",
  "ipAddressCountryIsocode": "string",
  "itemsCancelled": 0,
  "itemsReturned": 0,
  "itemsShipped": 0,
  "orderLines": [
    {
      "appliedDiscounts": [
        {
          "amount": 0,
          "amountInCent": 0,
          "couponCode": "string",
          "discountRef": "string",
          "discountType": "string",
          "headerLevel": true,
          "id": "string",
          "name": "string"
        }
      ],
      "basePrice": 0,
      "basePriceExTax": 0,
      "basePriceExTaxInCent": 0,
      "basePriceInCent": 0,
      "basePriceIncTax": 0,
      "basePriceIncTaxInCent": 0,
      "cancelledAt": "2022-06-27T14:39:07.843Z",
      "created_at": "2022-06-27T14:39:07.843Z",
      "entryRef": "string",
      "gtin": "string",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "processedAt": "2022-06-27T14:39:07.843Z",
      "productId": "string",
      "productRef": "string",
      "quantity": 0,
      "refundAmount": 0,
      "refundAmountInCent": 0,
      "returnId": 0,
      "returnedAt": "2022-06-27T14:39:07.843Z",
      "returnedQuantity": 0,
      "shippedQuantity": 0,
      "totalAmount": 0,
      "totalAmountBeforeDiscount": 0,
      "totalAmountBeforeDiscountInCent": 0,
      "totalAmountExTax": 0,
      "totalAmountInCent": 0,
      "totalAmountIncTax": 0,
      "totalAmountIncTaxInCent": 0,
      "updated_at": "2022-06-27T14:39:07.843Z"
    }
  ],
  "orderRef": "string",
  "orderStatus": "AWAITING_PAYMENT",
  "paymentMethod": "string",
  "paymentProvider": "string",
  "paymentStatus": "AUTHORIZED",
  "processedAt": "2022-06-27T14:39:07.843Z",
  "promotionalDiscounts": 0,
  "promotionalDiscountsInCent": 0,
  "refundedAmount": 0,
  "refundedAmountInCent": 0,
  "returnReason": "string",
  "returned": true,
  "returnedAt": "2022-06-27T14:39:07.843Z",
  "shipmentMode": {
    "created_at": "2022-06-27T14:39:07.843Z",
    "id": "string",
    "name": "string",
    "shipmentCost": 0,
    "shipmentCostInCent": 0,
    "updated_at": "2022-06-27T14:39:07.843Z"
  },
  "shipments": [
    {
      "created_at": "2022-06-27T14:39:07.843Z",
      "deliveryDate": "2022-06-27T14:39:07.843Z",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "shipmentLines": [
        {
          "created_at": "2022-06-27T14:39:07.843Z",
          "entryId": "string",
          "entryRef": "string",
          "id": "string",
          "orderId": "string",
          "orderRef": "string",
          "quantityShipped": "string",
          "shipmentId": "string",
          "shipmentLineRef": "string",
          "shipmentRef": "string",
          "updated_at": "2022-06-27T14:39:07.843Z"
        }
      ],
      "shipmentProvider": "string",
      "shipmentRef": "string",
      "shipmentStatus": "DELIVERED",
      "shippedDate": "2022-06-27T14:39:07.843Z",
      "trackingNumber": "string",
      "trackingUrl": "string",
      "updated_at": "2022-06-27T14:39:07.843Z"
    }
  ],
  "shippingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "shippingCost": 0,
  "shippingCostBeforeDiscount": 0,
  "shippingCostBeforeDiscountInCent": 0,
  "shippingCostExTax": 0,
  "shippingCostExTaxInCent": 0,
  "shippingCostInCent": 0,
  "shippingCostIncTax": 0,
  "shippingCostIncTaxCent": 0,
  "shippingState": "CREATED",
  "taxCategoryCode": "string",
  "taxIncluded": true,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountExTaxInCent": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "totalDiscounts": 0,
  "totalDiscountsInCent": 0,
  "totalItems": 0,
  "updated_at": "2022-06-27T14:39:07.843Z",
  "wrappingCost": 0,
  "wrappingCostExTax": 0,
  "wrappingCostExTaxInCent": 0,
  "wrappingCostInCent": 0,
  "wrappingCostIncTax": 0,
  "wrappingCostIncTaxInCent": 0
}
```

<summary>Response - 201 (created)</summary>

```json
{
  "acceptsMarketing": true,
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "appliedTaxes": [
    {
      "amount": 0,
      "amountInCent": 0,
      "id": "string",
      "name": "string",
      "taxCode": "string",
      "taxRate": 0
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    }
  },
  "billingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "cancelReason": "string",
  "cancelled": true,
  "cancelledAt": "2022-06-27T14:39:07.853Z",
  "cartId": "string",
  "channel": "MOBILE",
  "confirmed": true,
  "couponDiscounts": 0,
  "couponDiscountsInCent": 0,
  "created_at": "2022-06-27T14:39:07.853Z",
  "currencyCode": "string",
  "customerId": "string",
  "customerLocale": "string",
  "customerRef": "string",
  "deliveryStatus": "DELIVERED",
  "email": "string",
  "handlingCost": 0,
  "handlingCostExTax": 0,
  "handlingCostExTaxInCent": 0,
  "handlingCostInCent": 0,
  "handlingCostIncTax": 0,
  "handlingCostIncTaxInCent": 0,
  "id": "string",
  "ipAddress": "string",
  "ipAddressCountry": "string",
  "ipAddressCountryIsocode": "string",
  "itemsCancelled": 0,
  "itemsReturned": 0,
  "itemsShipped": 0,
  "orderLines": [
    {
      "appliedDiscounts": [
        {
          "amount": 0,
          "amountInCent": 0,
          "couponCode": "string",
          "discountRef": "string",
          "discountType": "string",
          "headerLevel": true,
          "id": "string",
          "name": "string"
        }
      ],
      "basePrice": 0,
      "basePriceExTax": 0,
      "basePriceExTaxInCent": 0,
      "basePriceInCent": 0,
      "basePriceIncTax": 0,
      "basePriceIncTaxInCent": 0,
      "cancelledAt": "2022-06-27T14:39:07.853Z",
      "created_at": "2022-06-27T14:39:07.853Z",
      "entryRef": "string",
      "gtin": "string",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "processedAt": "2022-06-27T14:39:07.853Z",
      "productId": "string",
      "productRef": "string",
      "quantity": 0,
      "refundAmount": 0,
      "refundAmountInCent": 0,
      "returnId": 0,
      "returnedAt": "2022-06-27T14:39:07.853Z",
      "returnedQuantity": 0,
      "shippedQuantity": 0,
      "totalAmount": 0,
      "totalAmountBeforeDiscount": 0,
      "totalAmountBeforeDiscountInCent": 0,
      "totalAmountExTax": 0,
      "totalAmountInCent": 0,
      "totalAmountIncTax": 0,
      "totalAmountIncTaxInCent": 0,
      "updated_at": "2022-06-27T14:39:07.853Z"
    }
  ],
  "orderRef": "string",
  "orderStatus": "AWAITING_PAYMENT",
  "paymentMethod": "string",
  "paymentProvider": "string",
  "paymentStatus": "AUTHORIZED",
  "processedAt": "2022-06-27T14:39:07.853Z",
  "promotionalDiscounts": 0,
  "promotionalDiscountsInCent": 0,
  "refundedAmount": 0,
  "refundedAmountInCent": 0,
  "returnReason": "string",
  "returned": true,
  "returnedAt": "2022-06-27T14:39:07.853Z",
  "shipmentMode": {
    "created_at": "2022-06-27T14:39:07.853Z",
    "id": "string",
    "name": "string",
    "shipmentCost": 0,
    "shipmentCostInCent": 0,
    "updated_at": "2022-06-27T14:39:07.853Z"
  },
  "shipments": [
    {
      "created_at": "2022-06-27T14:39:07.853Z",
      "deliveryDate": "2022-06-27T14:39:07.853Z",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "shipmentLines": [
        {
          "created_at": "2022-06-27T14:39:07.853Z",
          "entryId": "string",
          "entryRef": "string",
          "id": "string",
          "orderId": "string",
          "orderRef": "string",
          "quantityShipped": "string",
          "shipmentId": "string",
          "shipmentLineRef": "string",
          "shipmentRef": "string",
          "updated_at": "2022-06-27T14:39:07.853Z"
        }
      ],
      "shipmentProvider": "string",
      "shipmentRef": "string",
      "shipmentStatus": "DELIVERED",
      "shippedDate": "2022-06-27T14:39:07.853Z",
      "trackingNumber": "string",
      "trackingUrl": "string",
      "updated_at": "2022-06-27T14:39:07.853Z"
    }
  ],
  "shippingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "shippingCost": 0,
  "shippingCostBeforeDiscount": 0,
  "shippingCostBeforeDiscountInCent": 0,
  "shippingCostExTax": 0,
  "shippingCostExTaxInCent": 0,
  "shippingCostInCent": 0,
  "shippingCostIncTax": 0,
  "shippingCostIncTaxCent": 0,
  "shippingState": "CREATED",
  "taxCategoryCode": "string",
  "taxIncluded": true,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountExTaxInCent": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "totalDiscounts": 0,
  "totalDiscountsInCent": 0,
  "totalItems": 0,
  "updated_at": "2022-06-27T14:39:07.853Z",
  "wrappingCost": 0,
  "wrappingCostExTax": 0,
  "wrappingCostExTaxInCent": 0,
  "wrappingCostInCent": 0,
  "wrappingCostIncTax": 0,
  "wrappingCostIncTaxInCent": 0
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


## Update an order

Endpoint: ```​/api​/v1​/orders​```

Method: ```PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Sample Request : 

```json
{
  "acceptsMarketing": true,
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "appliedTaxes": [
    {
      "amount": 0,
      "amountInCent": 0,
      "id": "string",
      "name": "string",
      "taxCode": "string",
      "taxRate": 0
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    }
  },
  "billingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "cancelReason": "string",
  "cancelled": true,
  "cancelledAt": "2022-06-27T14:39:44.684Z",
  "cartId": "string",
  "channel": "MOBILE",
  "confirmed": true,
  "couponDiscounts": 0,
  "couponDiscountsInCent": 0,
  "created_at": "2022-06-27T14:39:44.684Z",
  "currencyCode": "string",
  "customerId": "string",
  "customerLocale": "string",
  "customerRef": "string",
  "deliveryStatus": "DELIVERED",
  "email": "string",
  "handlingCost": 0,
  "handlingCostExTax": 0,
  "handlingCostExTaxInCent": 0,
  "handlingCostInCent": 0,
  "handlingCostIncTax": 0,
  "handlingCostIncTaxInCent": 0,
  "id": "string",
  "ipAddress": "string",
  "ipAddressCountry": "string",
  "ipAddressCountryIsocode": "string",
  "itemsCancelled": 0,
  "itemsReturned": 0,
  "itemsShipped": 0,
  "orderLines": [
    {
      "appliedDiscounts": [
        {
          "amount": 0,
          "amountInCent": 0,
          "couponCode": "string",
          "discountRef": "string",
          "discountType": "string",
          "headerLevel": true,
          "id": "string",
          "name": "string"
        }
      ],
      "basePrice": 0,
      "basePriceExTax": 0,
      "basePriceExTaxInCent": 0,
      "basePriceInCent": 0,
      "basePriceIncTax": 0,
      "basePriceIncTaxInCent": 0,
      "cancelledAt": "2022-06-27T14:39:44.684Z",
      "created_at": "2022-06-27T14:39:44.684Z",
      "entryRef": "string",
      "gtin": "string",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "processedAt": "2022-06-27T14:39:44.684Z",
      "productId": "string",
      "productRef": "string",
      "quantity": 0,
      "refundAmount": 0,
      "refundAmountInCent": 0,
      "returnId": 0,
      "returnedAt": "2022-06-27T14:39:44.684Z",
      "returnedQuantity": 0,
      "shippedQuantity": 0,
      "totalAmount": 0,
      "totalAmountBeforeDiscount": 0,
      "totalAmountBeforeDiscountInCent": 0,
      "totalAmountExTax": 0,
      "totalAmountInCent": 0,
      "totalAmountIncTax": 0,
      "totalAmountIncTaxInCent": 0,
      "updated_at": "2022-06-27T14:39:44.684Z"
    }
  ],
  "orderRef": "string",
  "orderStatus": "AWAITING_PAYMENT",
  "paymentMethod": "string",
  "paymentProvider": "string",
  "paymentStatus": "AUTHORIZED",
  "processedAt": "2022-06-27T14:39:44.684Z",
  "promotionalDiscounts": 0,
  "promotionalDiscountsInCent": 0,
  "refundedAmount": 0,
  "refundedAmountInCent": 0,
  "returnReason": "string",
  "returned": true,
  "returnedAt": "2022-06-27T14:39:44.684Z",
  "shipmentMode": {
    "created_at": "2022-06-27T14:39:44.684Z",
    "id": "string",
    "name": "string",
    "shipmentCost": 0,
    "shipmentCostInCent": 0,
    "updated_at": "2022-06-27T14:39:44.684Z"
  },
  "shipments": [
    {
      "created_at": "2022-06-27T14:39:44.684Z",
      "deliveryDate": "2022-06-27T14:39:44.684Z",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "shipmentLines": [
        {
          "created_at": "2022-06-27T14:39:44.684Z",
          "entryId": "string",
          "entryRef": "string",
          "id": "string",
          "orderId": "string",
          "orderRef": "string",
          "quantityShipped": "string",
          "shipmentId": "string",
          "shipmentLineRef": "string",
          "shipmentRef": "string",
          "updated_at": "2022-06-27T14:39:44.684Z"
        }
      ],
      "shipmentProvider": "string",
      "shipmentRef": "string",
      "shipmentStatus": "DELIVERED",
      "shippedDate": "2022-06-27T14:39:44.684Z",
      "trackingNumber": "string",
      "trackingUrl": "string",
      "updated_at": "2022-06-27T14:39:44.684Z"
    }
  ],
  "shippingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "shippingCost": 0,
  "shippingCostBeforeDiscount": 0,
  "shippingCostBeforeDiscountInCent": 0,
  "shippingCostExTax": 0,
  "shippingCostExTaxInCent": 0,
  "shippingCostInCent": 0,
  "shippingCostIncTax": 0,
  "shippingCostIncTaxCent": 0,
  "shippingState": "CREATED",
  "taxCategoryCode": "string",
  "taxIncluded": true,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountExTaxInCent": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "totalDiscounts": 0,
  "totalDiscountsInCent": 0,
  "totalItems": 0,
  "updated_at": "2022-06-27T14:39:44.684Z",
  "wrappingCost": 0,
  "wrappingCostExTax": 0,
  "wrappingCostExTaxInCent": 0,
  "wrappingCostInCent": 0,
  "wrappingCostIncTax": 0,
  "wrappingCostIncTaxInCent": 0
}
```

<summary>Response - 200 (OK)</summary>

```json
{
  "acceptsMarketing": true,
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "appliedTaxes": [
    {
      "amount": 0,
      "amountInCent": 0,
      "id": "string",
      "name": "string",
      "taxCode": "string",
      "taxRate": 0
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    }
  },
  "billingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "cancelReason": "string",
  "cancelled": true,
  "cancelledAt": "2022-06-27T14:39:44.698Z",
  "cartId": "string",
  "channel": "MOBILE",
  "confirmed": true,
  "couponDiscounts": 0,
  "couponDiscountsInCent": 0,
  "created_at": "2022-06-27T14:39:44.698Z",
  "currencyCode": "string",
  "customerId": "string",
  "customerLocale": "string",
  "customerRef": "string",
  "deliveryStatus": "DELIVERED",
  "email": "string",
  "handlingCost": 0,
  "handlingCostExTax": 0,
  "handlingCostExTaxInCent": 0,
  "handlingCostInCent": 0,
  "handlingCostIncTax": 0,
  "handlingCostIncTaxInCent": 0,
  "id": "string",
  "ipAddress": "string",
  "ipAddressCountry": "string",
  "ipAddressCountryIsocode": "string",
  "itemsCancelled": 0,
  "itemsReturned": 0,
  "itemsShipped": 0,
  "orderLines": [
    {
      "appliedDiscounts": [
        {
          "amount": 0,
          "amountInCent": 0,
          "couponCode": "string",
          "discountRef": "string",
          "discountType": "string",
          "headerLevel": true,
          "id": "string",
          "name": "string"
        }
      ],
      "basePrice": 0,
      "basePriceExTax": 0,
      "basePriceExTaxInCent": 0,
      "basePriceInCent": 0,
      "basePriceIncTax": 0,
      "basePriceIncTaxInCent": 0,
      "cancelledAt": "2022-06-27T14:39:44.698Z",
      "created_at": "2022-06-27T14:39:44.698Z",
      "entryRef": "string",
      "gtin": "string",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "processedAt": "2022-06-27T14:39:44.698Z",
      "productId": "string",
      "productRef": "string",
      "quantity": 0,
      "refundAmount": 0,
      "refundAmountInCent": 0,
      "returnId": 0,
      "returnedAt": "2022-06-27T14:39:44.698Z",
      "returnedQuantity": 0,
      "shippedQuantity": 0,
      "totalAmount": 0,
      "totalAmountBeforeDiscount": 0,
      "totalAmountBeforeDiscountInCent": 0,
      "totalAmountExTax": 0,
      "totalAmountInCent": 0,
      "totalAmountIncTax": 0,
      "totalAmountIncTaxInCent": 0,
      "updated_at": "2022-06-27T14:39:44.698Z"
    }
  ],
  "orderRef": "string",
  "orderStatus": "AWAITING_PAYMENT",
  "paymentMethod": "string",
  "paymentProvider": "string",
  "paymentStatus": "AUTHORIZED",
  "processedAt": "2022-06-27T14:39:44.698Z",
  "promotionalDiscounts": 0,
  "promotionalDiscountsInCent": 0,
  "refundedAmount": 0,
  "refundedAmountInCent": 0,
  "returnReason": "string",
  "returned": true,
  "returnedAt": "2022-06-27T14:39:44.698Z",
  "shipmentMode": {
    "created_at": "2022-06-27T14:39:44.698Z",
    "id": "string",
    "name": "string",
    "shipmentCost": 0,
    "shipmentCostInCent": 0,
    "updated_at": "2022-06-27T14:39:44.698Z"
  },
  "shipments": [
    {
      "created_at": "2022-06-27T14:39:44.698Z",
      "deliveryDate": "2022-06-27T14:39:44.698Z",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "shipmentLines": [
        {
          "created_at": "2022-06-27T14:39:44.698Z",
          "entryId": "string",
          "entryRef": "string",
          "id": "string",
          "orderId": "string",
          "orderRef": "string",
          "quantityShipped": "string",
          "shipmentId": "string",
          "shipmentLineRef": "string",
          "shipmentRef": "string",
          "updated_at": "2022-06-27T14:39:44.698Z"
        }
      ],
      "shipmentProvider": "string",
      "shipmentRef": "string",
      "shipmentStatus": "DELIVERED",
      "shippedDate": "2022-06-27T14:39:44.698Z",
      "trackingNumber": "string",
      "trackingUrl": "string",
      "updated_at": "2022-06-27T14:39:44.698Z"
    }
  ],
  "shippingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "shippingCost": 0,
  "shippingCostBeforeDiscount": 0,
  "shippingCostBeforeDiscountInCent": 0,
  "shippingCostExTax": 0,
  "shippingCostExTaxInCent": 0,
  "shippingCostInCent": 0,
  "shippingCostIncTax": 0,
  "shippingCostIncTaxCent": 0,
  "shippingState": "CREATED",
  "taxCategoryCode": "string",
  "taxIncluded": true,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountExTaxInCent": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "totalDiscounts": 0,
  "totalDiscountsInCent": 0,
  "totalItems": 0,
  "updated_at": "2022-06-27T14:39:44.698Z",
  "wrappingCost": 0,
  "wrappingCostExTax": 0,
  "wrappingCostExTaxInCent": 0,
  "wrappingCostInCent": 0,
  "wrappingCostIncTax": 0,
  "wrappingCostIncTaxInCent": 0
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


## Update an order By Order Id

Endpoint: ```​/api​/v1​/orders​/id={id:.*}```

Method: ```PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable: 

```
id - Order id
```

Sample Request : 

```json
{
  "acceptsMarketing": true,
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "appliedTaxes": [
    {
      "amount": 0,
      "amountInCent": 0,
      "id": "string",
      "name": "string",
      "taxCode": "string",
      "taxRate": 0
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    }
  },
  "billingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "cancelReason": "string",
  "cancelled": true,
  "cancelledAt": "2022-06-27T14:39:44.684Z",
  "cartId": "string",
  "channel": "MOBILE",
  "confirmed": true,
  "couponDiscounts": 0,
  "couponDiscountsInCent": 0,
  "created_at": "2022-06-27T14:39:44.684Z",
  "currencyCode": "string",
  "customerId": "string",
  "customerLocale": "string",
  "customerRef": "string",
  "deliveryStatus": "DELIVERED",
  "email": "string",
  "handlingCost": 0,
  "handlingCostExTax": 0,
  "handlingCostExTaxInCent": 0,
  "handlingCostInCent": 0,
  "handlingCostIncTax": 0,
  "handlingCostIncTaxInCent": 0,  
  "ipAddress": "string",
  "ipAddressCountry": "string",
  "ipAddressCountryIsocode": "string",
  "itemsCancelled": 0,
  "itemsReturned": 0,
  "itemsShipped": 0,
  "orderLines": [
    {
      "appliedDiscounts": [
        {
          "amount": 0,
          "amountInCent": 0,
          "couponCode": "string",
          "discountRef": "string",
          "discountType": "string",
          "headerLevel": true,
          "id": "string",
          "name": "string"
        }
      ],
      "basePrice": 0,
      "basePriceExTax": 0,
      "basePriceExTaxInCent": 0,
      "basePriceInCent": 0,
      "basePriceIncTax": 0,
      "basePriceIncTaxInCent": 0,
      "cancelledAt": "2022-06-27T14:39:44.684Z",
      "created_at": "2022-06-27T14:39:44.684Z",
      "entryRef": "string",
      "gtin": "string",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "processedAt": "2022-06-27T14:39:44.684Z",
      "productId": "string",
      "productRef": "string",
      "quantity": 0,
      "refundAmount": 0,
      "refundAmountInCent": 0,
      "returnId": 0,
      "returnedAt": "2022-06-27T14:39:44.684Z",
      "returnedQuantity": 0,
      "shippedQuantity": 0,
      "totalAmount": 0,
      "totalAmountBeforeDiscount": 0,
      "totalAmountBeforeDiscountInCent": 0,
      "totalAmountExTax": 0,
      "totalAmountInCent": 0,
      "totalAmountIncTax": 0,
      "totalAmountIncTaxInCent": 0,
      "updated_at": "2022-06-27T14:39:44.684Z"
    }
  ],  
  "orderStatus": "AWAITING_PAYMENT",
  "paymentMethod": "string",
  "paymentProvider": "string",
  "paymentStatus": "AUTHORIZED",
  "processedAt": "2022-06-27T14:39:44.684Z",
  "promotionalDiscounts": 0,
  "promotionalDiscountsInCent": 0,
  "refundedAmount": 0,
  "refundedAmountInCent": 0,
  "returnReason": "string",
  "returned": true,
  "returnedAt": "2022-06-27T14:39:44.684Z",
  "shipmentMode": {
    "created_at": "2022-06-27T14:39:44.684Z",
    "id": "string",
    "name": "string",
    "shipmentCost": 0,
    "shipmentCostInCent": 0,
    "updated_at": "2022-06-27T14:39:44.684Z"
  },
  "shipments": [
    {
      "created_at": "2022-06-27T14:39:44.684Z",
      "deliveryDate": "2022-06-27T14:39:44.684Z",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "shipmentLines": [
        {
          "created_at": "2022-06-27T14:39:44.684Z",
          "entryId": "string",
          "entryRef": "string",
          "id": "string",
          "orderId": "string",
          "orderRef": "string",
          "quantityShipped": "string",
          "shipmentId": "string",
          "shipmentLineRef": "string",
          "shipmentRef": "string",
          "updated_at": "2022-06-27T14:39:44.684Z"
        }
      ],
      "shipmentProvider": "string",
      "shipmentRef": "string",
      "shipmentStatus": "DELIVERED",
      "shippedDate": "2022-06-27T14:39:44.684Z",
      "trackingNumber": "string",
      "trackingUrl": "string",
      "updated_at": "2022-06-27T14:39:44.684Z"
    }
  ],
  "shippingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "shippingCost": 0,
  "shippingCostBeforeDiscount": 0,
  "shippingCostBeforeDiscountInCent": 0,
  "shippingCostExTax": 0,
  "shippingCostExTaxInCent": 0,
  "shippingCostInCent": 0,
  "shippingCostIncTax": 0,
  "shippingCostIncTaxCent": 0,
  "shippingState": "CREATED",
  "taxCategoryCode": "string",
  "taxIncluded": true,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountExTaxInCent": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "totalDiscounts": 0,
  "totalDiscountsInCent": 0,
  "totalItems": 0,
  "updated_at": "2022-06-27T14:39:44.684Z",
  "wrappingCost": 0,
  "wrappingCostExTax": 0,
  "wrappingCostExTaxInCent": 0,
  "wrappingCostInCent": 0,
  "wrappingCostIncTax": 0,
  "wrappingCostIncTaxInCent": 0
}
```

<summary>Response - 200 (OK)</summary>

```json
{
  "acceptsMarketing": true,
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "appliedTaxes": [
    {
      "amount": 0,
      "amountInCent": 0,
      "id": "string",
      "name": "string",
      "taxCode": "string",
      "taxRate": 0
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    }
  },
  "billingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "cancelReason": "string",
  "cancelled": true,
  "cancelledAt": "2022-06-27T14:39:44.698Z",
  "cartId": "string",
  "channel": "MOBILE",
  "confirmed": true,
  "couponDiscounts": 0,
  "couponDiscountsInCent": 0,
  "created_at": "2022-06-27T14:39:44.698Z",
  "currencyCode": "string",
  "customerId": "string",
  "customerLocale": "string",
  "customerRef": "string",
  "deliveryStatus": "DELIVERED",
  "email": "string",
  "handlingCost": 0,
  "handlingCostExTax": 0,
  "handlingCostExTaxInCent": 0,
  "handlingCostInCent": 0,
  "handlingCostIncTax": 0,
  "handlingCostIncTaxInCent": 0,
  "id": "string",
  "ipAddress": "string",
  "ipAddressCountry": "string",
  "ipAddressCountryIsocode": "string",
  "itemsCancelled": 0,
  "itemsReturned": 0,
  "itemsShipped": 0,
  "orderLines": [
    {
      "appliedDiscounts": [
        {
          "amount": 0,
          "amountInCent": 0,
          "couponCode": "string",
          "discountRef": "string",
          "discountType": "string",
          "headerLevel": true,
          "id": "string",
          "name": "string"
        }
      ],
      "basePrice": 0,
      "basePriceExTax": 0,
      "basePriceExTaxInCent": 0,
      "basePriceInCent": 0,
      "basePriceIncTax": 0,
      "basePriceIncTaxInCent": 0,
      "cancelledAt": "2022-06-27T14:39:44.698Z",
      "created_at": "2022-06-27T14:39:44.698Z",
      "entryRef": "string",
      "gtin": "string",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "processedAt": "2022-06-27T14:39:44.698Z",
      "productId": "string",
      "productRef": "string",
      "quantity": 0,
      "refundAmount": 0,
      "refundAmountInCent": 0,
      "returnId": 0,
      "returnedAt": "2022-06-27T14:39:44.698Z",
      "returnedQuantity": 0,
      "shippedQuantity": 0,
      "totalAmount": 0,
      "totalAmountBeforeDiscount": 0,
      "totalAmountBeforeDiscountInCent": 0,
      "totalAmountExTax": 0,
      "totalAmountInCent": 0,
      "totalAmountIncTax": 0,
      "totalAmountIncTaxInCent": 0,
      "updated_at": "2022-06-27T14:39:44.698Z"
    }
  ],
  "orderRef": "string",
  "orderStatus": "AWAITING_PAYMENT",
  "paymentMethod": "string",
  "paymentProvider": "string",
  "paymentStatus": "AUTHORIZED",
  "processedAt": "2022-06-27T14:39:44.698Z",
  "promotionalDiscounts": 0,
  "promotionalDiscountsInCent": 0,
  "refundedAmount": 0,
  "refundedAmountInCent": 0,
  "returnReason": "string",
  "returned": true,
  "returnedAt": "2022-06-27T14:39:44.698Z",
  "shipmentMode": {
    "created_at": "2022-06-27T14:39:44.698Z",
    "id": "string",
    "name": "string",
    "shipmentCost": 0,
    "shipmentCostInCent": 0,
    "updated_at": "2022-06-27T14:39:44.698Z"
  },
  "shipments": [
    {
      "created_at": "2022-06-27T14:39:44.698Z",
      "deliveryDate": "2022-06-27T14:39:44.698Z",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "shipmentLines": [
        {
          "created_at": "2022-06-27T14:39:44.698Z",
          "entryId": "string",
          "entryRef": "string",
          "id": "string",
          "orderId": "string",
          "orderRef": "string",
          "quantityShipped": "string",
          "shipmentId": "string",
          "shipmentLineRef": "string",
          "shipmentRef": "string",
          "updated_at": "2022-06-27T14:39:44.698Z"
        }
      ],
      "shipmentProvider": "string",
      "shipmentRef": "string",
      "shipmentStatus": "DELIVERED",
      "shippedDate": "2022-06-27T14:39:44.698Z",
      "trackingNumber": "string",
      "trackingUrl": "string",
      "updated_at": "2022-06-27T14:39:44.698Z"
    }
  ],
  "shippingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "shippingCost": 0,
  "shippingCostBeforeDiscount": 0,
  "shippingCostBeforeDiscountInCent": 0,
  "shippingCostExTax": 0,
  "shippingCostExTaxInCent": 0,
  "shippingCostInCent": 0,
  "shippingCostIncTax": 0,
  "shippingCostIncTaxCent": 0,
  "shippingState": "CREATED",
  "taxCategoryCode": "string",
  "taxIncluded": true,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountExTaxInCent": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "totalDiscounts": 0,
  "totalDiscountsInCent": 0,
  "totalItems": 0,
  "updated_at": "2022-06-27T14:39:44.698Z",
  "wrappingCost": 0,
  "wrappingCostExTax": 0,
  "wrappingCostExTaxInCent": 0,
  "wrappingCostInCent": 0,
  "wrappingCostIncTax": 0,
  "wrappingCostIncTaxInCent": 0
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



## Update an order By Order Refence

Endpoint: ```​/api​/v1​/orders/ref={ref:.*}​```

Method: ```PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |


Path Variable: 

```
ref - Order Ref
```

Sample Request : 

```json
{
  "acceptsMarketing": true,
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "appliedTaxes": [
    {
      "amount": 0,
      "amountInCent": 0,
      "id": "string",
      "name": "string",
      "taxCode": "string",
      "taxRate": 0
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    }
  },
  "billingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "cancelReason": "string",
  "cancelled": true,
  "cancelledAt": "2022-06-27T14:39:44.684Z",
  "cartId": "string",
  "channel": "MOBILE",
  "confirmed": true,
  "couponDiscounts": 0,
  "couponDiscountsInCent": 0,
  "created_at": "2022-06-27T14:39:44.684Z",
  "currencyCode": "string",
  "customerId": "string",
  "customerLocale": "string",
  "customerRef": "string",
  "deliveryStatus": "DELIVERED",
  "email": "string",
  "handlingCost": 0,
  "handlingCostExTax": 0,
  "handlingCostExTaxInCent": 0,
  "handlingCostInCent": 0,
  "handlingCostIncTax": 0,
  "handlingCostIncTaxInCent": 0,  
  "ipAddress": "string",
  "ipAddressCountry": "string",
  "ipAddressCountryIsocode": "string",
  "itemsCancelled": 0,
  "itemsReturned": 0,
  "itemsShipped": 0,
  "orderLines": [
    {
      "appliedDiscounts": [
        {
          "amount": 0,
          "amountInCent": 0,
          "couponCode": "string",
          "discountRef": "string",
          "discountType": "string",
          "headerLevel": true,
          "id": "string",
          "name": "string"
        }
      ],
      "basePrice": 0,
      "basePriceExTax": 0,
      "basePriceExTaxInCent": 0,
      "basePriceInCent": 0,
      "basePriceIncTax": 0,
      "basePriceIncTaxInCent": 0,
      "cancelledAt": "2022-06-27T14:39:44.684Z",
      "created_at": "2022-06-27T14:39:44.684Z",
      "entryRef": "string",
      "gtin": "string",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "processedAt": "2022-06-27T14:39:44.684Z",
      "productId": "string",
      "productRef": "string",
      "quantity": 0,
      "refundAmount": 0,
      "refundAmountInCent": 0,
      "returnId": 0,
      "returnedAt": "2022-06-27T14:39:44.684Z",
      "returnedQuantity": 0,
      "shippedQuantity": 0,
      "totalAmount": 0,
      "totalAmountBeforeDiscount": 0,
      "totalAmountBeforeDiscountInCent": 0,
      "totalAmountExTax": 0,
      "totalAmountInCent": 0,
      "totalAmountIncTax": 0,
      "totalAmountIncTaxInCent": 0,
      "updated_at": "2022-06-27T14:39:44.684Z"
    }
  ],
  
  "orderStatus": "AWAITING_PAYMENT",
  "paymentMethod": "string",
  "paymentProvider": "string",
  "paymentStatus": "AUTHORIZED",
  "processedAt": "2022-06-27T14:39:44.684Z",
  "promotionalDiscounts": 0,
  "promotionalDiscountsInCent": 0,
  "refundedAmount": 0,
  "refundedAmountInCent": 0,
  "returnReason": "string",
  "returned": true,
  "returnedAt": "2022-06-27T14:39:44.684Z",
  "shipmentMode": {
    "created_at": "2022-06-27T14:39:44.684Z",
    "id": "string",
    "name": "string",
    "shipmentCost": 0,
    "shipmentCostInCent": 0,
    "updated_at": "2022-06-27T14:39:44.684Z"
  },
  "shipments": [
    {
      "created_at": "2022-06-27T14:39:44.684Z",
      "deliveryDate": "2022-06-27T14:39:44.684Z",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "shipmentLines": [
        {
          "created_at": "2022-06-27T14:39:44.684Z",
          "entryId": "string",
          "entryRef": "string",
          "id": "string",
          "orderId": "string",
          "orderRef": "string",
          "quantityShipped": "string",
          "shipmentId": "string",
          "shipmentLineRef": "string",
          "shipmentRef": "string",
          "updated_at": "2022-06-27T14:39:44.684Z"
        }
      ],
      "shipmentProvider": "string",
      "shipmentRef": "string",
      "shipmentStatus": "DELIVERED",
      "shippedDate": "2022-06-27T14:39:44.684Z",
      "trackingNumber": "string",
      "trackingUrl": "string",
      "updated_at": "2022-06-27T14:39:44.684Z"
    }
  ],
  "shippingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "shippingCost": 0,
  "shippingCostBeforeDiscount": 0,
  "shippingCostBeforeDiscountInCent": 0,
  "shippingCostExTax": 0,
  "shippingCostExTaxInCent": 0,
  "shippingCostInCent": 0,
  "shippingCostIncTax": 0,
  "shippingCostIncTaxCent": 0,
  "shippingState": "CREATED",
  "taxCategoryCode": "string",
  "taxIncluded": true,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountExTaxInCent": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "totalDiscounts": 0,
  "totalDiscountsInCent": 0,
  "totalItems": 0,
  "updated_at": "2022-06-27T14:39:44.684Z",
  "wrappingCost": 0,
  "wrappingCostExTax": 0,
  "wrappingCostExTaxInCent": 0,
  "wrappingCostInCent": 0,
  "wrappingCostIncTax": 0,
  "wrappingCostIncTaxInCent": 0
}
```

<summary>Response - 200 (OK)</summary>

```json
{
  "acceptsMarketing": true,
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "appliedTaxes": [
    {
      "amount": 0,
      "amountInCent": 0,
      "id": "string",
      "name": "string",
      "taxCode": "string",
      "taxRate": 0
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    }
  },
  "billingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "cancelReason": "string",
  "cancelled": true,
  "cancelledAt": "2022-06-27T14:39:44.698Z",
  "cartId": "string",
  "channel": "MOBILE",
  "confirmed": true,
  "couponDiscounts": 0,
  "couponDiscountsInCent": 0,
  "created_at": "2022-06-27T14:39:44.698Z",
  "currencyCode": "string",
  "customerId": "string",
  "customerLocale": "string",
  "customerRef": "string",
  "deliveryStatus": "DELIVERED",
  "email": "string",
  "handlingCost": 0,
  "handlingCostExTax": 0,
  "handlingCostExTaxInCent": 0,
  "handlingCostInCent": 0,
  "handlingCostIncTax": 0,
  "handlingCostIncTaxInCent": 0,
  "id": "string",
  "ipAddress": "string",
  "ipAddressCountry": "string",
  "ipAddressCountryIsocode": "string",
  "itemsCancelled": 0,
  "itemsReturned": 0,
  "itemsShipped": 0,
  "orderLines": [
    {
      "appliedDiscounts": [
        {
          "amount": 0,
          "amountInCent": 0,
          "couponCode": "string",
          "discountRef": "string",
          "discountType": "string",
          "headerLevel": true,
          "id": "string",
          "name": "string"
        }
      ],
      "basePrice": 0,
      "basePriceExTax": 0,
      "basePriceExTaxInCent": 0,
      "basePriceInCent": 0,
      "basePriceIncTax": 0,
      "basePriceIncTaxInCent": 0,
      "cancelledAt": "2022-06-27T14:39:44.698Z",
      "created_at": "2022-06-27T14:39:44.698Z",
      "entryRef": "string",
      "gtin": "string",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "processedAt": "2022-06-27T14:39:44.698Z",
      "productId": "string",
      "productRef": "string",
      "quantity": 0,
      "refundAmount": 0,
      "refundAmountInCent": 0,
      "returnId": 0,
      "returnedAt": "2022-06-27T14:39:44.698Z",
      "returnedQuantity": 0,
      "shippedQuantity": 0,
      "totalAmount": 0,
      "totalAmountBeforeDiscount": 0,
      "totalAmountBeforeDiscountInCent": 0,
      "totalAmountExTax": 0,
      "totalAmountInCent": 0,
      "totalAmountIncTax": 0,
      "totalAmountIncTaxInCent": 0,
      "updated_at": "2022-06-27T14:39:44.698Z"
    }
  ],
  "orderRef": "string",
  "orderStatus": "AWAITING_PAYMENT",
  "paymentMethod": "string",
  "paymentProvider": "string",
  "paymentStatus": "AUTHORIZED",
  "processedAt": "2022-06-27T14:39:44.698Z",
  "promotionalDiscounts": 0,
  "promotionalDiscountsInCent": 0,
  "refundedAmount": 0,
  "refundedAmountInCent": 0,
  "returnReason": "string",
  "returned": true,
  "returnedAt": "2022-06-27T14:39:44.698Z",
  "shipmentMode": {
    "created_at": "2022-06-27T14:39:44.698Z",
    "id": "string",
    "name": "string",
    "shipmentCost": 0,
    "shipmentCostInCent": 0,
    "updated_at": "2022-06-27T14:39:44.698Z"
  },
  "shipments": [
    {
      "created_at": "2022-06-27T14:39:44.698Z",
      "deliveryDate": "2022-06-27T14:39:44.698Z",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "shipmentLines": [
        {
          "created_at": "2022-06-27T14:39:44.698Z",
          "entryId": "string",
          "entryRef": "string",
          "id": "string",
          "orderId": "string",
          "orderRef": "string",
          "quantityShipped": "string",
          "shipmentId": "string",
          "shipmentLineRef": "string",
          "shipmentRef": "string",
          "updated_at": "2022-06-27T14:39:44.698Z"
        }
      ],
      "shipmentProvider": "string",
      "shipmentRef": "string",
      "shipmentStatus": "DELIVERED",
      "shippedDate": "2022-06-27T14:39:44.698Z",
      "trackingNumber": "string",
      "trackingUrl": "string",
      "updated_at": "2022-06-27T14:39:44.698Z"
    }
  ],
  "shippingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "shippingCost": 0,
  "shippingCostBeforeDiscount": 0,
  "shippingCostBeforeDiscountInCent": 0,
  "shippingCostExTax": 0,
  "shippingCostExTaxInCent": 0,
  "shippingCostInCent": 0,
  "shippingCostIncTax": 0,
  "shippingCostIncTaxCent": 0,
  "shippingState": "CREATED",
  "taxCategoryCode": "string",
  "taxIncluded": true,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountExTaxInCent": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "totalDiscounts": 0,
  "totalDiscountsInCent": 0,
  "totalItems": 0,
  "updated_at": "2022-06-27T14:39:44.698Z",
  "wrappingCost": 0,
  "wrappingCostExTax": 0,
  "wrappingCostExTaxInCent": 0,
  "wrappingCostInCent": 0,
  "wrappingCostIncTax": 0,
  "wrappingCostIncTaxInCent": 0
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


## Find orders

Endpoint: ```​/api​/v1​/orders```

Method: ```GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Query Params: 

```
orderId - Order Id , orderRef - Order Ref
```

<summary>Response - 200 (OK)</summary>

```json
{
  "acceptsMarketing": true,
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "appliedTaxes": [
    {
      "amount": 0,
      "amountInCent": 0,
      "id": "string",
      "name": "string",
      "taxCode": "string",
      "taxRate": 0
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    }
  },
  "billingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "cancelReason": "string",
  "cancelled": true,
  "cancelledAt": "2022-06-27T14:40:29.034Z",
  "cartId": "string",
  "channel": "MOBILE",
  "confirmed": true,
  "couponDiscounts": 0,
  "couponDiscountsInCent": 0,
  "created_at": "2022-06-27T14:40:29.034Z",
  "currencyCode": "string",
  "customerId": "string",
  "customerLocale": "string",
  "customerRef": "string",
  "deliveryStatus": "DELIVERED",
  "email": "string",
  "handlingCost": 0,
  "handlingCostExTax": 0,
  "handlingCostExTaxInCent": 0,
  "handlingCostInCent": 0,
  "handlingCostIncTax": 0,
  "handlingCostIncTaxInCent": 0,
  "id": "string",
  "ipAddress": "string",
  "ipAddressCountry": "string",
  "ipAddressCountryIsocode": "string",
  "itemsCancelled": 0,
  "itemsReturned": 0,
  "itemsShipped": 0,
  "orderLines": [
    {
      "appliedDiscounts": [
        {
          "amount": 0,
          "amountInCent": 0,
          "couponCode": "string",
          "discountRef": "string",
          "discountType": "string",
          "headerLevel": true,
          "id": "string",
          "name": "string"
        }
      ],
      "basePrice": 0,
      "basePriceExTax": 0,
      "basePriceExTaxInCent": 0,
      "basePriceInCent": 0,
      "basePriceIncTax": 0,
      "basePriceIncTaxInCent": 0,
      "cancelledAt": "2022-06-27T14:40:29.034Z",
      "created_at": "2022-06-27T14:40:29.034Z",
      "entryRef": "string",
      "gtin": "string",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "processedAt": "2022-06-27T14:40:29.034Z",
      "productId": "string",
      "productRef": "string",
      "quantity": 0,
      "refundAmount": 0,
      "refundAmountInCent": 0,
      "returnId": 0,
      "returnedAt": "2022-06-27T14:40:29.034Z",
      "returnedQuantity": 0,
      "shippedQuantity": 0,
      "totalAmount": 0,
      "totalAmountBeforeDiscount": 0,
      "totalAmountBeforeDiscountInCent": 0,
      "totalAmountExTax": 0,
      "totalAmountInCent": 0,
      "totalAmountIncTax": 0,
      "totalAmountIncTaxInCent": 0,
      "updated_at": "2022-06-27T14:40:29.034Z"
    }
  ],
  "orderRef": "string",
  "orderStatus": "AWAITING_PAYMENT",
  "paymentMethod": "string",
  "paymentProvider": "string",
  "paymentStatus": "AUTHORIZED",
  "processedAt": "2022-06-27T14:40:29.034Z",
  "promotionalDiscounts": 0,
  "promotionalDiscountsInCent": 0,
  "refundedAmount": 0,
  "refundedAmountInCent": 0,
  "returnReason": "string",
  "returned": true,
  "returnedAt": "2022-06-27T14:40:29.034Z",
  "shipmentMode": {
    "created_at": "2022-06-27T14:40:29.034Z",
    "id": "string",
    "name": "string",
    "shipmentCost": 0,
    "shipmentCostInCent": 0,
    "updated_at": "2022-06-27T14:40:29.034Z"
  },
  "shipments": [
    {
      "created_at": "2022-06-27T14:40:29.034Z",
      "deliveryDate": "2022-06-27T14:40:29.034Z",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "shipmentLines": [
        {
          "created_at": "2022-06-27T14:40:29.034Z",
          "entryId": "string",
          "entryRef": "string",
          "id": "string",
          "orderId": "string",
          "orderRef": "string",
          "quantityShipped": "string",
          "shipmentId": "string",
          "shipmentLineRef": "string",
          "shipmentRef": "string",
          "updated_at": "2022-06-27T14:40:29.034Z"
        }
      ],
      "shipmentProvider": "string",
      "shipmentRef": "string",
      "shipmentStatus": "DELIVERED",
      "shippedDate": "2022-06-27T14:40:29.034Z",
      "trackingNumber": "string",
      "trackingUrl": "string",
      "updated_at": "2022-06-27T14:40:29.034Z"
    }
  ],
  "shippingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "shippingCost": 0,
  "shippingCostBeforeDiscount": 0,
  "shippingCostBeforeDiscountInCent": 0,
  "shippingCostExTax": 0,
  "shippingCostExTaxInCent": 0,
  "shippingCostInCent": 0,
  "shippingCostIncTax": 0,
  "shippingCostIncTaxCent": 0,
  "shippingState": "CREATED",
  "taxCategoryCode": "string",
  "taxIncluded": true,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountExTaxInCent": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "totalDiscounts": 0,
  "totalDiscountsInCent": 0,
  "totalItems": 0,
  "updated_at": "2022-06-27T14:40:29.034Z",
  "wrappingCost": 0,
  "wrappingCostExTax": 0,
  "wrappingCostExTaxInCent": 0,
  "wrappingCostInCent": 0,
  "wrappingCostIncTax": 0,
  "wrappingCostIncTaxInCent": 0
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


## Search orders

Endpoint: ```​​/api​/v1​/orders​/search```

Method: ```GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Query Params: 

```
customerId - customer ID , customerRef - Customer ref , email - email , orderId - Order Id , orderRef - Order Ref
```

<summary>Response - 200 (OK)</summary>

```json
{
  "acceptsMarketing": true,
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "appliedTaxes": [
    {
      "amount": 0,
      "amountInCent": 0,
      "id": "string",
      "name": "string",
      "taxCode": "string",
      "taxRate": 0
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    }
  },
  "billingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "cancelReason": "string",
  "cancelled": true,
  "cancelledAt": "2022-06-27T14:41:31.941Z",
  "cartId": "string",
  "channel": "MOBILE",
  "confirmed": true,
  "couponDiscounts": 0,
  "couponDiscountsInCent": 0,
  "created_at": "2022-06-27T14:41:31.941Z",
  "currencyCode": "string",
  "customerId": "string",
  "customerLocale": "string",
  "customerRef": "string",
  "deliveryStatus": "DELIVERED",
  "email": "string",
  "handlingCost": 0,
  "handlingCostExTax": 0,
  "handlingCostExTaxInCent": 0,
  "handlingCostInCent": 0,
  "handlingCostIncTax": 0,
  "handlingCostIncTaxInCent": 0,
  "id": "string",
  "ipAddress": "string",
  "ipAddressCountry": "string",
  "ipAddressCountryIsocode": "string",
  "itemsCancelled": 0,
  "itemsReturned": 0,
  "itemsShipped": 0,
  "orderLines": [
    {
      "appliedDiscounts": [
        {
          "amount": 0,
          "amountInCent": 0,
          "couponCode": "string",
          "discountRef": "string",
          "discountType": "string",
          "headerLevel": true,
          "id": "string",
          "name": "string"
        }
      ],
      "basePrice": 0,
      "basePriceExTax": 0,
      "basePriceExTaxInCent": 0,
      "basePriceInCent": 0,
      "basePriceIncTax": 0,
      "basePriceIncTaxInCent": 0,
      "cancelledAt": "2022-06-27T14:41:31.941Z",
      "created_at": "2022-06-27T14:41:31.941Z",
      "entryRef": "string",
      "gtin": "string",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "processedAt": "2022-06-27T14:41:31.941Z",
      "productId": "string",
      "productRef": "string",
      "quantity": 0,
      "refundAmount": 0,
      "refundAmountInCent": 0,
      "returnId": 0,
      "returnedAt": "2022-06-27T14:41:31.941Z",
      "returnedQuantity": 0,
      "shippedQuantity": 0,
      "totalAmount": 0,
      "totalAmountBeforeDiscount": 0,
      "totalAmountBeforeDiscountInCent": 0,
      "totalAmountExTax": 0,
      "totalAmountInCent": 0,
      "totalAmountIncTax": 0,
      "totalAmountIncTaxInCent": 0,
      "updated_at": "2022-06-27T14:41:31.941Z"
    }
  ],
  "orderRef": "string",
  "orderStatus": "AWAITING_PAYMENT",
  "paymentMethod": "string",
  "paymentProvider": "string",
  "paymentStatus": "AUTHORIZED",
  "processedAt": "2022-06-27T14:41:31.941Z",
  "promotionalDiscounts": 0,
  "promotionalDiscountsInCent": 0,
  "refundedAmount": 0,
  "refundedAmountInCent": 0,
  "returnReason": "string",
  "returned": true,
  "returnedAt": "2022-06-27T14:41:31.941Z",
  "shipmentMode": {
    "created_at": "2022-06-27T14:41:31.941Z",
    "id": "string",
    "name": "string",
    "shipmentCost": 0,
    "shipmentCostInCent": 0,
    "updated_at": "2022-06-27T14:41:31.941Z"
  },
  "shipments": [
    {
      "created_at": "2022-06-27T14:41:31.941Z",
      "deliveryDate": "2022-06-27T14:41:31.941Z",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "shipmentLines": [
        {
          "created_at": "2022-06-27T14:41:31.941Z",
          "entryId": "string",
          "entryRef": "string",
          "id": "string",
          "orderId": "string",
          "orderRef": "string",
          "quantityShipped": "string",
          "shipmentId": "string",
          "shipmentLineRef": "string",
          "shipmentRef": "string",
          "updated_at": "2022-06-27T14:41:31.941Z"
        }
      ],
      "shipmentProvider": "string",
      "shipmentRef": "string",
      "shipmentStatus": "DELIVERED",
      "shippedDate": "2022-06-27T14:41:31.941Z",
      "trackingNumber": "string",
      "trackingUrl": "string",
      "updated_at": "2022-06-27T14:41:31.941Z"
    }
  ],
  "shippingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "shippingCost": 0,
  "shippingCostBeforeDiscount": 0,
  "shippingCostBeforeDiscountInCent": 0,
  "shippingCostExTax": 0,
  "shippingCostExTaxInCent": 0,
  "shippingCostInCent": 0,
  "shippingCostIncTax": 0,
  "shippingCostIncTaxCent": 0,
  "shippingState": "CREATED",
  "taxCategoryCode": "string",
  "taxIncluded": true,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountExTaxInCent": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "totalDiscounts": 0,
  "totalDiscountsInCent": 0,
  "totalItems": 0,
  "updated_at": "2022-06-27T14:41:31.941Z",
  "wrappingCost": 0,
  "wrappingCostExTax": 0,
  "wrappingCostExTaxInCent": 0,
  "wrappingCostInCent": 0,
  "wrappingCostIncTax": 0,
  "wrappingCostIncTaxInCent": 0
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

## Validate Order

Endpoint: ```​​/api​/v1​/orders​/validate```

Method: ```POST ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Sample Request : 

```json
{
  "acceptsMarketing": true,
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "appliedTaxes": [
    {
      "amount": 0,
      "amountInCent": 0,
      "id": "string",
      "name": "string",
      "taxCode": "string",
      "taxRate": 0
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    }
  },
  "billingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "cancelReason": "string",
  "cancelled": true,
  "cancelledAt": "2022-06-27T14:42:46.663Z",
  "cartId": "string",
  "channel": "MOBILE",
  "confirmed": true,
  "couponDiscounts": 0,
  "couponDiscountsInCent": 0,
  "created_at": "2022-06-27T14:42:46.663Z",
  "currencyCode": "string",
  "customerId": "string",
  "customerLocale": "string",
  "customerRef": "string",
  "deliveryStatus": "DELIVERED",
  "email": "string",
  "handlingCost": 0,
  "handlingCostExTax": 0,
  "handlingCostExTaxInCent": 0,
  "handlingCostInCent": 0,
  "handlingCostIncTax": 0,
  "handlingCostIncTaxInCent": 0,
  "id": "string",
  "ipAddress": "string",
  "ipAddressCountry": "string",
  "ipAddressCountryIsocode": "string",
  "itemsCancelled": 0,
  "itemsReturned": 0,
  "itemsShipped": 0,
  "orderLines": [
    {
      "appliedDiscounts": [
        {
          "amount": 0,
          "amountInCent": 0,
          "couponCode": "string",
          "discountRef": "string",
          "discountType": "string",
          "headerLevel": true,
          "id": "string",
          "name": "string"
        }
      ],
      "basePrice": 0,
      "basePriceExTax": 0,
      "basePriceExTaxInCent": 0,
      "basePriceInCent": 0,
      "basePriceIncTax": 0,
      "basePriceIncTaxInCent": 0,
      "cancelledAt": "2022-06-27T14:42:46.664Z",
      "created_at": "2022-06-27T14:42:46.664Z",
      "entryRef": "string",
      "gtin": "string",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "processedAt": "2022-06-27T14:42:46.664Z",
      "productId": "string",
      "productRef": "string",
      "quantity": 0,
      "refundAmount": 0,
      "refundAmountInCent": 0,
      "returnId": 0,
      "returnedAt": "2022-06-27T14:42:46.664Z",
      "returnedQuantity": 0,
      "shippedQuantity": 0,
      "totalAmount": 0,
      "totalAmountBeforeDiscount": 0,
      "totalAmountBeforeDiscountInCent": 0,
      "totalAmountExTax": 0,
      "totalAmountInCent": 0,
      "totalAmountIncTax": 0,
      "totalAmountIncTaxInCent": 0,
      "updated_at": "2022-06-27T14:42:46.664Z"
    }
  ],
  "orderRef": "string",
  "orderStatus": "AWAITING_PAYMENT",
  "paymentMethod": "string",
  "paymentProvider": "string",
  "paymentStatus": "AUTHORIZED",
  "processedAt": "2022-06-27T14:42:46.664Z",
  "promotionalDiscounts": 0,
  "promotionalDiscountsInCent": 0,
  "refundedAmount": 0,
  "refundedAmountInCent": 0,
  "returnReason": "string",
  "returned": true,
  "returnedAt": "2022-06-27T14:42:46.664Z",
  "shipmentMode": {
    "created_at": "2022-06-27T14:42:46.664Z",
    "id": "string",
    "name": "string",
    "shipmentCost": 0,
    "shipmentCostInCent": 0,
    "updated_at": "2022-06-27T14:42:46.664Z"
  },
  "shipments": [
    {
      "created_at": "2022-06-27T14:42:46.664Z",
      "deliveryDate": "2022-06-27T14:42:46.664Z",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "shipmentLines": [
        {
          "created_at": "2022-06-27T14:42:46.664Z",
          "entryId": "string",
          "entryRef": "string",
          "id": "string",
          "orderId": "string",
          "orderRef": "string",
          "quantityShipped": "string",
          "shipmentId": "string",
          "shipmentLineRef": "string",
          "shipmentRef": "string",
          "updated_at": "2022-06-27T14:42:46.664Z"
        }
      ],
      "shipmentProvider": "string",
      "shipmentRef": "string",
      "shipmentStatus": "DELIVERED",
      "shippedDate": "2022-06-27T14:42:46.664Z",
      "trackingNumber": "string",
      "trackingUrl": "string",
      "updated_at": "2022-06-27T14:42:46.664Z"
    }
  ],
  "shippingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "shippingCost": 0,
  "shippingCostBeforeDiscount": 0,
  "shippingCostBeforeDiscountInCent": 0,
  "shippingCostExTax": 0,
  "shippingCostExTaxInCent": 0,
  "shippingCostInCent": 0,
  "shippingCostIncTax": 0,
  "shippingCostIncTaxCent": 0,
  "shippingState": "CREATED",
  "taxCategoryCode": "string",
  "taxIncluded": true,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountExTaxInCent": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "totalDiscounts": 0,
  "totalDiscountsInCent": 0,
  "totalItems": 0,
  "updated_at": "2022-06-27T14:42:46.664Z",
  "wrappingCost": 0,
  "wrappingCostExTax": 0,
  "wrappingCostExTaxInCent": 0,
  "wrappingCostInCent": 0,
  "wrappingCostIncTax": 0,
  "wrappingCostIncTaxInCent": 0
}
```

<summary>Response - 200 (Validated)</summary>

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


## **Order Item**

## Search entries for an order
Endpoint: ```​​/api​/v1​/orders​/entries```

Method: ```GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Query Params: 

```
orderId - Order Id , orderRef - Order Ref
```


<summary>Response - 200 (OK)</summary>

```json
{
  "acceptsMarketing": true,
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "appliedTaxes": [
    {
      "amount": 0,
      "amountInCent": 0,
      "id": "string",
      "name": "string",
      "taxCode": "string",
      "taxRate": 0
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    }
  },
  "billingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "cancelReason": "string",
  "cancelled": true,
  "cancelledAt": "2022-06-27T14:43:45.092Z",
  "cartId": "string",
  "channel": "MOBILE",
  "confirmed": true,
  "couponDiscounts": 0,
  "couponDiscountsInCent": 0,
  "created_at": "2022-06-27T14:43:45.092Z",
  "currencyCode": "string",
  "customerId": "string",
  "customerLocale": "string",
  "customerRef": "string",
  "deliveryStatus": "DELIVERED",
  "email": "string",
  "handlingCost": 0,
  "handlingCostExTax": 0,
  "handlingCostExTaxInCent": 0,
  "handlingCostInCent": 0,
  "handlingCostIncTax": 0,
  "handlingCostIncTaxInCent": 0,
  "id": "string",
  "ipAddress": "string",
  "ipAddressCountry": "string",
  "ipAddressCountryIsocode": "string",
  "itemsCancelled": 0,
  "itemsReturned": 0,
  "itemsShipped": 0,
  "orderLines": [
    {
      "appliedDiscounts": [
        {
          "amount": 0,
          "amountInCent": 0,
          "couponCode": "string",
          "discountRef": "string",
          "discountType": "string",
          "headerLevel": true,
          "id": "string",
          "name": "string"
        }
      ],
      "basePrice": 0,
      "basePriceExTax": 0,
      "basePriceExTaxInCent": 0,
      "basePriceInCent": 0,
      "basePriceIncTax": 0,
      "basePriceIncTaxInCent": 0,
      "cancelledAt": "2022-06-27T14:43:45.092Z",
      "created_at": "2022-06-27T14:43:45.092Z",
      "entryRef": "string",
      "gtin": "string",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "processedAt": "2022-06-27T14:43:45.092Z",
      "productId": "string",
      "productRef": "string",
      "quantity": 0,
      "refundAmount": 0,
      "refundAmountInCent": 0,
      "returnId": 0,
      "returnedAt": "2022-06-27T14:43:45.092Z",
      "returnedQuantity": 0,
      "shippedQuantity": 0,
      "totalAmount": 0,
      "totalAmountBeforeDiscount": 0,
      "totalAmountBeforeDiscountInCent": 0,
      "totalAmountExTax": 0,
      "totalAmountInCent": 0,
      "totalAmountIncTax": 0,
      "totalAmountIncTaxInCent": 0,
      "updated_at": "2022-06-27T14:43:45.092Z"
    }
  ],
  "orderRef": "string",
  "orderStatus": "AWAITING_PAYMENT",
  "paymentMethod": "string",
  "paymentProvider": "string",
  "paymentStatus": "AUTHORIZED",
  "processedAt": "2022-06-27T14:43:45.092Z",
  "promotionalDiscounts": 0,
  "promotionalDiscountsInCent": 0,
  "refundedAmount": 0,
  "refundedAmountInCent": 0,
  "returnReason": "string",
  "returned": true,
  "returnedAt": "2022-06-27T14:43:45.092Z",
  "shipmentMode": {
    "created_at": "2022-06-27T14:43:45.092Z",
    "id": "string",
    "name": "string",
    "shipmentCost": 0,
    "shipmentCostInCent": 0,
    "updated_at": "2022-06-27T14:43:45.092Z"
  },
  "shipments": [
    {
      "created_at": "2022-06-27T14:43:45.092Z",
      "deliveryDate": "2022-06-27T14:43:45.092Z",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "shipmentLines": [
        {
          "created_at": "2022-06-27T14:43:45.092Z",
          "entryId": "string",
          "entryRef": "string",
          "id": "string",
          "orderId": "string",
          "orderRef": "string",
          "quantityShipped": "string",
          "shipmentId": "string",
          "shipmentLineRef": "string",
          "shipmentRef": "string",
          "updated_at": "2022-06-27T14:43:45.092Z"
        }
      ],
      "shipmentProvider": "string",
      "shipmentRef": "string",
      "shipmentStatus": "DELIVERED",
      "shippedDate": "2022-06-27T14:43:45.092Z",
      "trackingNumber": "string",
      "trackingUrl": "string",
      "updated_at": "2022-06-27T14:43:45.092Z"
    }
  ],
  "shippingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "shippingCost": 0,
  "shippingCostBeforeDiscount": 0,
  "shippingCostBeforeDiscountInCent": 0,
  "shippingCostExTax": 0,
  "shippingCostExTaxInCent": 0,
  "shippingCostInCent": 0,
  "shippingCostIncTax": 0,
  "shippingCostIncTaxCent": 0,
  "shippingState": "CREATED",
  "taxCategoryCode": "string",
  "taxIncluded": true,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountExTaxInCent": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "totalDiscounts": 0,
  "totalDiscountsInCent": 0,
  "totalItems": 0,
  "updated_at": "2022-06-27T14:43:45.092Z",
  "wrappingCost": 0,
  "wrappingCostExTax": 0,
  "wrappingCostExTaxInCent": 0,
  "wrappingCostInCent": 0,
  "wrappingCostIncTax": 0,
  "wrappingCostIncTaxInCent": 0
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


## Create an order entry
Endpoint: ```​​/api​/v1​/orders​/entries```

Method: ```POST ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Sample Request : 

```json
{
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "basePrice": 0,
  "basePriceExTax": 0,
  "basePriceExTaxInCent": 0,
  "basePriceInCent": 0,
  "basePriceIncTax": 0,
  "basePriceIncTaxInCent": 0,
  "cancelledAt": "2022-06-27T14:44:43.995Z",
  "created_at": "2022-06-27T14:44:43.995Z",
  "entryRef": "string",
  "gtin": "string",
  "id": "string",
  "orderId": "string",
  "orderRef": "string",
  "processedAt": "2022-06-27T14:44:43.995Z",
  "productId": "string",
  "productRef": "string",
  "quantity": 0,
  "refundAmount": 0,
  "refundAmountInCent": 0,
  "returnId": 0,
  "returnedAt": "2022-06-27T14:44:43.995Z",
  "returnedQuantity": 0,
  "shippedQuantity": 0,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "updated_at": "2022-06-27T14:44:43.995Z"
}
```

<summary>Response - 201 (created)</summary>

```json
{
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "basePrice": 0,
  "basePriceExTax": 0,
  "basePriceExTaxInCent": 0,
  "basePriceInCent": 0,
  "basePriceIncTax": 0,
  "basePriceIncTaxInCent": 0,
  "cancelledAt": "2022-06-27T14:44:44.020Z",
  "created_at": "2022-06-27T14:44:44.020Z",
  "entryRef": "string",
  "gtin": "string",
  "id": "string",
  "orderId": "string",
  "orderRef": "string",
  "processedAt": "2022-06-27T14:44:44.020Z",
  "productId": "string",
  "productRef": "string",
  "quantity": 0,
  "refundAmount": 0,
  "refundAmountInCent": 0,
  "returnId": 0,
  "returnedAt": "2022-06-27T14:44:44.020Z",
  "returnedQuantity": 0,
  "shippedQuantity": 0,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "updated_at": "2022-06-27T14:44:44.020Z"
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


## Update an order entry (order line)
Endpoint: ```​​/api​/v1​/orders​/entries```

Method: ```PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Sample Request : 

```json
{
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "basePrice": 0,
  "basePriceExTax": 0,
  "basePriceExTaxInCent": 0,
  "basePriceInCent": 0,
  "basePriceIncTax": 0,
  "basePriceIncTaxInCent": 0,
  "cancelledAt": "2022-06-27T14:45:09.327Z",
  "created_at": "2022-06-27T14:45:09.327Z",
  "entryRef": "string",
  "gtin": "string",
  "id": "string",
  "orderId": "string",
  "orderRef": "string",
  "processedAt": "2022-06-27T14:45:09.327Z",
  "productId": "string",
  "productRef": "string",
  "quantity": 0,
  "refundAmount": 0,
  "refundAmountInCent": 0,
  "returnId": 0,
  "returnedAt": "2022-06-27T14:45:09.327Z",
  "returnedQuantity": 0,
  "shippedQuantity": 0,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "updated_at": "2022-06-27T14:45:09.327Z"
}
```

<summary>Response - 200 (OK)</summary>

```json
{
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "basePrice": 0,
  "basePriceExTax": 0,
  "basePriceExTaxInCent": 0,
  "basePriceInCent": 0,
  "basePriceIncTax": 0,
  "basePriceIncTaxInCent": 0,
  "cancelledAt": "2022-06-27T14:45:09.367Z",
  "created_at": "2022-06-27T14:45:09.367Z",
  "entryRef": "string",
  "gtin": "string",
  "id": "string",
  "orderId": "string",
  "orderRef": "string",
  "processedAt": "2022-06-27T14:45:09.367Z",
  "productId": "string",
  "productRef": "string",
  "quantity": 0,
  "refundAmount": 0,
  "refundAmountInCent": 0,
  "returnId": 0,
  "returnedAt": "2022-06-27T14:45:09.367Z",
  "returnedQuantity": 0,
  "shippedQuantity": 0,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "updated_at": "2022-06-27T14:45:09.367Z"
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


## Update an order entry/line By Order Entry Id

Endpoint: ```​​/api​/v1​/orders​/entries/id={id:.*}```

Method: ```PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable: 

``` 
id - Order Entry id 
```

Sample Request : 

```json
{
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "basePrice": 0,
  "basePriceExTax": 0,
  "basePriceExTaxInCent": 0,
  "basePriceInCent": 0,
  "basePriceIncTax": 0,
  "basePriceIncTaxInCent": 0,
  "cancelledAt": "2022-06-27T14:45:09.327Z",
  "created_at": "2022-06-27T14:45:09.327Z",  
  "gtin": "string",  
  "orderId": "string",
  "orderRef": "string",
  "processedAt": "2022-06-27T14:45:09.327Z",
  "productId": "string",
  "productRef": "string",
  "quantity": 0,
  "refundAmount": 0,
  "refundAmountInCent": 0,
  "returnId": 0,
  "returnedAt": "2022-06-27T14:45:09.327Z",
  "returnedQuantity": 0,
  "shippedQuantity": 0,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "updated_at": "2022-06-27T14:45:09.327Z"
}
```

<summary>Response - 200 (OK)</summary>

```json
{
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "basePrice": 0,
  "basePriceExTax": 0,
  "basePriceExTaxInCent": 0,
  "basePriceInCent": 0,
  "basePriceIncTax": 0,
  "basePriceIncTaxInCent": 0,
  "cancelledAt": "2022-06-27T14:45:09.367Z",
  "created_at": "2022-06-27T14:45:09.367Z",
  "entryRef": "string",
  "gtin": "string",
  "id": "string",
  "orderId": "string",
  "orderRef": "string",
  "processedAt": "2022-06-27T14:45:09.367Z",
  "productId": "string",
  "productRef": "string",
  "quantity": 0,
  "refundAmount": 0,
  "refundAmountInCent": 0,
  "returnId": 0,
  "returnedAt": "2022-06-27T14:45:09.367Z",
  "returnedQuantity": 0,
  "shippedQuantity": 0,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "updated_at": "2022-06-27T14:45:09.367Z"
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


## Update an order entry/line by Order Entry Ref

Endpoint: ```​​/api​/v1​/orders​/entries/{orderref}/ref={ref:.*}```

Method: ```PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable: 

```
orderref - Order ref , ref - Order Entry Ref 
```

Sample Request : 

```json
{
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "basePrice": 0,
  "basePriceExTax": 0,
  "basePriceExTaxInCent": 0,
  "basePriceInCent": 0,
  "basePriceIncTax": 0,
  "basePriceIncTaxInCent": 0,
  "cancelledAt": "2022-06-27T14:45:09.327Z",
  "created_at": "2022-06-27T14:45:09.327Z",  
  "gtin": "string",  
  "orderId": "string",
  "orderRef": "string",
  "processedAt": "2022-06-27T14:45:09.327Z",
  "productId": "string",
  "productRef": "string",
  "quantity": 0,
  "refundAmount": 0,
  "refundAmountInCent": 0,
  "returnId": 0,
  "returnedAt": "2022-06-27T14:45:09.327Z",
  "returnedQuantity": 0,
  "shippedQuantity": 0,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "updated_at": "2022-06-27T14:45:09.327Z"
}
```

<summary>Response - 200 (OK)</summary>

```json
{
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "basePrice": 0,
  "basePriceExTax": 0,
  "basePriceExTaxInCent": 0,
  "basePriceInCent": 0,
  "basePriceIncTax": 0,
  "basePriceIncTaxInCent": 0,
  "cancelledAt": "2022-06-27T14:45:09.367Z",
  "created_at": "2022-06-27T14:45:09.367Z",
  "entryRef": "string",
  "gtin": "string",
  "id": "string",
  "orderId": "string",
  "orderRef": "string",
  "processedAt": "2022-06-27T14:45:09.367Z",
  "productId": "string",
  "productRef": "string",
  "quantity": 0,
  "refundAmount": 0,
  "refundAmountInCent": 0,
  "returnId": 0,
  "returnedAt": "2022-06-27T14:45:09.367Z",
  "returnedQuantity": 0,
  "shippedQuantity": 0,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "updated_at": "2022-06-27T14:45:09.367Z"
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


## Search an order entry/line

Endpoint: ```​​/api​/v1​/orders​/entry```

Method: ```GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Query Params : 

```
entryId - Entry ID , entryRef - Entry Ref
```

<summary>Response - 200 (OK)</summary>

```json
{
  "acceptsMarketing": true,
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "appliedTaxes": [
    {
      "amount": 0,
      "amountInCent": 0,
      "id": "string",
      "name": "string",
      "taxCode": "string",
      "taxRate": 0
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    }
  },
  "billingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "cancelReason": "string",
  "cancelled": true,
  "cancelledAt": "2022-06-27T14:45:40.353Z",
  "cartId": "string",
  "channel": "MOBILE",
  "confirmed": true,
  "couponDiscounts": 0,
  "couponDiscountsInCent": 0,
  "created_at": "2022-06-27T14:45:40.353Z",
  "currencyCode": "string",
  "customerId": "string",
  "customerLocale": "string",
  "customerRef": "string",
  "deliveryStatus": "DELIVERED",
  "email": "string",
  "handlingCost": 0,
  "handlingCostExTax": 0,
  "handlingCostExTaxInCent": 0,
  "handlingCostInCent": 0,
  "handlingCostIncTax": 0,
  "handlingCostIncTaxInCent": 0,
  "id": "string",
  "ipAddress": "string",
  "ipAddressCountry": "string",
  "ipAddressCountryIsocode": "string",
  "itemsCancelled": 0,
  "itemsReturned": 0,
  "itemsShipped": 0,
  "orderLines": [
    {
      "appliedDiscounts": [
        {
          "amount": 0,
          "amountInCent": 0,
          "couponCode": "string",
          "discountRef": "string",
          "discountType": "string",
          "headerLevel": true,
          "id": "string",
          "name": "string"
        }
      ],
      "basePrice": 0,
      "basePriceExTax": 0,
      "basePriceExTaxInCent": 0,
      "basePriceInCent": 0,
      "basePriceIncTax": 0,
      "basePriceIncTaxInCent": 0,
      "cancelledAt": "2022-06-27T14:45:40.353Z",
      "created_at": "2022-06-27T14:45:40.353Z",
      "entryRef": "string",
      "gtin": "string",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "processedAt": "2022-06-27T14:45:40.353Z",
      "productId": "string",
      "productRef": "string",
      "quantity": 0,
      "refundAmount": 0,
      "refundAmountInCent": 0,
      "returnId": 0,
      "returnedAt": "2022-06-27T14:45:40.353Z",
      "returnedQuantity": 0,
      "shippedQuantity": 0,
      "totalAmount": 0,
      "totalAmountBeforeDiscount": 0,
      "totalAmountBeforeDiscountInCent": 0,
      "totalAmountExTax": 0,
      "totalAmountInCent": 0,
      "totalAmountIncTax": 0,
      "totalAmountIncTaxInCent": 0,
      "updated_at": "2022-06-27T14:45:40.353Z"
    }
  ],
  "orderRef": "string",
  "orderStatus": "AWAITING_PAYMENT",
  "paymentMethod": "string",
  "paymentProvider": "string",
  "paymentStatus": "AUTHORIZED",
  "processedAt": "2022-06-27T14:45:40.353Z",
  "promotionalDiscounts": 0,
  "promotionalDiscountsInCent": 0,
  "refundedAmount": 0,
  "refundedAmountInCent": 0,
  "returnReason": "string",
  "returned": true,
  "returnedAt": "2022-06-27T14:45:40.353Z",
  "shipmentMode": {
    "created_at": "2022-06-27T14:45:40.353Z",
    "id": "string",
    "name": "string",
    "shipmentCost": 0,
    "shipmentCostInCent": 0,
    "updated_at": "2022-06-27T14:45:40.353Z"
  },
  "shipments": [
    {
      "created_at": "2022-06-27T14:45:40.353Z",
      "deliveryDate": "2022-06-27T14:45:40.353Z",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "shipmentLines": [
        {
          "created_at": "2022-06-27T14:45:40.353Z",
          "entryId": "string",
          "entryRef": "string",
          "id": "string",
          "orderId": "string",
          "orderRef": "string",
          "quantityShipped": "string",
          "shipmentId": "string",
          "shipmentLineRef": "string",
          "shipmentRef": "string",
          "updated_at": "2022-06-27T14:45:40.353Z"
        }
      ],
      "shipmentProvider": "string",
      "shipmentRef": "string",
      "shipmentStatus": "DELIVERED",
      "shippedDate": "2022-06-27T14:45:40.353Z",
      "trackingNumber": "string",
      "trackingUrl": "string",
      "updated_at": "2022-06-27T14:45:40.353Z"
    }
  ],
  "shippingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "shippingCost": 0,
  "shippingCostBeforeDiscount": 0,
  "shippingCostBeforeDiscountInCent": 0,
  "shippingCostExTax": 0,
  "shippingCostExTaxInCent": 0,
  "shippingCostInCent": 0,
  "shippingCostIncTax": 0,
  "shippingCostIncTaxCent": 0,
  "shippingState": "CREATED",
  "taxCategoryCode": "string",
  "taxIncluded": true,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountExTaxInCent": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "totalDiscounts": 0,
  "totalDiscountsInCent": 0,
  "totalItems": 0,
  "updated_at": "2022-06-27T14:45:40.353Z",
  "wrappingCost": 0,
  "wrappingCostExTax": 0,
  "wrappingCostExTaxInCent": 0,
  "wrappingCostInCent": 0,
  "wrappingCostIncTax": 0,
  "wrappingCostIncTaxInCent": 0
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


## Delete order entry/line

Endpoint: ```​​/api​/v1​/orders​/entry```

Method: ```DELETE ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)


<summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Query Params : 

```
entryId - Entry ID , entryRef - Entry Ref
```

<summary>Response - 204 (Deleted)</summary> 

```json
{
  "acceptsMarketing": true,
  "appliedDiscounts": [
    {
      "amount": 0,
      "amountInCent": 0,
      "couponCode": "string",
      "discountRef": "string",
      "discountType": "string",
      "headerLevel": true,
      "id": "string",
      "name": "string"
    }
  ],
  "appliedTaxes": [
    {
      "amount": 0,
      "amountInCent": 0,
      "id": "string",
      "name": "string",
      "taxCode": "string",
      "taxRate": 0
    }
  ],
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "BLOB"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "BLOB"
        }
      },
      "is_obsolete": true
    }
  },
  "billingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "cancelReason": "string",
  "cancelled": true,
  "cancelledAt": "2022-06-27T14:46:44.341Z",
  "cartId": "string",
  "channel": "MOBILE",
  "confirmed": true,
  "couponDiscounts": 0,
  "couponDiscountsInCent": 0,
  "created_at": "2022-06-27T14:46:44.341Z",
  "currencyCode": "string",
  "customerId": "string",
  "customerLocale": "string",
  "customerRef": "string",
  "deliveryStatus": "DELIVERED",
  "email": "string",
  "handlingCost": 0,
  "handlingCostExTax": 0,
  "handlingCostExTaxInCent": 0,
  "handlingCostInCent": 0,
  "handlingCostIncTax": 0,
  "handlingCostIncTaxInCent": 0,
  "id": "string",
  "ipAddress": "string",
  "ipAddressCountry": "string",
  "ipAddressCountryIsocode": "string",
  "itemsCancelled": 0,
  "itemsReturned": 0,
  "itemsShipped": 0,
  "orderLines": [
    {
      "appliedDiscounts": [
        {
          "amount": 0,
          "amountInCent": 0,
          "couponCode": "string",
          "discountRef": "string",
          "discountType": "string",
          "headerLevel": true,
          "id": "string",
          "name": "string"
        }
      ],
      "basePrice": 0,
      "basePriceExTax": 0,
      "basePriceExTaxInCent": 0,
      "basePriceInCent": 0,
      "basePriceIncTax": 0,
      "basePriceIncTaxInCent": 0,
      "cancelledAt": "2022-06-27T14:46:44.341Z",
      "created_at": "2022-06-27T14:46:44.341Z",
      "entryRef": "string",
      "gtin": "string",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "processedAt": "2022-06-27T14:46:44.341Z",
      "productId": "string",
      "productRef": "string",
      "quantity": 0,
      "refundAmount": 0,
      "refundAmountInCent": 0,
      "returnId": 0,
      "returnedAt": "2022-06-27T14:46:44.341Z",
      "returnedQuantity": 0,
      "shippedQuantity": 0,
      "totalAmount": 0,
      "totalAmountBeforeDiscount": 0,
      "totalAmountBeforeDiscountInCent": 0,
      "totalAmountExTax": 0,
      "totalAmountInCent": 0,
      "totalAmountIncTax": 0,
      "totalAmountIncTaxInCent": 0,
      "updated_at": "2022-06-27T14:46:44.341Z"
    }
  ],
  "orderRef": "string",
  "orderStatus": "AWAITING_PAYMENT",
  "paymentMethod": "string",
  "paymentProvider": "string",
  "paymentStatus": "AUTHORIZED",
  "processedAt": "2022-06-27T14:46:44.341Z",
  "promotionalDiscounts": 0,
  "promotionalDiscountsInCent": 0,
  "refundedAmount": 0,
  "refundedAmountInCent": 0,
  "returnReason": "string",
  "returned": true,
  "returnedAt": "2022-06-27T14:46:44.341Z",
  "shipmentMode": {
    "created_at": "2022-06-27T14:46:44.341Z",
    "id": "string",
    "name": "string",
    "shipmentCost": 0,
    "shipmentCostInCent": 0,
    "updated_at": "2022-06-27T14:46:44.341Z"
  },
  "shipments": [
    {
      "created_at": "2022-06-27T14:46:44.341Z",
      "deliveryDate": "2022-06-27T14:46:44.341Z",
      "id": "string",
      "orderId": "string",
      "orderRef": "string",
      "shipmentLines": [
        {
          "created_at": "2022-06-27T14:46:44.341Z",
          "entryId": "string",
          "entryRef": "string",
          "id": "string",
          "orderId": "string",
          "orderRef": "string",
          "quantityShipped": "string",
          "shipmentId": "string",
          "shipmentLineRef": "string",
          "shipmentRef": "string",
          "updated_at": "2022-06-27T14:46:44.341Z"
        }
      ],
      "shipmentProvider": "string",
      "shipmentRef": "string",
      "shipmentStatus": "DELIVERED",
      "shippedDate": "2022-06-27T14:46:44.341Z",
      "trackingNumber": "string",
      "trackingUrl": "string",
      "updated_at": "2022-06-27T14:46:44.341Z"
    }
  ],
  "shippingAddress": {
    "address1": "string",
    "address2": "string",
    "addressId": "string",
    "addressRef": "string",
    "city": "string",
    "company": "string",
    "country": "string",
    "countryCode": "string",
    "countryName": "string",
    "email": "string",
    "id": "string",
    "name": "string",
    "phone": "string",
    "postcode": "string",
    "province": "string",
    "provinceCode": "string"
  },
  "shippingCost": 0,
  "shippingCostBeforeDiscount": 0,
  "shippingCostBeforeDiscountInCent": 0,
  "shippingCostExTax": 0,
  "shippingCostExTaxInCent": 0,
  "shippingCostInCent": 0,
  "shippingCostIncTax": 0,
  "shippingCostIncTaxCent": 0,
  "shippingState": "CREATED",
  "taxCategoryCode": "string",
  "taxIncluded": true,
  "totalAmount": 0,
  "totalAmountBeforeDiscount": 0,
  "totalAmountBeforeDiscountInCent": 0,
  "totalAmountExTax": 0,
  "totalAmountExTaxInCent": 0,
  "totalAmountInCent": 0,
  "totalAmountIncTax": 0,
  "totalAmountIncTaxInCent": 0,
  "totalDiscounts": 0,
  "totalDiscountsInCent": 0,
  "totalItems": 0,
  "updated_at": "2022-06-27T14:46:44.341Z",
  "wrappingCost": 0,
  "wrappingCostExTax": 0,
  "wrappingCostExTaxInCent": 0,
  "wrappingCostInCent": 0,
  "wrappingCostIncTax": 0,
  "wrappingCostIncTaxInCent": 0
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
[Back to Top](#order-svc-api)

[Back to Home](index.md#welcome-to-the-wishlist)



