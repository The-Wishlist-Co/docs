
[Back to Home](index.md#welcome-to-the-wishlist)


# **Platform Generated Messages**

The TWC Platform is capable of providing some platform generated messaging services  such as wishlists, price drop and low stock notifications based on subscription.


***
- [**Platform Generated Messages**](#platform-generated-messages)
  - [**Customer Interaction**](#customer-interaction)
  - [**Price Drop**](#price-drop)
  - [**Low Stock**](#low-stock)
  

## **Customer Interaction**

The TWC system is capable of capturing all wishlist and wishlist item interactions such as creations, updations and deletions made by the customer.
Each notification is then prepared based on the status of the event subscription
that is defined by the store using this [*Event Subscription Resource*](eventcollectorAPI.md#event-subscription-resource) API.


## **Price Drop**

The TWC system generates price drops notification for each customer's product wishlist 

Notification generates for customer whos accepts marketing promotions

Currenltly price drop is defined as a schduler and runs every 10 min and reads the from price-drop-details where notification sent flag false.

system generates notification messages at once for all wishlist items of customer after that updates below data price-drop-detials table and sends the notification message to queue

## Price Drop Details
`new_sale_price` - number - new sale price for varient.

`notification_sent` - boolean - notfication sent flag.

`old_sale_price` - number -sale price for product when customer add in the  wishlist .

`productvariantId` - product varient.

`new_price` - new price for product varient. 

`old_price` - old product for varient.





[Sample Payload](PriceDrop/priceDropEventNotificationMessage.md#example-applicationjson)

[Payload Schema](PriceDrop/priceDropEventPayloadSchema.md)



## **Low Stock**
The TWC system generates Low Stock notification for each customer's product wishlist 

Notification generates for customer whos accepts marketing promotions

Currenltly Low stock is defined as a schduler and runs every 10 min and reads the from low-stock-details where notification sent flag false.

system generates notification messages at once for all wishlist items of customer after that updates below data low-stock-details table and sends the notification message to queue

`notification_sent` - boolean - notfication sent flag.


[Sample Payload](LowStock/lowStockEventNotificationMessage.md#example-applicationjson)

[Payload Schema](LowStock/lowStockEventPayloadSchema.md)






[Back to Top](#platform-generated-messages)  

[Back to Home](index.md#welcome-to-the-wishlist)


 
