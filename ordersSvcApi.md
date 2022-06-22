
# **Order Svc API**
An order is a customer's request to purchase one or more products from a shop. You can create, retrieve, update, and delete orders using the Order resource.



## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.

<!-- <details> -->
 <!-- <summary><font size="4">Import Batch Resource</font></summary> -->

`acceptsMarketing` - boolean - option to enable of disable marketing notifications.

`appliedDiscounts` - [applied discounts](Common_Fields/appliedDiscounts.md) - array - All discounds and applicable promotional offers etc are enabled here. This contains :

`appliedTaxes` - array - All applicable taxes are enabled here. This contains :

- `amount` -   
- `amountInCent` -  
- `taxCode` - string
- `taxRate` -
- `id` - string
- `name` - string

`attributeGroups` - array -additional required properties hat are not present by default are enabled here. Refer swagger documentation for detailed more information on internal structure.

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

- ## **Impex Batch Resource**


