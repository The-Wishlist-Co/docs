
## Shipment

`created_at` -string($date-time)

`deliveryDate` - string($date-time)

`id` - string

`orderId` - string

`orderRef` - string

`shipmentProvider` - string

`shipmentRef` - string

`shipmentLines` - [shipment Lines](shipmentLine.md)

`shipmentStatus` - string - Enum:
[ DELIVERED, DELIVERED_LEFT_AT_SAFE_PLACE, DELIVERED_TO_NEIGHBOUR, DELIVERY_DEFERED, DELIVERY_FAILED, IN_TRANSIT, OUT_FOR_DELIVERY, PACKAGE_DAMAGED, PACKED, PICKED, READY_TO_SHIP, RETURNING_TO_WAREHOUSE, SHIPPED ]

`shippedDate` - string($date-time)

`trackingNumber` - string

`trackingUrl` -string

`updated_at` - string($date-time)
