
[Back to Home](index.md#welcome-to-the-wishlist)


# **Platform Generated Messages**

The Wishlist Platform is capable of providing some platform generated notification services related to  wishlists, price drop and low stock notifications.


***
- [**Platform Generated Messages**](#platform-generated-messages)
  - [**Customer Interaction**](#customer-interaction)
    -  [**Representations**](#representations)
  - [**Price Drop**](#price-drop)
  - [**Low Stock**](#low-stock)
  

## **Customer Interaction**

The Wishlist can capture all wishlist and wishlist item interactions such as creations, updates, deletions and purchses made by the customer (when a wishlist item is purchased.)  Each notification is then prepared based on the status of the event subscription that is defined by the store using the [*Event Subscription Resource*](eventcollectorAPI.md#event-subscription-resource) API.

## <font size="3">Representations</font>
 All requests or responses are JSON objects.

 ```id``` - string - A unique identifier for the customer interaction.

 ```created_at``` - The date and time (ISO 8601 format) when the customer interaction was created.

  ```customerId``` - string -A unique identifier for the customer.

  ```customerRef``` - string -A unique Reference number for the customer.

  ```deleted``` -  To indicate the customer interaction is deleted or not.
- 0 - Represents FALSE
- 1 - Represents TRUE 

```disableNotification``` - To indicate the customer Notifications is disabled or not.
- 0 - Represents FALSE
- 1 - Represents TRUE

```entityType``` - String - Represents product is based on Wishlist or Wishlist item.

```interactionType``` - string - Represents the type of interaction.
- CREATED
- CHANGED
- DELETED
- PURCHASED

```itemId``` - String - Represents either wishlist ID or wishlistItem ID based on the entity Type.
  - If Entity Type is Wishlist then Item ID is wishlist ID . 
  - If Entity Type is wishlist Item then Item ID is wishlist Item ID.
  
```prerelease``` - To indicate the Product is pre-released or not.
- 0 - Represents FALSE
- 1 - Represents TRUE

```productId``` - string - the unique id of the product.

```productRef``` - string - the unique ref of the product.

```purchased```  - To indicate the wishlist item is purchased to not.
- 0 - Represents FALSE
- 1 - Represents TRUE

```tenantId``` - string - Represents Tenant ID.

```variantId``` - string - The unique id of the product variant.

```varientAttributes``` - string - Represents variant Attributes like color, size.

```wishlistId``` - string - the unique id of the respective wishlist.

## **Price Drop**

The Wishlist generates notifications when a price drop occurs on a product in the customer wishlists.

## **Low Stock**
The Wishlist generates notifications based on low stock level for each product in the customer wishlist.
The retailer defines a low-stock level. 

## **Back in Stock**
The Wishlist generates notifications based on an item that was previously out of stock now being back in stock.

[Back to Top](#platform-generated-messages)  

[Back to Home](index.md#welcome-to-the-wishlist)


 
