
[Back to Home](index.md#welcome-to-the-wishlist)


# **Platform Generated Messages**

The TWC Platform is capable of providing some platform generated messaging services  such as wishlists, price drop and low stock notifications based on subscription.


***
- [**Platform Generated Messages**](#platform-generated-messages)
  - [**Customer Interaction**](#customer-interaction)
    -  [**Representations**](#representations)
  - [**Price Drop**](#price-drop)
  - [**Low Stock**](#low-stock)
  

## **Customer Interaction**

The TWC system is capable of capturing all wishlist and wishlist item interactions such as creations, updations and deletions and purchses made by the customer.
Each notification is then prepared based on the status of the event subscription
that is defined by the store using this [*Event Subscription Resource*](eventcollectorAPI.md#event-subscription-resource) API.

## <font size="3">Representations</font>
 All representations are JSON objects submitted or received as payload to API requests or responses.

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

```salePrice``` - BigDicemal - variant sales price.

```price``` - BigDicemal - variant  price.

```storeId``` - String - storeId .

```customerEmail``` - String - customeremail .




## **Price Drop**

The TWC system generates notifications based on  price drop for each product in the customer wishlist.

## **Low Stock**
The TWC system generates notifications based on low stock level for each product in the customer wishlist.
The freaquency of this notifications is based on the depleating amount of stock.


[Back to Top](#platform-generated-messages)  

[Back to Home](index.md#welcome-to-the-wishlist)


 
