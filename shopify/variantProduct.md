# **Variant Product**
A variant can be added to a Product resource to represent one version of a product with several options. The Product resource will have a variant for every possible combination of its options. 

## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.

### Product

<!-- </details> -->
<!-- <summary>Expand for details</summary> -->

`barcode` - The barcode, UPC, or ISBN number for the product.

`compare_at_price` - The original price of the item before an adjustment or a sale.

`created_at` - The date and time (ISO 8601 format) when the product variant was created.

`fulfillment_service` - The fulfillment service associated with the product variant. Valid values: manual or the handle of a fulfillment service.

`grams` - The weight of the product variant in grams.

`id` - The unique numeric identifier for the product variant.

`image_id` - The unique numeric identifier for a product's image. The image must be associated to the same product as the variant.

`inventory_item_id` - The unique identifier for the inventory item, which is used in the Inventory API to query for inventory information.

`inventory_management` - The fulfillment service that tracks the number of items in stock for the product variant. Valid values:
- shopify: You are tracking inventory yourself using the admin.
- null: You aren't tracking inventory on the variant.
- The handle of a fulfillment service that has inventory management enabled: This must be the same fulfillment service referenced by the fulfillment_service property.

`inventory_policy` - Whether customers are allowed to place an order for the product variant when it's out of stock. Valid values:
- deny: Customers are not allowed to place orders for the product variant if it's out of stock.
- continue: Customers are allowed to place orders for the product variant if it's out of stock.
  
*Default value: deny.

`inventory_quantity` - An aggregate of inventory across all locations. To adjust inventory at a specific location, use the InventoryLevel resource.

`old_inventory_quantity` - This property is deprecated. Use the InventoryLevel resource instead.

`inventory_quantity_adjustment` - This property is deprecated. Use the InventoryLevel resource instead.

`option` - The custom properties that a shop owner uses to define product variants. You can define three options for a product variant: option1, option2, option3. Default value: Default Title. The title field is a concatenation of the option1, option2, and option3 fields. Updating the option fields updates the title field.

`presentment_prices` - A list of the variant's presentment prices and compare-at prices in each of the shop's enabled presentment currencies. Each price object has the following properties:
- currency_code: The three-letter code (ISO 4217 format) for one of the shop's enabled presentment currencies.
- amount: The variant's price or compare-at price in the presentment currency.

`position` - The order of the product variant in the list of product variants. The first position in the list is 1. The position of variants is indicated by the order in which they are listed.

`price` - The price of the product variant.

`product_id` - The unique numeric identifier for the product.

`requires_shipping` - This property is deprecated. Use the *requires_shipping* property on the InventoryItem resource instead.

`sku` - A unique identifier for the product variant in the shop. Required in order to connect to a FulfillmentService.

`taxable` - Whether a tax is charged when the product variant is sold.

`tax_code` - This parameter applies only to the stores that have the Avalara AvaTax app installed. Specifies the Avalara tax code for the product variant.

`title`- The title of the product variant. The title field is a concatenation of the option1, option2, and option3 fields. You can only update title indirectly using the option fields.

`updated_at` - The date and time when the product variant was last modified. Gets returned in ISO 8601 format.

`weight` - The weight of the product variant in the unit system specified with weight_unit.

`weight_unit` - The unit of measurement that applies to the product variant's weight. If you don't specify a value for weight_unit, then the shop's default unit of measurement is applied. Valid values: g, kg, oz, and lb.

<!-- </details> -->

## **REST Endpoints**

## Add products variant from shopify to TWC
A new variant is created for an existing product in the TWC system from the shopify data using the connector.

