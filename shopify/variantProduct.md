# **Variant Product**
A variant can be added to a Product resource to represent one version of a product with several options. The Product resource will have a variant for every possible combination of its options. 

## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.

### Product

</details>
<summary>Expand for details</summary>

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

</details>

## **REST Endpoints**

## Add products variant from shopify to TWC
A new variant is created for an existing product in the TWC system from the shopify data using the connector.

Endpoint: ```/api/products/variants```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication`

## Add products from shopify to TWC
Used for entering multiple variant data of a product to the TWC system from a bulk Shopify data. 

Endpoint: ```/api/products/upload-variants```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication`

## Update an existing variant
Updates an already existing variant. If the product or the variant does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/products/variant```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication`

## Find product by ID
Returns an products by its id and variant id by passing the respective id's as a path params in the endpoint. 
If the products or the variant does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/products/{productId}/variants/{id}```

Method: ``` GET ``` 

OAuth 2.0 Scopes: `Tenant authentication`

## Deletes a product
Product variant is marked as deleted by passing id as a path param of the endpoint.

Endpoint: ```/api/products/{productId}/variants/{id}```

Method: ``` DELETE ``` 

OAuth 2.0 Scopes: `Tenant authentication`




