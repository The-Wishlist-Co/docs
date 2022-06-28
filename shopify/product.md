
# **Product**

The Product resource lets you update and create products in a merchant's store. You can use product variants with the Product resource to create or update different versions of the same product. You can also add or update product images.

## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.

### Product
<!-- <details> -->
<!-- <summary>Expand for details</summary> -->

`body_html` - string - A description of the product. Supports HTML formatting.

`created_at` - The date and time (ISO 8601 format) when the product was created.

`handle` - string - A unique human-friendly string for the product. Automatically generated from the product's title. Used by the Liquid templating language to refer to objects.

`id` - integer -An integer that's used as a unique identifier for the product. Each id is unique across the Shopify system. No two products will have the same id, even if they're from different shops.

 `images ` - array - A list of product image objects, each one representing an image associated with the product.

`options`- array - The custom product properties. For example, Size, Color, and Material. Each product can have up to 3 options and each option value can be up to 255 characters. Product variants are made of up combinations of option values. Options cannot be created without values. To create new options, a variant with an associated option value also needs to be created.

`product_type` - string - A categorization for the product used for filtering and searching products.

`published_at` - The date and time (ISO 8601 format) when the product was published. Can be set to null to unpublish the product from the Online Store channel.

`published_scope` - string - Whether the product is published to the Point of Sale channel. Valid values:
- web: The product is published to the Online Store channel but not published to the Point of Sale channel.
- global: The product is published to both the Online Store channel and the Point of Sale channel.

`status` - string - The status of the product.
 Valid values:
- active: The product is ready to sell and is available to customers on the online store, sales channels, and apps. By default, existing products are set to active.
- archived: The product is no longer being sold and isn't available to customers on sales channels and apps.
- draft: The product isn't ready to sell and is unavailable to customers on sales channels and apps. By default, duplicated and unarchived products are set to draft.

`tags` - string - A string of comma-separated tags that are used for filtering and search. A product can have up to 250 tags. Each tag can have up to 255 characters.

`template_suffix` - string - The suffix of the Liquid template used for the product page. If this property is specified, then the product page uses a template called "product.suffix.liquid", where "suffix" is the value of this property. If this property is "" or null, then the product 
page uses the default template "product.liquid". (default: null)

`title` - string - The name of the product.

`updated_at` - The date and time (ISO 8601 format) when the product was last modified. A product's updated_at value can change for different reasons. For example, if an order is placed for a product that has inventory tracking set up, then the inventory adjustment is counted as an update.

`variants` - array - An array of product variants, each representing a different version of the product.

`vendor` - string - The name of the product's vendor.

<!-- </details> -->

## **REST Endpoints**