Endpoint: ```/api/products/variants```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication`


<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

<!-- <details> -->
 <summary>Payload</summary>
 
```json
{
  "admin_graphql_api_id": "string",
  "barcode": "string",
  "compare_at_price": 0,
  "created_at": "2022-06-22T11:35:05.578Z",
  "fulfillment_service": "string",
  "grams": 0,
  "id": "string",
  "image_id": "string",
  "inventory_item_id": "string",
  "inventory_management": "string",
  "inventory_policy": "string",
  "inventory_quantity": 0,
  "old_inventory_quantity": 0,
  "option1": "string",
  "option2": "string",
  "option3": "string",
  "position": 0,
  "presentment_prices": [
    {
      "compare_at_price": 0,
      "price": {
        "amount": 0,
        "currency_code": "string"
      }
    }
  ],
  "price": 0,
  "product_id": "string",
  "requires_shipping": true,
  "sku": "string",
  "tax_code": "string",
  "taxable": true,
  "title": "string",
  "updated_at": "2022-06-22T11:35:05.578Z",
  "weight": 0,
  "weight_unit": "string"
}
      
 ```
 
<!-- </details> -->

<!-- <details> -->
 <summary>Response - 200 (OK)</summary>

```json
{
  "admin_graphql_api_id": "string",
  "barcode": "string",
  "compare_at_price": 0,
  "created_at": "2022-06-22T11:35:05.603Z",
  "fulfillment_service": "string",
  "grams": 0,
  "id": "string",
  "image_id": "string",
  "inventory_item_id": "string",
  "inventory_management": "string",
  "inventory_policy": "string",
  "inventory_quantity": 0,
  "old_inventory_quantity": 0,
  "option1": "string",
  "option2": "string",
  "option3": "string",
  "position": 0,
  "presentment_prices": [
    {
      "compare_at_price": 0,
      "price": {
        "amount": 0,
        "currency_code": "string"
      }
    }
  ],
  "price": 0,
  "product_id": "string",
  "requires_shipping": true,
  "sku": "string",
  "tax_code": "string",
  "taxable": true,
  "title": "string",
  "updated_at": "2022-06-22T11:35:05.603Z",
  "weight": 0,
  "weight_unit": "string"
}      
 ```
 
<!-- </details> --> 

<!-- <details> -->
 <summary>Response - 201 (Variant  created)</summary>
 
 ```json
 {
  "admin_graphql_api_id": "string",
  "barcode": "string",
  "compare_at_price": 0,
  "created_at": "2022-06-22T11:35:05.606Z",
  "fulfillment_service": "string",
  "grams": 0,
  "id": "string",
  "image_id": "string",
  "inventory_item_id": "string",
  "inventory_management": "string",
  "inventory_policy": "string",
  "inventory_quantity": 0,
  "old_inventory_quantity": 0,
  "option1": "string",
  "option2": "string",
  "option3": "string",
  "position": 0,
  "presentment_prices": [
    {
      "compare_at_price": 0,
      "price": {
        "amount": 0,
        "currency_code": "string"
      }
    }
  ],
  "price": 0,
  "product_id": "string",
  "requires_shipping": true,
  "sku": "string",
  "tax_code": "string",
  "taxable": true,
  "title": "string",
  "updated_at": "2022-06-22T11:35:05.606Z",
  "weight": 0,
  "weight_unit": "string"
}
 ```
 <!-- </details> --> 

<!-- <details> -->
 <summary>Response - 400 (Bad request)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
<!-- </details> --> 

<!-- <details> -->
 <summary>Response - 405 (Invalid input)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
<!-- </details> -->
 
HTTP Status Code:
``` 
- 200 OK
- 201 Variant created
- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Add products from shopify to TWC
Used for entering multiple variant data of a product to the TWC system from a bulk Shopify data. 

Endpoint: ```/api/products/upload-variants```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication`


<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

<!-- <details> -->
 <summary>Payload</summary>
 
```json
{
  "variants": [
    {
      "admin_graphql_api_id": "string",
      "barcode": "string",
      "compare_at_price": 0,
      "created_at": "2022-06-22T11:38:04.413Z",
      "fulfillment_service": "string",
      "grams": 0,
      "id": "string",
      "image_id": "string",
      "inventory_item_id": "string",
      "inventory_management": "string",
      "inventory_policy": "string",
      "inventory_quantity": 0,
      "old_inventory_quantity": 0,
      "option1": "string",
      "option2": "string",
      "option3": "string",
      "position": 0,
      "presentment_prices": [
        {
          "compare_at_price": 0,
          "price": {
            "amount": 0,
            "currency_code": "string"
          }
        }
      ],
      "price": 0,
      "product_id": "string",
      "requires_shipping": true,
      "sku": "string",
      "tax_code": "string",
      "taxable": true,
      "title": "string",
      "updated_at": "2022-06-22T11:38:04.413Z",
      "weight": 0,
      "weight_unit": "string"
    }
  ]
}      
```
 
<!-- </details> -->


<!-- <details> -->
 <summary>Response - 400 (Invalid ID supplied)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
<!-- </details> --> 

<!-- <details> -->
 <summary>Response - 401 (Unauthorized)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
<!-- </details> --> 


<!-- <details> -->
 <summary>Response - 405 (Invalid input)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
<!-- </details> -->

<!-- <details> -->
 <summary>Response - 406 (Unacceptable Input)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
<!-- </details> -->
 
HTTP Status Code:
``` 
- 200 Variant updated
- 201 created
- 400 Invalid ID suppied
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 Validation exception
- 406 Unacceptable Input
```

## Update an existing variant
Updates an already existing variant. If the product or the variant does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/products/variant```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication`


<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

<!-- <details> -->
 <summary>Payload</summary>
 
```json
{
  "admin_graphql_api_id": "string",
  "barcode": "string",
  "compare_at_price": 0,
  "created_at": "2022-06-22T11:41:24.349Z",
  "fulfillment_service": "string",
  "grams": 0,
  "id": "string",
  "image_id": "string",
  "inventory_item_id": "string",
  "inventory_management": "string",
  "inventory_policy": "string",
  "inventory_quantity": 0,
  "old_inventory_quantity": 0,
  "option1": "string",
  "option2": "string",
  "option3": "string",
  "position": 0,
  "presentment_prices": [
    {
      "compare_at_price": 0,
      "price": {
        "amount": 0,
        "currency_code": "string"
      }
    }
  ],
  "price": 0,
  "product_id": "string",
  "requires_shipping": true,
  "sku": "string",
  "tax_code": "string",
  "taxable": true,
  "title": "string",
  "updated_at": "2022-06-22T11:41:24.349Z",
  "weight": 0,
  "weight_unit": "string"
}      
 ```
 
<!-- </details> -->

<!-- <details> -->
 <summary>Response - 200 (Variant updated)</summary>

```json
  {
  "admin_graphql_api_id": "string",
  "barcode": "string",
  "compare_at_price": 0,
  "created_at": "2022-06-22T11:41:24.376Z",
  "fulfillment_service": "string",
  "grams": 0,
  "id": "string",
  "image_id": "string",
  "inventory_item_id": "string",
  "inventory_management": "string",
  "inventory_policy": "string",
  "inventory_quantity": 0,
  "old_inventory_quantity": 0,
  "option1": "string",
  "option2": "string",
  "option3": "string",
  "position": 0,
  "presentment_prices": [
    {
      "compare_at_price": 0,
      "price": {
        "amount": 0,
        "currency_code": "string"
      }
    }
  ],
  "price": 0,
  "product_id": "string",
  "requires_shipping": true,
  "sku": "string",
  "tax_code": "string",
  "taxable": true,
  "title": "string",
  "updated_at": "2022-06-22T11:41:24.376Z",
  "weight": 0,
  "weight_unit": "string"
}    
 ```
 
<!-- </details> --> 


<!-- <details> -->
 <summary>Response - 400 (Invalid ID Supplied)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
<!-- </details> --> 

<!-- <details> -->
 <summary>Response - 401 (Unauthorized)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
<!-- </details> --> 


<!-- <details> -->
 <summary>Response - 404 (Product not found)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
<!-- </details> -->

<!-- <details> -->
 <summary>Response - 405 (Validation exception)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
<!-- </details> -->
 
HTTP Status Code:
``` 
- 200 Variant updated
- 201 created
- 400 Invalid ID Supplied
- 401 Unauthorized
- 403 Forbidden 
- 404 Product Not Found
- 405 Validation exception
```

## Find product by ID
Returns an products by its id and variant id by passing the respective id's as a path params in the endpoint. 
If the products or the variant does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/products/{productId}/variants/{id}```

