## Order Line

`appliedDiscounts` - [discounts](appliedDiscounts.md)

`basePrice`	- number - Base price of the item.

`basePriceExTax` - number - Base price of the item excluding tax.

`basePriceExTaxInCent` - number - Base price of the item excluding tax in cents.

`basePriceInCent` - number - Base price of the item in cents.

`basePriceIncTax` - number - Base price of the item including tax.

`basePriceIncTaxInCent` - number - Base price of the item including tax in cents.

`cancelledAt`	- The date and time (ISO 8601 format) when the order line was cancelled. 

`created_at` - The date and time (ISO 8601 format) when the order line was created. 

`entryRef` - string

`gtin` - string - Global Trade Item Number (GTIN) can be used by a company to uniquely identify all of its trade items. 

`id` - string - Unique TWC identifier of the order line.

`orderId`- string - Unique TWC identifier for the order.

`orderRef` - string - Unique customer reference for the order.

`processedAt` - The date and time (ISO 8601 format) when an order was processed. This value is the date that appears on your orders and that's used in the analytic reports. If you're importing orders from an app or another platform, then you can set processed_at to a date and time in the past to match when the original order was created.

`productId` - string - Unigue id of the product.

`productRef` - string - Unigue Ref of the product.

`quantity` - integer - Quantity of the product in the order line. 

`refundAmount` - number - Amount that is returned as a refund.

`refundAmountInCent` - integer - Amount that is returned as a refund in cents.

`returnId` - integer - Unique id of the order line being returned. 

`returnedAt` - The date and time (ISO 8601 format) when an order line was returned. 

`returnedQuantity` - integer - Quantity of the product being returned. 

`shippedQuantity` - integer - Quantity of the product being shipped. 

`totalAmount` - number

`totalAmountBeforeDiscount`	- number

`totalAmountBeforeDiscountInCent` - integer

`totalAmountExTax` - number

`totalAmountInCent` - integer

`totalAmountIncTax`	- number

`totalAmountIncTaxInCent` - integer

`updated_at` - he date and time (ISO 8601 format) when an order was returned. 