## Add products from shopify to TWC
The shopify product data is translated and transformed according to the TWC system requiremennts through product section of the shopify connector api.
Endpoint: ```/api/products```

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
  "body_html": "string",
  "created_at": "2022-06-22T10:19:06.867Z",
  "handle": "string",
  "id": "string",
  "image": {
    "admin_graphql_api_id": "string",
    "alt": "string",
    "created_at": "string",
    "height": 0,
    "id": "string",
    "position": 0,
    "product_id": "string",
    "src": "string",
    "updated_at": "string",
    "variant_ids": [
      "string"
    ],
    "width": 0
  },
  "images": [
    {
      "admin_graphql_api_id": "string",
      "alt": "string",
      "created_at": "string",
      "height": 0,
      "id": "string",
      "position": 0,
      "product_id": "string",
      "src": "string",
      "updated_at": "string",
      "variant_ids": [
        "string"
      ],
      "width": 0
    }
  ],
  "options": [
    {
      "id": "string",
      "name": "string",
      "position": 0,
      "product_id": "string",
      "values": [
        "string"
      ]
    }
  ],
  "product_type": "string",
  "published_at": "2022-06-22T10:19:06.867Z",
  "published_scope": "web",
  "status": "active",
  "tags": "string",
  "template_suffix": "string",
  "title": "string",
  "twc_product_id": "string",
  "updated_at": "2022-06-22T10:19:06.868Z",
  "variants": [
    {
      "admin_graphql_api_id": "string",
      "barcode": "string",
      "compare_at_price": 0,
      "created_at": "2022-06-22T10:19:06.868Z",
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
      "updated_at": "2022-06-22T10:19:06.868Z",
      "weight": 0,
      "weight_unit": "string"
    }
  ],
  "vendor": "string"
}      
```
 
<!-- </details> -->

<!-- <details> -->
 <summary>Response - 200 (OK)</summary>

```json
{
  "admin_graphql_api_id": "string",
  "body_html": "string",
  "created_at": "2022-06-22T11:14:41.935Z",
  "handle": "string",
  "id": "string",
  "image": {
    "admin_graphql_api_id": "string",
    "alt": "string",
    "created_at": "string",
    "height": 0,
    "id": "string",
    "position": 0,
    "product_id": "string",
    "src": "string",
    "updated_at": "string",
    "variant_ids": [
      "string"
    ],
    "width": 0
  },
  "images": [
    {
      "admin_graphql_api_id": "string",
      "alt": "string",
      "created_at": "string",
      "height": 0,
      "id": "string",
      "position": 0,
      "product_id": "string",
      "src": "string",
      "updated_at": "string",
      "variant_ids": [
        "string"
      ],
      "width": 0
    }
  ],
  "options": [
    {
      "id": "string",
      "name": "string",
      "position": 0,
      "product_id": "string",
      "values": [
        "string"
      ]
    }
  ],
  "product_type": "string",
  "published_at": "2022-06-22T11:14:41.935Z",
  "published_scope": "web",
  "status": "active",
  "tags": "string",
  "template_suffix": "string",
  "title": "string",
  "twc_product_id": "string",
  "updated_at": "2022-06-22T11:14:41.935Z",
  "variants": [
    {
      "admin_graphql_api_id": "string",
      "barcode": "string",
      "compare_at_price": 0,
      "created_at": "2022-06-22T11:14:41.935Z",
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
      "updated_at": "2022-06-22T11:14:41.935Z",
      "weight": 0,
      "weight_unit": "string"
    }
  ],
  "vendor": "string"
}  
  
 ```
 
<!-- </details> --> 

<!-- <details> -->
 <summary>Response - 201 (product created)</summary>
 
 ```json
 {
  "admin_graphql_api_id": "string",
  "body_html": "string",
  "created_at": "2022-06-22T11:14:41.937Z",
  "handle": "string",
  "id": "string",
  "image": {
    "admin_graphql_api_id": "string",
    "alt": "string",
    "created_at": "string",
    "height": 0,
    "id": "string",
    "position": 0,
    "product_id": "string",
    "src": "string",
    "updated_at": "string",
    "variant_ids": [
      "string"
    ],
    "width": 0
  },
  "images": [
    {
      "admin_graphql_api_id": "string",
      "alt": "string",
      "created_at": "string",
      "height": 0,
      "id": "string",
      "position": 0,
      "product_id": "string",
      "src": "string",
      "updated_at": "string",
      "variant_ids": [
        "string"
      ],
      "width": 0
    }
  ],
  "options": [
    {
      "id": "string",
      "name": "string",
      "position": 0,
      "product_id": "string",
      "values": [
        "string"
      ]
    }
  ],
  "product_type": "string",
  "published_at": "2022-06-22T11:14:41.937Z",
  "published_scope": "web",
  "status": "active",
  "tags": "string",
  "template_suffix": "string",
  "title": "string",
  "twc_product_id": "string",
  "updated_at": "2022-06-22T11:14:41.937Z",
  "variants": [
    {
      "admin_graphql_api_id": "string",
      "barcode": "string",
      "compare_at_price": 0,
      "created_at": "2022-06-22T11:14:41.937Z",
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
      "updated_at": "2022-06-22T11:14:41.937Z",
      "weight": 0,
      "weight_unit": "string"
    }
  ],
  "vendor": "string"
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
- 201 Product created
- 400 Invalid status value
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Add products from shopify to TWC
The shopify product data is translated and transformed according to the TWC system requiremennts through product section of the shopify connector api. This endpoint is for creating bulk entries at a time.
Endpoint: ```/api/products/upload-products```

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
  "products": [
    {
      "admin_graphql_api_id": "string",
      "body_html": "string",
      "created_at": "2022-06-22T10:19:24.800Z",
      "handle": "string",
      "id": "string",
      "image": {
        "admin_graphql_api_id": "string",
        "alt": "string",
        "created_at": "string",
        "height": 0,
        "id": "string",
        "position": 0,
        "product_id": "string",
        "src": "string",
        "updated_at": "string",
        "variant_ids": [
          "string"
        ],
        "width": 0
      },
      "images": [
        {
          "admin_graphql_api_id": "string",
          "alt": "string",
          "created_at": "string",
          "height": 0,
          "id": "string",
          "position": 0,
          "product_id": "string",
          "src": "string",
          "updated_at": "string",
          "variant_ids": [
            "string"
          ],
          "width": 0
        }
      ],
      "options": [
        {
          "id": "string",
          "name": "string",
          "position": 0,
          "product_id": "string",
          "values": [
            "string"
          ]
        }
      ],
      "product_type": "string",
      "published_at": "2022-06-22T10:19:24.800Z",
      "published_scope": "web",
      "status": "active",
      "tags": "string",
      "template_suffix": "string",
      "title": "string",
      "twc_product_id": "string",
      "updated_at": "2022-06-22T10:19:24.800Z",
      "variants": [
        {
          "admin_graphql_api_id": "string",
          "barcode": "string",
          "compare_at_price": 0,
          "created_at": "2022-06-22T10:19:24.800Z",
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
          "updated_at": "2022-06-22T10:19:24.800Z",
          "weight": 0,
          "weight_unit": "string"
        }
      ],
      "vendor": "string"
    }
  ]
}      
 ```
 
<!-- </details> -->

<!-- <details> -->
 <summary>Response - 400 (Invalid status value)</summary>
 
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
- 201 created
- 400 Invalid status value
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Update an existing product
Updates an already existing product. If the product does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/products```

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
  "body_html": "string",
  "created_at": "2022-06-22T10:19:16.410Z",
  "handle": "string",
  "id": "string",
  "image": {
    "admin_graphql_api_id": "string",
    "alt": "string",
    "created_at": "string",
    "height": 0,
    "id": "string",
    "position": 0,
    "product_id": "string",
    "src": "string",
    "updated_at": "string",
    "variant_ids": [
      "string"
    ],
    "width": 0
  },
  "images": [
    {
      "admin_graphql_api_id": "string",
      "alt": "string",
      "created_at": "string",
      "height": 0,
      "id": "string",
      "position": 0,
      "product_id": "string",
      "src": "string",
      "updated_at": "string",
      "variant_ids": [
        "string"
      ],
      "width": 0
    }
  ],
  "options": [
    {
      "id": "string",
      "name": "string",
      "position": 0,
      "product_id": "string",
      "values": [
        "string"
      ]
    }
  ],
  "product_type": "string",
  "published_at": "2022-06-22T10:19:16.410Z",
  "published_scope": "web",
  "status": "active",
  "tags": "string",
  "template_suffix": "string",
  "title": "string",
  "twc_product_id": "string",
  "updated_at": "2022-06-22T10:19:16.410Z",
  "variants": [
    {
      "admin_graphql_api_id": "string",
      "barcode": "string",
      "compare_at_price": 0,
      "created_at": "2022-06-22T10:19:16.410Z",
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
      "updated_at": "2022-06-22T10:19:16.410Z",
      "weight": 0,
      "weight_unit": "string"
    }
  ],
  "vendor": "string"
}      
 ```
 
<!-- </details> -->

<!-- <details> -->
 <summary>Response - 200 (OK)</summary>

```json
 {
  "admin_graphql_api_id": "string",
  "body_html": "string",
  "created_at": "2022-06-22T11:20:55.611Z",
  "handle": "string",
  "id": "string",
  "image": {
    "admin_graphql_api_id": "string",
    "alt": "string",
    "created_at": "string",
    "height": 0,
    "id": "string",
    "position": 0,
    "product_id": "string",
    "src": "string",
    "updated_at": "string",
    "variant_ids": [
      "string"
    ],
    "width": 0
  },
  "images": [
    {
      "admin_graphql_api_id": "string",
      "alt": "string",
      "created_at": "string",
      "height": 0,
      "id": "string",
      "position": 0,
      "product_id": "string",
      "src": "string",
      "updated_at": "string",
      "variant_ids": [
        "string"
      ],
      "width": 0
    }
  ],
  "options": [
    {
      "id": "string",
      "name": "string",
      "position": 0,
      "product_id": "string",
      "values": [
        "string"
      ]
    }
  ],
  "product_type": "string",
  "published_at": "2022-06-22T11:20:55.611Z",
  "published_scope": "web",
  "status": "active",
  "tags": "string",
  "template_suffix": "string",
  "title": "string",
  "twc_product_id": "string",
  "updated_at": "2022-06-22T11:20:55.611Z",
  "variants": [
    {
      "admin_graphql_api_id": "string",
      "barcode": "string",
      "compare_at_price": 0,
      "created_at": "2022-06-22T11:20:55.611Z",
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
      "updated_at": "2022-06-22T11:20:55.611Z",
      "weight": 0,
      "weight_unit": "string"
    }
  ],
  "vendor": "string"
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
- 200 OK
- 201 created
- 400 Invalid ID supplied
- 401 Unauthorized
- 403 Forbidden 
- 404 Product not found
- 405 Validation exception
```

## Find product by ID
Returns an products by its id from a specific Store while passing the respective id as a path param in the endpoint. 
If the products does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/products​/{id}```

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
 <summary>Path Variable</summary>
 
  - {id}
  
<!-- </details> -->

<!-- <details> -->
 <summary>Response - 200 (successful operation)</summary>

```json
  {
  "admin_graphql_api_id": "string",
  "body_html": "string",
  "created_at": "2022-06-22T11:25:51.404Z",
  "handle": "string",
  "id": "string",
  "image": {
    "admin_graphql_api_id": "string",
    "alt": "string",
    "created_at": "string",
    "height": 0,
    "id": "string",
    "position": 0,
    "product_id": "string",
    "src": "string",
    "updated_at": "string",
    "variant_ids": [
      "string"
    ],
    "width": 0
  },
  "images": [
    {
      "admin_graphql_api_id": "string",
      "alt": "string",
      "created_at": "string",
      "height": 0,
      "id": "string",
      "position": 0,
      "product_id": "string",
      "src": "string",
      "updated_at": "string",
      "variant_ids": [
        "string"
      ],
      "width": 0
    }
  ],
  "options": [
    {
      "id": "string",
      "name": "string",
      "position": 0,
      "product_id": "string",
      "values": [
        "string"
      ]
    }
  ],
  "product_type": "string",
  "published_at": "2022-06-22T11:25:51.404Z",
  "published_scope": "web",
  "status": "active",
  "tags": "string",
  "template_suffix": "string",
  "title": "string",
  "twc_product_id": "string",
  "updated_at": "2022-06-22T11:25:51.404Z",
  "variants": [
    {
      "admin_graphql_api_id": "string",
      "barcode": "string",
      "compare_at_price": 0,
      "created_at": "2022-06-22T11:25:51.404Z",
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
      "updated_at": "2022-06-22T11:25:51.404Z",
      "weight": 0,
      "weight_unit": "string"
    }
  ],
  "vendor": "string"
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
- 200 successful operation
- 400 Invalid ID supplied
- 401 Unauthorized
- 403 Forbidden 
- 404 Product not found
```


## Deletes a product
Product is marked as deleted by passing id as a path param of the endpoint.

Endpoint: ```/api/products​/{id}```

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
 <summary>Path Variable</summary>
 
  - {id}
 
<!-- </details> -->

<!-- <details> -->
 <summary>Response - 200 (Product deleted)</summary>

```json
   {
  "admin_graphql_api_id": "string",
  "body_html": "string",
  "created_at": "2022-06-22T11:28:20.435Z",
  "handle": "string",
  "id": "string",
  "image": {
    "admin_graphql_api_id": "string",
    "alt": "string",
    "created_at": "string",
    "height": 0,
    "id": "string",
    "position": 0,
    "product_id": "string",
    "src": "string",
    "updated_at": "string",
    "variant_ids": [
      "string"
    ],
    "width": 0
  },
  "images": [
    {
      "admin_graphql_api_id": "string",
      "alt": "string",
      "created_at": "string",
      "height": 0,
      "id": "string",
      "position": 0,
      "product_id": "string",
      "src": "string",
      "updated_at": "string",
      "variant_ids": [
        "string"
      ],
      "width": 0
    }
  ],
  "options": [
    {
      "id": "string",
      "name": "string",
      "position": 0,
      "product_id": "string",
      "values": [
        "string"
      ]
    }
  ],
  "product_type": "string",
  "published_at": "2022-06-22T11:28:20.435Z",
  "published_scope": "web",
  "status": "active",
  "tags": "string",
  "template_suffix": "string",
  "title": "string",
  "twc_product_id": "string",
  "updated_at": "2022-06-22T11:28:20.435Z",
  "variants": [
    {
      "admin_graphql_api_id": "string",
      "barcode": "string",
      "compare_at_price": 0,
      "created_at": "2022-06-22T11:28:20.435Z",
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
      "updated_at": "2022-06-22T11:28:20.435Z",
      "weight": 0,
      "weight_unit": "string"
    }
  ],
  "vendor": "string"
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
- 204 No Content
- 400 Invalid ID supplied
- 401 Unauthorized
- 403 Forbidden 
- 404 Product not found
```

***
[Back to Shopify connector](../ShopifyConnector.md)

[Back to Index](index.md)





