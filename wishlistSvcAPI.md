
[Back to Home](index.md#welcome-to-the-wishlist)


# **Wishlist API**
The Wishlist API enables the management of customer wishlists.  

In most situations, The Wishlist platform will be the master data source for Wishlists, as it is able to manage wishlist information from multiple sources (e.g. website or physical stores); then trigger events based on saved wishlist items; and send wishlist information to 3rd party systems such as marketing automation platforms like Emarsys, Klaviyo and DotDigital.  

One customer may have mulitple wishlists.  You can only create a wishlist for a valid customer.

A wishlist is created 'empty' and items added later, either one by one, or multiple items can be added at the same time.


***

[**Wishlist API**](#wishlist-api)
- [**Wishlist API**](#wishlist-api)
  - [**General Notes**](#general-notes)
  - [**Representations**](#representations)
    - [Wishlist Request](#wishlist-request)
    - [Wishlist Response](#wishlist-response)
    - [WishlistItem Request](#wishlistitem-request)
    - [WishlistItem Product](#wishlistitem-product)
    - [AttributeGroups](#attributegroups)
    - [AttributeGroup](#attributegroup)
    - [WishlistItem Response](#wishlistitem-response)
- [**Endpoints**](#endpoints)
  - [**Wishlist**](#wishlist)
    - [Ceate a wishlist](#ceate-a-wishlist)
  - [Update a wishlist](#update-a-wishlist)
    - [Update Wishlist By ID](#update-wishlist-by-id)
    - [Update Wishlist By Ref](#update-wishlist-by-ref)
    - [Update wishlist by either ID or Ref](#update-wishlist-by-either-id-or-ref)
  - [GET Wishlist](#get-wishlist)
    - [Get Wishlist by Id](#get-wishlist-by-id)
    - [Get Wishlist by Wishlist Reference](#get-wishlist-by-wishlist-reference)
    - [Get Wishlist by id/wishlistRef](#get-wishlist-by-idwishlistref)
  - [Get customer wishlists](#get-customer-wishlists)
  - [Delete Wishlist](#delete-wishlist)
    - [Delete Wishlist by ID/Ref](#delete-wishlist-by-idref)
  - [Delete Wishlist by ID](#delete-wishlist-by-id)
    - [Delete Wishlist by Ref](#delete-wishlist-by-ref)
  - [Get wishlist interactions](#get-wishlist-interactions)
- [**WishlistItem**](#wishlistitem)
  - [Create a Wishlist Item](#create-a-wishlist-item)
  - [Add multple Wishlist Items](#add-multple-wishlist-items)
  - [Update WishlistItems](#update-wishlistitems)
    - [Update a Wishlist Item](#update-a-wishlist-item)
    - [Update a Wishlist Item By Ref](#update-a-wishlist-item-by-ref)
    - [Update a Wishlist Item By Id](#update-a-wishlist-item-by-id)
  - [Get Wishlist Items](#get-wishlist-items)
    - [Get all Items in a Wishlist by Wishlist Id](#get-all-items-in-a-wishlist-by-wishlist-id)
    - [Get Wishlist Item by Item Id](#get-wishlist-item-by-item-id)
    - [Get Wishlist Item by Item Ref](#get-wishlist-item-by-item-ref)
  - [Delete Wishlist Item](#delete-wishlist-item)
    - [Delete Wishlist Item by Id](#delete-wishlist-item-by-id)
    - [Delete Wishlist Item by itemRef](#delete-wishlist-item-by-itemref)

## **General Notes**
Wishlist endpoints must be prefixed with ```/services/wsservice``` for example create customer endpoint is ```/api/wishlists```, when you invoke the api it will be ```/services/wsservice/api/wishlists```

Production api endpoint ```https://api.au-aws.thewishlist.io/services/wsservice/api/wishlists```

## **Representations**

All requests or responses are JSON objects

### Wishlist Request

| Field | Type | Description |
|---|---|---|
| *customerId* | string | TWC generated unique customer identifier. Either customerId or customerRef is mandatory when creating a wishlist |
| *customerRef* | string | Retailer's own unique customer identifier. Either customerId or customerRef is mandatory when creating wishlist |
| *description* | string | Wishlist description.  This field is optional. It may be useful in social shopping scenarios |
| *name* | string | The Wishlist name provided by the customer |
| *wishlistRef* | string | This is an optional reference identifier given to the wishlist by the retailer. This field may be used to GET/UPDATE/DELETE the wishlist.  It is likely most useful for integrating with existing ecommerce wishlist systems. |
| *isPrivate* | boolean | Indicates the wishlist is private to customer |
| *attributeGroups* |[AttributeGroups](#attributegroups)| This field may be used to add additional attributes to the wishlist. This field is in general available on most entitiesin The Wishlist platform.<br> "attributeGroups":&nbsp;{<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"wishlist_origin":&nbsp;"app",<br>&emsp;&emsp;"ecommerce_wishlist_id":&nbsp;"ecommerce&nbsp;system&nbsp;generated&nbsp;id",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;wishlist"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>}<br> |


### Wishlist Response

| Field | Type | Description |
|---|---|---|
| *id* | string | TWC generated unique wishlist identifier.|
| *customerId* | string | TWC unique customer identifier.|
| *customerRef* | string | Retailer's own unique identifier of customer.|
| *description* | string | Wishlist description.|
| *name* | string | Wishlist name provided by the customer |
| *wishlistRef* | string | This is a reference identifier given to a wishlist by retailer. This field may be used to GET/UPDATE/DELETE the wishlist.  It is likely most useful when integrating to existing ecoommerce wishlist systems. |
| *isPrivate* | boolean | Indicates the wishlist is private to customer |
| *attributeGroups* |[AttributeGroups](#attributegroups)| This field may be used to add additional attributes to the wishlist. This field is in general available on most entitiesin The Wishlist platform.<br> "attributeGroups":&nbsp;{<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"wishlist_origin":&nbsp;"app",<br>&emsp;&emsp;"ecommerce_wishlist_id":&nbsp;"ecommerce&nbsp;system&nbsp;generated&nbsp;id",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;wishlist"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>}<br> |


###  WishlistItem Request

| Field | Type | Description |
|---|---|---|
| *addedFromCart* | boolean | Indicates the item was added from cart.  Developers should set this flag if the item was added to the wishlist directly fom the shopping cart (this is considered an 'interaction' in The Wishlist reporting dashboards |
| *disableNotification* | boolean| Disable notifications for this wishlist item. |
| *wishlistId* | string | TWC generated unique identifier for the wishlist to which the item is being added. Either wishlistId or wishlistRef is mandatory when creating a wishlist item. |
| *wishlistRef* | string | The reatailer assigned unique reference identifier for the wishlist. Either wishlistId or wishlistRef is mandatory when creating a wishlist item. |
| *wishlistItemRef* | string | Retailer assigned unique reference identifier of the wishlist item. |
| *prerelease* | boolean | Indicates that the customer is registering interest to a pre-released product.  Used in the Register Interest notification |
| *purchased* | boolean | Indicates that the item has been purchased.  Note, this field is for TWC internal use to track wishlist item conversions, and should not be updated directly by developers |
| *purchasedAndRemoved* | boolean | This parameter is used to differentiate and identify the wishlist items removed after sale conversions. This can be set manually or automated based on a configuration. |
| *product* | [Product](#wishlistitem-product) | Represents the item [product](#wishlistitem-product). This is a mandatory field. |
| *attributeGroups* | [AttributeGroups](#attributegroups) | This field may be used to add additional attributes to the wishlist. This field is in general available on most entitiesin The Wishlist platform.<br> "attributeGroups":&nbsp;{<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"wishlist_item_origin":&nbsp;"mobile_app",<br>&emsp;&emsp;"ecommerce_wishlist_item_id":&nbsp;"ecommerce&nbsp;system&nbsp;generated&nbsp;id",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;wishlist"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>}<br> |

###  WishlistItem Product

| Field | Type| Description |
|---|---|---|
| *productId* | string| This is the TWC generated product identifier. Either productId or productRef is mandatory when creating a wishlist item.|
| *productRef* | string | This is the retailer assigned product reference identifier. Either productId or productRef is mandatory when creating a wishlist item.  Please note that TWC does not validate the existance of a product when adding to the Wishlist.  This allows you to add an item that may not have yet been synched to the product catalogue.  However, notifications will not trigger if a product/variant does not exist.|
| *selectedVariantId* | string | This is the TWC assigned variant identifier. Either selectedVariantId or selectedVariantRef is mandatory when creating a wishlist item.|
| *selectedVariantRef* | string | This is the retailer assigned variant reference identifier. Either selectedVariantId or selectedVariantRef is mandatory when creating a wishlist item.  Please note that TWC does not validate the existance of a variant when adding to the Wishlist.  This allows you to add an item that may not have yet been synched to the product catalogue.  However, notifications will not trigger if a product/variant does not exist.|
| *oldVariantId* | string | When updating a wishlist item to another variant oldVariantId field is mandatory, to switch to another variant. This is TWC generated unique identifier.|

###  AttributeGroups

| Field | Type| Description |
|---|---|---|
| *attributeGroup* | [AttributeGroup](#attributegroup) | This field holds the groups of attributes as a map of <String, [AttributeGroup](#attributegroup)>. <br> e.g.: {<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"wishlist_origin":&nbsp;"app",<br>&emsp;&emsp;"ecommerce_wishlist_id":&nbsp;"ecommerce&nbsp;system&nbsp;generated&nbsp;id",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;wishlist"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>} |

###  AttributeGroup

| Field | Type| Description |
|---|---|---|
| *attributes* | map | This field holds map of attributes as a map of <string, string> <br> e.g.: {<br>&emsp;&emsp;"wishlist_origin":&nbsp;"app",<br>&emsp;&emsp;"ecommerce_wishlist_id":&nbsp;"ecommerce&nbsp;system&nbsp;generated&nbsp;id",&emsp;&emsp;<br>&emsp;&ensp;} |
| *description* | string | This field is a short description about the attributes captured under field *attributes*. This will only be used in the backoffice tools. |

###  WishlistItem Response

| Field | Type | Description |
|---|---|---|
| *id* | string | This is the TWC generted unique identifier for the wishlist item.|
| *addedFromCart* | boolean | Indicates the item was added from a shopping cart.|
| *disableNotification* | boolean | Disable notifications for this wishlist item.|
| *wishlistId* | string | TWC generated unique identifier of wishlist, to which the item is being added. Either wishlistId or wishlistRef is mandatory when creating a wishlist item.|
| *wishlistRef* | string | reatailer assigned unique identifier for the wishlist. Either wishlistId or wishlistRef is mandatory when creating a wishlist item.|
| *wishlistItemRef* | string | reatailer assigned unique identifier for the wishlist item.|
| *prerelease* | boolean | Indicates that customer is registering interest to a pre release item.  Used in the register interest notification|
| *purchased* | boolean | Indicates that the item has been purchased.|
| *purchasedDate* | boolean | The date on which item was purchased. If orders are pushed to TWC, TWC will mark the item as purchased.|
| *product* |[Product](#wishlistitem-product)| This field represents the field being added to item [product](#wishlistitem-product)|
| *attributeGroups* | object | This field may be used to add additional attributes to the wishlist. This field is in general available on most entitiesin The Wishlist platform.<br> "attributeGroups":&nbsp;{<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"wishlist_item_origin":&nbsp;"mobile_app",<br>&emsp;&emsp;"ecommerce_wishlist_item_id":&nbsp;"ecommerce&nbsp;system&nbsp;generated&nbsp;id",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;wishlist"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>}<br>|


# **Endpoints**

## **Wishlist**

### Ceate a wishlist

Creates a new wishlist. This API requires wishlist request to be passed to API. The Customer must be created before creating their wishlist(s).

| Endpoint| ```/api/wishlists```|
|-----------|---------------|
| Method    | POST          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

Sample Request:
```json
{
  "attributeGroups": {
    "extra_attribute_group1": {
      "attributes": {
        "wishlist_origin": "app",
        "ecommerce_wishlist_id": "ecommerce system generated id",        
      },
      "description": "any additional attribute you want to add to wishlist"
    },
    "retailer_defined_name_of_group": {
      "attributes": {
        "retailer_defined_attribute1": "user defined attribute value",
        "another_attribute": "another value"
      },
      "description": "retailer defined properties and its values, flexible data model to add additional properties."
    }
  },
  "customerId": "twc-generated-customer-id", //either customerId or customerRef is mandatory
  "customerRef": "retailers_customer_id",
  "description": "wishlists description", // This field may not be used for private wishlist scenario. This field however may be key in a social shopping scenario.
  "isPrivate": "true", //marking the wishlist private. not a mandatory field.
  "name": "wishlist name",
  "wishlistRef": "retailers wishlist id" // this is not a mandatory field. However, if set could be used to GET/UDPATE/DELETE wishlist using this reference Id.
}
```

<summary>Response - 201 (created)</summary>

```json
{
    "id": "2cd4e650-8f00-4d13-ba46-831c2cf29211",
    "wishlistRef": "1111111",
    "name": "An awesome wishlist",
    "customerId": "93847020-4c74-4239-9310-58d1c91cc1a7",
    "customerRef": "CUSTOMER1234",
    "deleted": false,
    "createdTime": "2023-05-01T00:02:38.048171Z",
    "modifiedTime": "2023-05-01T00:02:38.048174Z",
    "attributeGroups": {
        "pos_attributes": {
            "description": "POS related wishlist information",
            "attributes": {
                "created_in": "POS",
                "staff_id": "STAFF111",
                "POS_ref": "POS12341234",
                "store_id": "STORE111"
            }
        }
    }
}
```

HTTP Status Code:
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Update a wishlist

### Update Wishlist By ID
T
his API uses the TWC generated identifier to update metadata about a wishlist, for example, attribute groups, staff/store ID or wishlist name.  *Note this API is NOT used to update the items on the wishlist.*

As this API uses TWC Wishlist ID, then you can use it to update the wishlistRef (the retailer's own wishlit unique identifier).   

Endpoint: ```/api/wishlists/id={id}```


| Endpoint| ```/api/wishlists/id={id}``` |
|-----------|---------------|
| Method    | PUT          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```id``` This is the TWC generated unique identifier for the wishlist being updated. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|


Sample Request:

<!--  -->
```json
{
  "id": "2cd4e650-8f00-4d13-ba46-831c2cf29211",
  "attributeGroups": {
    "extra_attribute_group1": {
      "attributes": {
        "wishlist_origin": "app",
        "ecommerce_wishlist_id": "ecommerce system generated id",        
      },
      "description": "any additional attribute you want to add to wishlist"
    },
    "retailer_defined_name_of_group": {
      "attributes": {
        "retailer_defined_attribute1": "user defined attribute value",
        "another_attribute": "another value"
      },
      "description": "retailer defined properties and its values, flexible data model to add additional properties."
    }
  },
  "wishlistRef": "17949",
  "name": "Test wishlist 17949 creation",
  "customerId": "93847020-4c74-4239-9310-58d1c91cc1a7",
  "customerRef": "CUST16003",
  "deleted": false,
  "createdTime": "2023-05-01T00:02:38.048171Z",
}
```
<!--  -->

<summary>Response - 200 (OK Updated)</summary>

```json
{
  "id": "2cd4e650-8f00-4d13-ba46-831c2cf29211",
  "attributeGroups": {
    "extra_attribute_group1": {
      "attributes": {
        "wishlist_origin": "app",
        "ecommerce_wishlist_id": "ecommerce system generated id",        
      },
      "description": "any additional attribute you want to add to wishlist"
    },
    "retailer_defined_name_of_group": {
      "attributes": {
        "retailer_defined_attribute1": "user defined attribute value",
        "another_attribute": "another value"
      },
      "description": "retailer defined properties and its values, flexible data model to add additional properties."
    }
  },
  "wishlistRef": "17949",
  "name": "Test wishlist 17949 creation",
  "customerId": "93847020-4c74-4239-9310-58d1c91cc1a7",
  "customerRef": "CUST16003",
  "deleted": false,
  "createdTime": "2023-05-01T00:02:38.048171Z",
}
```

HTTP Status Code:
``` 
- 200 OK
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
- 400 Invalid input
```

### Update Wishlist By Ref

Used to update the metadata about a wishlist, for example, attribute groups, staff/store ID or wishlist name, using the retailer's own unique wishlist identifier.  *Note this API is NOT used to update items on the wishlist.*

| Endpoint| ```/api/wishlists/ref={ref}``` |
|-----------|---------------|
| Method    | PUT          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```ref``` This is the retailers reference identifier for the wishlist being updated |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

Sample Request:

<!--  -->
```json
{
  "id": "2cd4e650-8f00-4d13-ba46-831c2cf29211",
  "attributeGroups": {
    "extra_attribute_group1": {
      "attributes": {
        "wishlist_origin": "app",
        "ecommerce_wishlist_id": "ecommerce system generated id",        
      },
      "description": "any additional attribute you want to add to wishlist"
    },
    "retailer_defined_name_of_group": {
      "attributes": {
        "retailer_defined_attribute1": "user defined attribute value",
        "another_attribute": "another value"
      },
      "description": "retailer defined properties and its values, flexible data model to add additional properties."
    }
  },
  "wishlistRef": "17949",
  "name": "Test wishlist 17949 creation",
  "customerId": "93847020-4c74-4239-9310-58d1c91cc1a7",
  "customerRef": "CUST16003",
  "deleted": false,
  "createdTime": "2023-05-01T00:02:38.048171Z",
}
```
<!--  -->

<summary>Response - 200 (OK Updated)</summary>

```json
{
  "id": "2cd4e650-8f00-4d13-ba46-831c2cf29211",
  "attributeGroups": {
    "extra_attribute_group1": {
      "attributes": {
        "wishlist_origin": "app",
        "ecommerce_wishlist_id": "ecommerce system generated id",        
      },
      "description": "any additional attribute you want to add to wishlist"
    },
    "retailer_defined_name_of_group": {
      "attributes": {
        "retailer_defined_attribute1": "user defined attribute value",
        "another_attribute": "another value"
      },
      "description": "retailer defined properties and its values, flexible data model to add additional properties."
    }
  },
  "wishlistRef": "17949",
  "name": "Test wishlist 17949 creation",
  "customerId": "93847020-4c74-4239-9310-58d1c91cc1a7",
  "customerRef": "CUST16003",
  "deleted": false,
  "createdTime": "2023-05-01T00:02:38.048171Z",
}
```

HTTP Status Code:
``` 
- 200 OK
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
- 400 Invalid input
```

### Update wishlist by either ID or Ref

Used to update any metadata about a wishlist, for example, attribute groups, staff/store ID or wishlist name.  *This API is NOT used to update items on the wishlist*  You can update by internal Wishlist ID or wishlistRef (the retailer's unique wishlist identifier).   

**THIS API IS DEPRECIATED.  PLEASE USE UDATE WISHLIST BY ID OR WISHLISTREF**

| Endpoint| ```/api/wishlists```|
|-----------|---------------|
| Method    | PUT          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
|How to get access token| [Tenant Authentication](authenticationsvcApi.md)|

Sample Request:

<!--  -->
```json
{
  "id":"twc-generated-wishlist-id", // Either id or wishlistRef is mandatory to update a wishlist using this service.
  "attributeGroups": {
    "extra_attribute_group1": {
      "attributes": {
        "wishlist_origin": "app",
        "ecommerce_wishlist_id": "ecommerce system generated id",        
      },
      "description": "any additional attribute you want to add to wishlist"
    },
    "retailer_defined_name_of_group": {
      "attributes": {
        "retailer_defined_attribute1": "user defined attribute value",
        "another_attribute": "another value"
      },
      "description": "retailer defined properties and values, flexible data model to add additional properties."
    }
  },
  "customerId": "twc-generated-customer-id", //either customerId or customerRef is mandatory
  "customerRef": "retailers_customer_id",
  "description": "wishlists description", // This field may be useful in a social shopping scenario.
  "isPrivate": "true", //marking the wishlist private. not a mandatory field.
  "name": "wishlist name",
  "wishlistRef": "retailers wishlist id" // Either id or wishlistRef is mandatory to update a wishlist using this service.
}
```
<!--  -->

<summary>Response - 200 (OK Updated)</summary>

```json
{
  "id": "2cd4e650-8f00-4d13-ba46-831c2cf29211",
  "attributeGroups": {
    "extra_attribute_group1": {
      "attributes": {
        "wishlist_origin": "app",
        "ecommerce_wishlist_id": "ecommerce system generated id",        
      },
      "description": "any additional attribute you want to add to wishlist"
    },
    "retailer_defined_name_of_group": {
      "attributes": {
        "retailer_defined_attribute1": "user defined attribute value",
        "another_attribute": "another value"
      },
      "description": "retailer defined properties and values, flexible data model to add additional properties."
    }
  },
  "wishlistRef": "17949",
  "name": "Test wishlist 17949 creation",
  "customerId": "93847020-4c74-4239-9310-58d1c91cc1a7",
  "customerRef": "CUST16003",
  "deleted": false,
  "createdTime": "2023-05-01T00:02:38.048171Z",
}
```

<summary>HTTP Status Codes </summary>

``` 
- 200 OK
- 400 Bad request
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


## GET Wishlist

Below APIs provide mechanisms to get wishlists by internal TWC identifier, retailer's reference identifier or by customer. 

### Get Wishlist by Id

Returns the wishlist that matches the given internal TWC Platform identifier, along with the wishlist items.

The returned item array is paginated - 20 default (50 maximum).  The API will respond with the item count in the page, and the itemID the for the last item (lastitemID) returned for that response, which should then be used for the  subsequent API call to retrieve the next page.  

If the wishlist does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlists/{id}```|
|-----------|---------------|
| Method    | GET          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| Path variable | ```id``` TWC generated unique ID of the wishlist |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

| Query Parameters | What is it for ? |
|---|---|
| ```pageSize``` | Determines the number of wishlist items returned in the API response. Default page size is 20 and max is 50. |
| ```lastItemId``` | Determines which items to return. The API returns wishlist items in the ascending order of their TWC generated wishlist ID. This parameter will inform the API to respond with the items with an identifier greater than, but excluding the value provided. |

When provided with valid inputs, the API responds with a ```application/json``` type content.

<summary>sample response - 200 (OK)</summary>

```json
{
    "id": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
    "wishlistRef": "24639",
    "name": "Test wishlist 24639 creation",
    "customerId": "93847020-4c74-4239-9310-58d1c91cc1a7",
    "customerRef": "CUST16003",
    "deleted": false,
    "createdTime": "2023-05-01T02:37:00.543594Z",
    "modifiedTime": "2023-05-01T02:37:00.543597Z",
    "lastEvaluatedItemId": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
    "itemCount": 1,
    "wishlistItems": [
        {
            "id": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
            "wishlistItemRef": "WI200013716",
            "purchased": false,
            "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
            "product": {
                "productId": "ede20e6c-88c8-41d9-b0a5-a631871b23d2",
                "productRef": "100019951",
                "selectedVariantId": "5396d084-4346-44d2-9d87-b2015c1d7b42",
                "selectedVariantRef": "4690"
            },
            "createdTime": "2023-05-01T02:37:22.407387Z",
            "modifiedTime": "2023-05-01T02:37:22.407390Z",
            "attributeGroups": {
                "POS_attributes": {
                    "description": "POS related attidional information",
                    "attributes": {
                        "POS_ref": "POS001",
                        "store_id": "STORE001"
                    }
                }
            },
            "addedFromCart": false,
            "prerelease": false,
            "disableNotification": false
        }
    ],
    "attributeGroups": {
        "POS_attributes": {
            "description": "POS related attidional information",
            "attributes": {
                "STAFF_ID": "STAFF001",
                "POS_ref": "POS001",
                "store_id": "STORE001"
            }
        }
    }
}
```        

The API responds with below statuses. HTTP status differ depending on the input, access token etc.

<summary>HTTP Status Codes </summary>

``` 
- 200 OK
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


### Get Wishlist by Wishlist Reference

Returns the wishlist that matches the provided wishlistRef (which is the retailer's own wishlist identifier), along with the wishlist items.

The returned item array is paginated - 20 default (50 maximum).  The API will respond with the item count in the page, and the itemID the for the last item (lastitemID) returned for that response, which should then be used for the  subsequent API call to retrieve the next page.  

If the wishlist does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlists/{wishlistRef}/byref``` |
|-----------|---------------|
| Method    | GET          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| Path variable | ```wishlistRef``` retailer assigned reference id of wishlist |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

| Query Parameters | What is it for ? |
|---|---|
| ```pageSize``` | Determines the number of wishlist items returned in the API response. Default page size is 20 and max is 50. |
| ```lastItemId``` | Determines which items to return.  The API returns wishlist items in the ascending order of their TWC generated wishlist ID. This parameter will inform the API to respond with items with ID greater than, but excluding the provided value. |

When provided with valid inputs, API responds with a ```application/json``` type content.

<summary>sample response - 200 (OK)</summary>

```json
{
    "id": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
    "wishlistRef": "24639",
    "name": "Test wishlist 24639 creation",
    "customerId": "93847020-4c74-4239-9310-58d1c91cc1a7",
    "customerRef": "CUST16003",
    "deleted": false,
    "createdTime": "2023-05-01T02:37:00.543594Z",
    "modifiedTime": "2023-05-01T02:37:00.543597Z",
    "lastEvaluatedItemId": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
    "itemCount": 1,
    "wishlistItems": [
        {
            "id": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
            "wishlistItemRef": "WI200013716",
            "purchased": false,
            "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
            "product": {
                "productId": "ede20e6c-88c8-41d9-b0a5-a631871b23d2",
                "productRef": "100019951",
                "selectedVariantId": "5396d084-4346-44d2-9d87-b2015c1d7b42",
                "selectedVariantRef": "4690"
            },
            "createdTime": "2023-05-01T02:37:22.407387Z",
            "modifiedTime": "2023-05-01T02:37:22.407390Z",
            "attributeGroups": {
                "POS_attributes": {
                    "description": "POS related attidional information",
                    "attributes": {
                        "POS_ref": "POS001",
                        "store_id": "STORE001"
                    }
                }
            },
            "addedFromCart": false,
            "prerelease": false,
            "disableNotification": false
        }
    ],
    "attributeGroups": {
        "POS_attributes": {
            "description": "POS related attidional information",
            "attributes": {
                "STAFF_ID": "STAFF001",
                "POS_ref": "POS001",
                "store_id": "STORE001"
            }
        }
    }
}
```        

The API responds with below statuses. HTTP status differ depending on the input, access token etc.

<summary>HTTP Status Codes </summary>

``` 
- 200 OK
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


### Get Wishlist by id/wishlistRef

Retrieves the wishlist and the wishlist items that belongs to the given Id and/or wishlistRef.  If the wishlist does not exist, this method returns a ResourceNotFound error.

The returned item array is paginated - 20 default (50 maximum).  The API will respond with the item count in the page, and the itemID the for the last item (lastitemID) returned for that response, which should then be used for the subsequent API call to retrieve the next page.  

| Endpoint| ```/api/wishlists/```|
|-----------|---------------|
| Method    | GET          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

| Query Parameters | What is it for ? |
|---|---|
| ```id``` | This is the TWC system generated unique wishlist identifier. e.g: ```67ccc612-0f1b-4d9d-b69e-d43511c6782d```. The API will query the database for wishlists by ID. |
| ```wishlistRef``` | This is the retailer assigned unique wishlist reference identifier. e.g: ```WISH0001```. The API will query the database  for wishlists by reference value. |
| ```pageSize``` | Determines the number of wishlist items returned in the API response. Default page size is 20 and max is 50. |
| ```lastItemId``` | Determines which items to return. API returns wishlist items in the ascending order of their TWC generated wishlist ID. This parameter will inform the API to respond with items that have ID greater than, but excluding the value provided. |

When provided with valid inputs, API responds with a ```application/json``` type content.

<summary>sample response - 200 (OK)</summary>

```json
{
    "id": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
    "wishlistRef": "24639",
    "name": "Test wishlist 24639 creation",
    "customerId": "93847020-4c74-4239-9310-58d1c91cc1a7",
    "customerRef": "CUST16003",
    "deleted": false,
    "createdTime": "2023-05-01T02:37:00.543594Z",
    "modifiedTime": "2023-05-01T02:37:00.543597Z",
    "lastEvaluatedItemId": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
    "itemCount": 1,
    "wishlistItems": [
        {
            "id": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
            "wishlistItemRef": "WI200013716",
            "purchased": false,
            "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
            "product": {
                "productId": "ede20e6c-88c8-41d9-b0a5-a631871b23d2",
                "productRef": "100019951",
                "selectedVariantId": "5396d084-4346-44d2-9d87-b2015c1d7b42",
                "selectedVariantRef": "4690"
            },
            "createdTime": "2023-05-01T02:37:22.407387Z",
            "modifiedTime": "2023-05-01T02:37:22.407390Z",
            "attributeGroups": {
                "POS_attributes": {
                    "description": "POS related attidional information",
                    "attributes": {
                        "POS_ref": "POS001",
                        "store_id": "STORE001"
                    }
                }
            },
            "addedFromCart": false,
            "prerelease": false,
            "disableNotification": false
        }
    ],
    "attributeGroups": {
        "POS_attributes": {
            "description": "POS related attidional information",
            "attributes": {
                "STAFF_ID": "STAFF001",
                "POS_ref": "POS001",
                "store_id": "STORE001"
            }
        }
    }
}
```        
      
<summary>HTTP Status Code:</summary>

``` 
- 200 OK
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


## Get customer wishlists

Returns the collection of wishlists that belong to either the internal TWC customer identifier, or the retailer's own customerRef.

The returned list is paginated - 20 default (50 maximum).  The API will respond with the number of wishlists returned in the page, and the wishlistID for the for the last wishlist returned for that response, which should then be used for the subsequent API call to retrieve the next page.  

If no wishlists exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlists/lookup```|
|-----------|---------------|
| Method    | GET          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

| Query Parameters | What is it for ? |
|---|---|
| ```customerId``` | This is the TWC generated unique customer identifier. e.g: ```67ccc612-0f1b-4d9d-b69e-d43511c6782d```. API will query database for wishlists that belong to customer with the given ID. |
| ```customerRef``` | This is the retailer assigned unique customer reference identifier. e.g: ```CUST1111```. API will query database for wishlists that belong to customer with the given reference value. |
| ```pageSize``` | Determines the number of wishlist items returned in the API response. Default page size is 20 and max is 50. |
| ```lastItemId``` | Determinse which items to return.  API returns wishlist items in the ascending order of their TWC generated wishlist ID. This parameter will inform API to respond items with ID greater than, but excluding the value provided. |

<summary>Response - 200 (OK)</summary>

```json
{
    "wishlistCount": 2,
    "lastEvaluatedWishlistId": "2cd4e650-8f00-4d13-ba46-831c2cf29211",
    "wishlist": [
        {
            "id": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
            "wishlistRef": "24639",
            "name": "Test wishlist 24639 creation",
            "customerId": "93847020-4c74-4239-9310-58d1c91cc1a7",
            "customerRef": "CUST16003",
            "deleted": false,
            "createdTime": "2023-05-01T02:37:00.543594Z",
            "modifiedTime": "2023-05-01T02:37:00.543597Z",
            "lastEvaluatedItemId": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
            "itemCount": 1,
            "wishlistItems": [
                {
                    "id": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
                    "wishlistItemRef": "WI200013716",
                    "purchased": false,
                    "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
                    "product": {
                        "productId": "ede20e6c-88c8-41d9-b0a5-a631871b23d2",
                        "productRef": "100019951",
                        "selectedVariantId": "5396d084-4346-44d2-9d87-b2015c1d7b42",
                        "selectedVariantRef": "4690"
                    },
                    "createdTime": "2023-05-01T02:37:22.407387Z",
                    "modifiedTime": "2023-05-01T02:37:22.407390Z",
                    "attributeGroups": {
                        "POS_attributes": {
                            "description": "POS related attidional information",
                            "attributes": {
                                "POS_ref": "POS001",
                                "store_id": "STORE001"
                            }
                        }
                    },
                    "addedFromCart": false,
                    "prerelease": false,
                    "disableNotification": false
                }
            ],
            "attributeGroups": {
                "POS_attributes": {
                    "description": "POS related attidional information",
                    "attributes": {
                        "STAFF_ID": "STAFF001",
                        "POS_ref": "POS001",
                        "store_id": "STORE001"
                    }
                }
            }
        },
        {
            "id": "2cd4e650-8f00-4d13-ba46-831c2cf29211",
            "wishlistRef": "17949",
            "name": "Test wishlist 17949 creation",
            "customerId": "93847020-4c74-4239-9310-58d1c91cc1a7",
            "customerRef": "CUST16003",
            "deleted": false,
            "createdTime": "2023-05-01T00:02:38.048171Z",
            "modifiedTime": "2023-05-01T00:02:38.048174Z",
            "wishlistItems": [],
            "attributeGroups": {
                "POS_attributes": {
                    "description": "POS related attidional information",
                    "attributes": {
                        "STAFF_ID": "STAFF001",
                        "POS_ref": "POS001",
                        "store_id": "STORE001"
                    }
                }
            }
        }
    ]
}
```

<summary>HTTP Status Codes</summary>

``` 
- 200 OK
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


## Delete Wishlist

### Delete Wishlist by ID/Ref

Delete Wishlist marks the wishlist as deleted and produces an HTTP response confirming the action.  The Wishlist is identified either by the TWC Internal wishlist identifier or the retailers own wishlistRef.   The wishlists are actually retained in the system for reporting purposes, but are de-identified so cannot be linked back to the customer.

If the wishlist does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlists/```|
|-----------|---------------|
| Method    | DELETE          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

| Query Parameters | What is it for ? |
|---|---|
| ```id``` | This is the TWC system generated unique wishlist identifier. e.g: ```67ccc612-0f1b-4d9d-b69e-d43511c6782d```. API will remove the wishlists for the given ID.  Either ```id``` or ```wishlistRef``` must be provided with this API call.|
| ```wishlistRef``` | This is the retailers assigned unique wishlist reference identifier. e.g: ```WISH0001```. The API will remove the wishlists matching the given retailer wishlist reference ID.  Either ```id``` or ```wishlistRef``` must be provided with this API call.|

<summary>Response - 204 (Deleted)</summary> 

<summary>HTTP Status Code</summary> 

``` 
- 204 Deleted
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


## Delete Wishlist by ID

Delete Wishlist marks the matching wishlist as deleted and produces an HTTP response confirming the action.  In this case the Wishlist is identified by the TWC internal wishlist identifier.

If the wishlist does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlists/{id}```|
|-----------|---------------|
| Method    | DELETE          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

| Path Parameters | What is it for ? |
|---|---|
| ```id``` | This is the TWC system generated unique wishlist identifier. e.g: ```67ccc612-0f1b-4d9d-b69e-d43511c6782d```. API will remove the wishlists for the given TWC ID.|

<summary>Response - 204 (Deleted)</summary> 

<summary>HTTP Status Code</summary> 

``` 
- 204 Deleted
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


### Delete Wishlist by Ref

Delete Wishlist marks the matching wishlist as deleted and produces an HTTP response confirming the action.  In this case the Wishlist is identified by the retailer's wishlist identifer - wishlistRef.

If the wishlist does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlists/{wishlistRef}/byref```|
|-----------|---------------|
| Method    | DELETE          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

| Path Parameters | What is it for ? |
|---|---|
| ```wishlistRef``` | This is the retailer generated wishlist reference identifier. e.g: ```WISH1111```. The API will remove the wishlists for the given reference ID, if it exists. |

<summary>Response - 204 (Deleted)</summary> 

<summary>HTTP Status Code</summary> 

``` 
- 204 Deleted
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

## Get wishlist interactions

Returns the collection of wishlists interactions that belong to tenantId.

The returned list is paginated - 20 default (50 maximum).  The API will respond with the number of interactions returned in the page, and the interactionId for the  last interaction returned for that response, which should then be used for the subsequent API call to retrieve the next page.  

If no interactions exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api//wishlists/interactions```|
|-----------|---------------|
| Method    | GET          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

| Query Parameters | What is it for ? |
|---|---|
| ```updated_after``` | This is the time period for generating the data. e.g: ```2023-09-01```. API will query database for interactions that created after this particular date. |
| ```pageSize``` | Determines the number of wishlist items returned in the API response. Default page size is 20 and max is 50. |
| ```lastItemId``` | Determinse which items to return.  API returns wishlist items in the ascending order of their TWC generated interaction ID. This parameter will inform API to respond items with ID greater than, but excluding the value provided. |

<summary>Response - 200 (OK)</summary>

```json
{
    [
        {
            "id": "4812c4857e89ae6f63433d5557aec32b",
            "customer_email": "vysakh.09801x@gmail.com",
            "customerRef": "CUST0980x1",
            "entityType": "WISHLISTITEM",
            "interactionType": "CREATED",
            "itemId": "d9138d39-6aba-4f6f-8454-e3f700fd277c",
            "productRef": "PROD0045-1",
            "variantRef": "VAR-321",
            "varientAttributes": "color=blue,size=xl",
            "wishlistId": "ee92caf3-5414-4e66-89c9-fd793e2748df",
            "interaction_date": "2023-09-15T09:48:06.980Z"
        },
        {
            "id": "04631734fb80332fd385dcbba428fc6d",
            "customer_email": "manusankar88@gmail.com",
            "customerRef": "Vys-1234",
            "entityType": "WISHLIST",
            "interactionType": "CREATED",
            "itemId": "76eb38aa-7278-4bc7-9e4e-983f0f318164",
            "wishlistId": "76eb38aa-7278-4bc7-9e4e-983f0f318164",
            "interaction_date": "2023-06-05T10:29:05.827Z"
        }
    ]
}
```

<summary>HTTP Status Codes</summary>

``` 
- 200 OK
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


# **WishlistItem**

## Create a Wishlist Item

Adds a single wishlist item into an existing wishlist.  The wishlist can be identified by either the TWC internal identifier, or the wishlistRef, which is the retailer's own wishlist identifier.  

To create a wishlist item, you need to provide either of the following:
- BOTH the *TWC* product identifier AND TWC variant identifer (i.e. the TWC productID and variantID which you can get from TWC in a prior call), **OR** 
- BOTH your own *internal* product identifier AND variant identifer (i.e. productRef and variantRef).

| Endpoint| ```/api/wishlist/items```|
|-----------|---------------|
| Method    | POST          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<summary>Sample Request:</summary>
 
```json
{
    "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
    "wishlistItemRef": "WISHITEM1111",
    "product":
    {
        "productId": "ede20e6c-88c8-41d9-b0a5-a631871b23d2",
        "selectedVariantId": "5396d084-4346-44d2-9d87-b2015c1d7b42"
    },
    "attributeGroups":
    {
        "cart_info":
        {
            "attributes": {
                "cart_id": "CART1111",
                "channel": "mobile-app"
            },
            "description": "cart related attributes"
        }
    }
}
```

<summary>Response - 201 (created)</summary>

```json
{
    "id": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
    "wishlistItemRef": "WI200013716",
    "purchased": false,
    "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
    "product": {
        "productId": "ede20e6c-88c8-41d9-b0a5-a631871b23d2",
        "productRef": "100019951",
        "selectedVariantId": "5396d084-4346-44d2-9d87-b2015c1d7b42",
        "selectedVariantRef": "4690"
    },
    "createdTime": "2023-05-01T02:37:22.407387Z",
    "modifiedTime": "2023-05-01T02:37:22.407390Z",
    "attributeGroups": {
        "cart_info":
        {
            "attributes": {
                "cart_id": "CART1111",
                "channel": "mobile-app"
            },
            "description": "cart related attributes"
        }
    },
    "addedFromCart": false,
    "prerelease": false,
    "disableNotification": false
}
```

<summary>HTTP Status Code: </summary>

``` 
- 200 OK
- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Add multple Wishlist Items

Add multiple items to an existing wishlist. Please provide either item id or reference.

| Endpoint| ```/api/wishlist/add-items```|
|-----------|---------------|
| Method    | POST          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<summary>Sample Request</summary>

```json
{
  "itemId": [
    {
      "addedFromCart": true,
      "attributeGroups": {
        "additionalProp1": {
          "attributes": {
            "additionalProp1": "string",
            "additionalProp2": "string",
            "additionalProp3": "string"
          },
          "description": "string"
        }
      },
      "datePurchased": "2023-10-31T05:14:07.734Z",
      "disableNotification": true,
      "id": "string",
      "locationId": "string",
      "locationRef": "string",
      "prerelease": true,
      "productId": "string",
      "purchased": true,
      "selectedVariantId": "string",
      "wishlistItemRef": "string"
    }
  ],
  "itemRef": [
    {
      "addedFromCart": true,
      "attributeGroups": {
        "additionalProp1": {
          "attributes": {
            "additionalProp1": "string",
            "additionalProp2": "string",
            "additionalProp3": "string"
          },
          "description": "string"
        }
      },
      "datePurchased": "2023-10-31T05:14:07.734Z",
      "disableNotification": true,
      "id": "string",
      "locationId": "string",
      "locationRef": "string",
      "prerelease": true,
      "productRef": "string",
      "purchased": true,
      "selectedVariantRef": "string",
      "wishlistItemRef": "string"
    }
  ],
  "wishlistId": "string",
  "wishlistRef": "string"
}
```

<summary>Status Codes</summary>

``` 
- 202 Accepted
- 400 Bad request
- 401 Unauthorized
- 403 Forbidden 
- 409 Conflict
```


## Update WishlistItems

The APIs below provide mechanisms to update wishlist items.  The retailer may choose the most appropriate API to suit their circumstances.

### Update a Wishlist Item

Update a wishlist item (for example to change the chosen variant).  Developer must supply either the wishlist ID and item ID (both internal TWC values) or the wishlistRef and itemRef (both retailer's own identifiers).

Note that itemRef is the client's unique identifier for a wishlist item associated with a wishlist item.  It is NOT the productRef, which typically could be the retailer's product SKU.

If the variant is being changed, then the original variant ID (TWC internal ID) must also be provided.

| Endpoint| ```/api/wishlist/items```|
|-----------|---------------|
| Method    | PUT           |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<summary>Sample Request:</summary>

```json

{
    "id": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
    "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
    "product": {
        "productId": "{{productId}}",
        "selectedVariantId": "{{variantId}}",
        "oldVariantId": "5396d084-4346-44d2-9d87-b2015c1d7b42"
    },
    "attributeGroups": {
        "cart_attributes": {
            "attributes": {
                "cart_ref": "CART00111",
                "channel": "web"
            },
            "description": "cart info"
        }
    }
}
```

<summary>Response - 200 (OK Updated)</summary>

```json
{
    "id": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
    "wishlistItemRef": "WI200013716",
    "purchased": false,
    "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
    "product": {
        "productId": "ede20e6c-88c8-41d9-b0a5-a631871b23d2",
        "productRef": "100019951",
        "selectedVariantId": "3a40289c-d56b-49f2-b0f7-d3383a36bc80",
        "selectedVariantRef": "6665"
    },
    "createdTime": "2023-05-01T02:37:22.407387Z",
    "modifiedTime": "2023-05-01T04:57:45.835957Z",
    "attributeGroups": {
        "cart_attributes": {
            "description": "cart info",
            "attributes": {
                "cart_ref": "CART00111",
                "channel": "web"
            }
        },
        "POS_attributes": {
            "description": "POS related attidional information",
            "attributes": {
                "POS_ref": "POS001",
                "store_id": "STORE001"
            }
        }
    },
    "addedFromCart": false,
    "prerelease": false,
    "disableNotification": false
}
```

<summary>HTTP Status Code:</summary>

``` 
- 200 OK
- 400 Bad request
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


### Update a Wishlist Item By Ref

Update a wishlist item (for example to change the selected variant).  Developer must supply the wishlistRef and itemRef (both the retailer's own identifiers).

Note that itemRef is the client's unique identifier for a wishlist item associated with a single wishlist item.  It is NOT the productRef, which typically could be the retailer's product SKU.

If the variant is being changed, then the original variant ID (TWC internal ID) must also be provided.

| Endpoint| ```/api/wishlist/items/ref={ref}```|
|-----------|---------------|
| Method    | PUT           |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| path variable | ```ref``` ref is the retailer assigned unique wishlist item reference. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<summary>Sample Request:</summary>

```json

{
    "id": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
    "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
    "product": {
        "productId": "{{productId}}",
        "selectedVariantId": "{{variantId}}",
        "oldVariantId": "5396d084-4346-44d2-9d87-b2015c1d7b42"
    },
    "attributeGroups": {
        "cart_attributes": {
            "attributes": {
                "cart_ref": "CART00111",
                "channel": "web"
            },
            "description": "cart info"
        }
    }
}
```

<summary>Response - 200 (OK Updated)</summary>

```json
{
    "id": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
    "wishlistItemRef": "WI200013716",
    "purchased": false,
    "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
    "product": {
        "productId": "ede20e6c-88c8-41d9-b0a5-a631871b23d2",
        "productRef": "100019951",
        "selectedVariantId": "3a40289c-d56b-49f2-b0f7-d3383a36bc80",
        "selectedVariantRef": "6665"
    },
    "createdTime": "2023-05-01T02:37:22.407387Z",
    "modifiedTime": "2023-05-01T04:57:45.835957Z",
    "attributeGroups": {
        "cart_attributes": {
            "description": "cart info",
            "attributes": {
                "cart_ref": "CART00111",
                "channel": "web"
            }
        },
        "POS_attributes": {
            "description": "POS related attidional information",
            "attributes": {
                "POS_ref": "POS001",
                "store_id": "STORE001"
            }
        }
    },
    "addedFromCart": false,
    "prerelease": false,
    "disableNotification": false
}
```
<summary>HTTP Status Code:</summary>

``` 
- 200 OK
- 400 Bad request
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


### Update a Wishlist Item By Id

Update a wishlist item (for example to change the selected variant).  Developer must supply the wishlist ID and item ID (both TWC internal identifiers).

If the variant is being changed, then the original variant ID (TWC internal ID) must also be provided.

| Endpoint| ```/api/wishlist/items/id={id}```|
|-----------|---------------|
| Method    | PUT           |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| path variable | ```id``` id is the TWC generated unique identifier of the wishlist item. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<summary>Sample Request:</summary>

```json

{
    "id": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
    "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
    "product": {
        "productId": "{{productId}}",
        "selectedVariantId": "{{variantId}}",
        "oldVariantId": "5396d084-4346-44d2-9d87-b2015c1d7b42"
    },
    "attributeGroups": {
        "cart_attributes": {
            "attributes": {
                "cart_ref": "CART00111",
                "channel": "web"
            },
            "description": "cart info"
        }
    }
}
```

<summary>Response - 200 (OK Updated)</summary>

```json
{
    "id": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
    "wishlistItemRef": "WI200013716",
    "purchased": false,
    "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
    "product": {
        "productId": "ede20e6c-88c8-41d9-b0a5-a631871b23d2",
        "productRef": "100019951",
        "selectedVariantId": "3a40289c-d56b-49f2-b0f7-d3383a36bc80",
        "selectedVariantRef": "6665"
    },
    "createdTime": "2023-05-01T02:37:22.407387Z",
    "modifiedTime": "2023-05-01T04:57:45.835957Z",
    "attributeGroups": {
        "cart_attributes": {
            "description": "cart info",
            "attributes": {
                "cart_ref": "CART00111",
                "channel": "web"
            }
        },
        "POS_attributes": {
            "description": "POS related attidional information",
            "attributes": {
                "POS_ref": "POS001",
                "store_id": "STORE001"
            }
        }
    },
    "addedFromCart": false,
    "prerelease": false,
    "disableNotification": false
}
```

<summary>HTTP Status Code:</summary>

``` 
- 200 OK
- 400 Bad request
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


## Get Wishlist Items

THe APIs below provide mechanisms to get all items in a single wishlist, or a single wishlist item.

### Get all Items in a Wishlist by Wishlist Id

Returns a list of all wishlist items belonging to the given wishlist identifier (TWC internal identifier).

Results are paginated, page size is 20, maximum 50.  If the item does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlist/items```|
|-----------|---------------|
| Method    | GET           |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|


| Query Parameters | What is it for ? |
|---|---|
| ```id``` | This is the TWC system generated unique wishlist identifier. e.g: ```67ccc612-0f1b-4d9d-b69e-d43511c6782d```. The API will query the database for wishlists by ID. |
| ```wishlistRef``` | This is the retailer assigned unique wishlist reference identifier. e.g: ```WISH0001```. The API will query the database for wishlists by the reference value provided. |
| ```pageSize``` | Determines the number of wishlist items returned in the API response. Default page size is 20 and max is 50. |
| ```lastItemId``` | Determines which items to return. API returns wishlist items in the ascending order of their TWC generated wishlist ID. This parameter will inform the API to respond with the items with an identifier greater than, but excluding the value provided. |

<summary>Sample Response - 200 (OK)</summary>

```json
{
    "itemCount": 2,
    "lastEvaluatedItemId": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
    "wishlistItems": [
        {
            "id": "ffe332f6-7f28-4dc0-a398-5c6f93b0d7df",
            "wishlistItemRef": "WI2000131662",
            "purchased": false,
            "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
            "product": {
                "productId": "ede20e6c-88c8-41d9-b0a5-a631871b23d2",
                "productRef": "100019951",
                "selectedVariantId": "b72e501d-d87a-40bb-b0bb-2d4c3cbb4f0a",
                "selectedVariantRef": "9561"
            },
            "createdTime": "2023-05-01T04:40:44.106530Z",
            "modifiedTime": "2023-05-01T04:40:44.106530Z",
            "attributeGroups": {
                "cart_info": {
                    "description": "cart related attributes",
                    "attributes": {
                        "cart_id": "CART1111",
                        "channel": "mobile-app"
                    }
                }
            },
            "addedFromCart": true,
            "prerelease": false,
            "disableNotification": false
        },
        {
            "id": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
            "wishlistItemRef": "WI200013716",
            "purchased": false,
            "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
            "product": {
                "productId": "ede20e6c-88c8-41d9-b0a5-a631871b23d2",
                "productRef": "100019951",
                "selectedVariantId": "3a40289c-d56b-49f2-b0f7-d3383a36bc80",
                "selectedVariantRef": "6665"
            },
            "createdTime": "2023-05-01T02:37:22.407387Z",
            "modifiedTime": "2023-05-01T04:57:45.835957Z",
            "attributeGroups": {
                "cart_attributes": {
                    "description": "cart info",
                    "attributes": {
                        "cart_ref": "CART00111",
                        "channel": "web"
                    }
                },
                "POS_attributes": {
                    "description": "POS related attidional information",
                    "attributes": {
                        "POS_ref": "POS001",
                        "store_id": "STORE001"
                    }
                }
            },
            "addedFromCart": false,
            "prerelease": false,
            "disableNotification": false
        }
    ]
}
```


### Get Wishlist Item by Item Id

Returns the wishlist item belonging to the given item Id (TWC internal item identifier)

If the item does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlist/items/{id}```|
|-----------|---------------|
| Method    | GET           |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| path variable | ```id``` id is the TWC generated unique identifier of the wishlist item. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<summary>Sample Response - 200 (OK)</summary>

```json
{
    "id": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
    "wishlistItemRef": "WI200013716",
    "purchased": false,
    "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
    "product": {
        "productId": "ede20e6c-88c8-41d9-b0a5-a631871b23d2",
        "productRef": "100019951",
        "selectedVariantId": "3a40289c-d56b-49f2-b0f7-d3383a36bc80",
        "selectedVariantRef": "6665"
    },
    "createdTime": "2023-05-01T02:37:22.407387Z",
    "modifiedTime": "2023-05-01T04:57:45.835957Z",
    "attributeGroups": {
        "cart_attributes": {
            "description": "cart info",
            "attributes": {
                "cart_ref": "CART00111",
                "channel": "web"
            }
        },
        "POS_attributes": {
            "description": "POS related attidional information",
            "attributes": {
                "POS_ref": "POS001",
                "store_id": "STORE001"
            }
        }
    },
    "addedFromCart": false,
    "prerelease": false,
    "disableNotification": false
}
```

<summary>HTTP Status Code: </summary>

``` 
- 200 OK
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


### Get Wishlist Item by Item Ref

Returns the wishlist item belonging to the given itemRef (retailer's own item identifier).

Note that itemRef is the client's unique identifier for a wishlist item associated with a single wishlist.  It is NOT the productRef, which typically could be the retailer's product SKU.

If the item does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlist/items/ref={wishlistItemRef}```|
|-----------|---------------|
| Method    | GET           |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| path variable | ```wishlistItemRef``` is the retailer assigned unique wishlist reference identifier. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<summary>Sample Response - 200 (OK)</summary>

```json
{
    "id": "9a5aee4a-f20a-4478-ab4e-02d8bf8c2837",
    "wishlistItemRef": "WI200013716",
    "purchased": false,
    "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
    "product": {
        "productId": "ede20e6c-88c8-41d9-b0a5-a631871b23d2",
        "productRef": "100019951",
        "selectedVariantId": "3a40289c-d56b-49f2-b0f7-d3383a36bc80",
        "selectedVariantRef": "6665"
    },
    "createdTime": "2023-05-01T02:37:22.407387Z",
    "modifiedTime": "2023-05-01T04:57:45.835957Z",
    "attributeGroups": {
        "cart_attributes": {
            "description": "cart info",
            "attributes": {
                "cart_ref": "CART00111",
                "channel": "web"
            }
        },
        "POS_attributes": {
            "description": "POS related attidional information",
            "attributes": {
                "POS_ref": "POS001",
                "store_id": "STORE001"
            }
        }
    },
    "addedFromCart": false,
    "prerelease": false,
    "disableNotification": false
}
```

<summary>HTTP Status Code: </summary>

``` 
- 200 OK
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


## Delete Wishlist Item

### Delete Wishlist Item by Id

Delete Wishlist item marks the item matching the given item ID (TWC internal platform ID) as deleted and produces an HTTP response confirming the action. 

If the wishlist/item does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlist/items/{id}```|
|-----------|---------------|
| Method    | DELETE          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| ```id``` | This is the TWC system generated unique wishlist item identifier. e.g: ```67ccc612-0f1b-4d9d-b69e-d43511c6782d```. The API will remove the wishlist item for the given identifier, if it exists. |
| Query Parameters |  |
| ```purchasedAndRemoved``` | This Boolean parameter is used to differentiate and identify the wishlist items removed after sale conversions. This can be set manually or automated  |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<summary>Response - 204 (Deleted)</summary> 

<summary>HTTP Status Code</summary> 

``` 
- 204 Deleted
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


### Delete Wishlist Item by itemRef

Delete Wishlist Item by itemRef marks the item matching the given itemRef (retailer's own identifier) as deleted and produces an HTTP response confirming the action. 

Note that itemRef is the client's unique identifier for a wishlist item associated with a single wishlist.  It is NOT the productRef, which typically could be the retailer's product SKU.

If the wishlist/item does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlist/items/{wishlistItemRef}/ref```|
|-----------|---------------|
| Method    | DELETE          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| ```wishlistItemRef``` | This is the TWC retailer assigned unique wishlist item identifier. e.g: ```WISHITEM111111```. The API will remove the wishlist item for the given reference, if it exists. |
| Query Parameters |  |
| ```purchasedAndRemoved``` | This Boolean parameter is used to differentiate and identify the wishlist items removed after sale conversions. This can be set manually or automated  |

<summary>Response - 204 (Deleted)</summary> 

<summary>HTTP Status Code</summary> 

``` 
- 204 Deleted
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

***
[Back to Top](#wishlist-api)

[Back to Home](index.md#welcome-to-the-wishlist)

