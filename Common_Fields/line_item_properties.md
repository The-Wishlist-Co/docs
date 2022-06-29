## Line Items Properties


`fulfillable_quantity` : The amount available to fulfill, calculated as follows:
- quantity max(refunded_quantity, fulfilled_quantity)
- pending_fulfilled_quantity - open_fulfilled_quantity

`fulfillment_service` : The service provider that's fulfilling the item. Valid values: manual, or the name of the provider, such as amazon or shipwire.

`fulfillment_status` : How far along an order is in terms line items fulfilled. Valid values: null, fulfilled, partial, and not_eligible.

`grams` : The weight of the item in grams.

`id` : The ID of the line item.

`price` : The price of the item before discounts have been applied in the shop currency.

`price_set` : The price of the line item in shop and presentment currencies.

`product_id` : The ID of the product that the line item belongs to. Can be null if the original product associated with the order is deleted at a later date.

`quantity` : The number of items that were purchased.

`requires_shipping` : Whether the item requires shipping.

`sku` : The item's SKU (stock keeping unit).

`title` : The title of the product.

`variant_id` : The ID of the product variant.

`variant_title` : The title of the product variant.

`vendor` : The name of the item's supplier.

`name` : The name of the product variant.

`gift_card` : Whether the item is a gift card. If true, then the item is not taxed or considered for shipping charges.

`properties` : An array of custom information for the item that has been added to the cart. Often used to provide product customization options.

`taxable` : Whether the item was taxable.

`tax_lines` : A list of tax line objects, each of which details a tax applied to the item.

- `title` : The name of the tax.

- `price` : The amount added to the order for this tax in the shop currency.

- `price_set` : The amount added to the order for this tax in shop and presentment currencies.

- `rate` : The tax rate applied to the order to calculate the tax price. 

- `channel_liable` : Whether the channel that submitted the tax line is liable for remitting. A value of null indicates unknown liability for the tax line.

`tip_payment_gateway` : The payment gateway used to tender the tip, such as shopify_payments. Present only on tips.

`tip_payment_method` : The payment method used to tender the tip, such as Visa. Present only on tips.

`total_discount` : The total amount of the discount allocated to the line item in the shop currency. This field must be explicitly set using draft orders, Shopify scripts, or the API. Instead of using this field, Shopify recommends using.discount_allocations, which provides the same information.

`total_discount_set` : The total amount allocated to the line item in the presentment currency. Instead of using this field, Shopify recommends using discount_allocations, which provides the same information.

`discount_allocations` : An ordered list of amounts allocated by discount applications. Each discount allocation is associated with a particular discount application.
- amount: The discount amount allocated to the line in the shop currency.
- discount_application_index: The index of the associated discount application in the order's discount_applications list.
- amount_set: The discount amount allocated to the line item in shop and presentment currencies.

`origin_location` : The location of the line item’s fulfillment origin. This field is due to be deprecated. Consider using ' "FulfillmentOrder#assigned_location_id instead.
- id: The location ID of the line item’s fulfillment origin. Used by Shopify to calculate applicable taxes. This is not the ID of the location where the order was placed. You can use the FulfillmentOrder resource to determine the location an item will be sourced from.
- country_code: The two-letter code (ISO 3166-1 format) for the country of the item's supplier.
- province_code: The two-letter abbreviation for the region of the item's supplier.
- name: The name of the item's supplier.
- address1: The street address of the item's supplier.
- address2: The suite number of the item's supplier.
- city: The city of the item's supplier.
- zip: The zip of the item's supplier.

`duties` : A list of duty objects, each containing information about a duty on the line item.