Method: ``` GET ``` 

OAuth 2.0 Scopes: `Tenant authentication`


<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

<!-- <details> -->
 <summary>Path Variables</summary>
 
	- {id}
	- {productId}
 
<!-- </details> -->

<!-- <details> -->
 <summary>Response - 200 (successful operation)</summary>

```json
 {
  "admin_graphql_api_id": "string",
  "barcode": "string",
  "compare_at_price": 0,
  "created_at": "2022-06-22T11:44:28.261Z",
  "fulfillment_service": "string",
  "grams": 0,
  "id": "string",
  "image_id": "string",
  "inventory_item_id": "string",
  "inventory_management": "string",
  "inventory_policy": "string",
  "inventory_quantity": 0,
  "old_inventory_quantity": 0,
  "option1": "string",
  "option2": "string",
  "option3": "string",
  "position": 0,
  "presentment_prices": [
    {
      "compare_at_price": 0,
      "price": {
        "amount": 0,
        "currency_code": "string"
      }
    }
  ],
  "price": 0,
  "product_id": "string",
  "requires_shipping": true,
  "sku": "string",
  "tax_code": "string",
  "taxable": true,
  "title": "string",
  "updated_at": "2022-06-22T11:44:28.261Z",
  "weight": 0,
  "weight_unit": "string"
}     
 ```
 
<!-- </details> --> 

<!-- <details> -->
 <summary>Response - 400 (Invalid Id supplied)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
<!-- </details> --> 

<!-- <details> -->
 <summary>Response - 404 (Product not found)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
<!-- </details> -->

HTTP Status Code:
``` 
- 200 successful created
- 400 Invalid ID supplied
- 401 Unauthorized
- 403 Forbidden 
- 404 Product Not Found
```

## Deletes a product
Product variant is marked as deleted by passing id as a path param of the endpoint.

Endpoint: ```/api/products/{productId}/variants/{id}```

Method: ``` DELETE ``` 

OAuth 2.0 Scopes: `Tenant authentication`


<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->

<!-- <details> -->
 <summary>Path Variables</summary>
 
 - {id}
 - {productId}
	
 
<!-- </details> -->

<!-- <details> -->
 <summary>Response - 400 (Invalid ID supplied)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
<!-- </details> --> 

<!-- <details> -->
 <summary>Response - 404 (Product not found)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
<!-- </details> -->
 
HTTP Status Code:
``` 
- 200 Product deleted
- 201 No Content
- 400 Invalid Id Supplied
- 401 Unauthorized
- 403 Forbidden 
- 404 Product Not Found
```



***
[Back to Shopify connector](../ShopifyConnector.md)

[Back to Index](index.md)