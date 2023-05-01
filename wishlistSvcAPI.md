
[Back to Home](index.md#welcome-to-the-wishlist)


# **Wishlist API**
The Wishlist API enables the management of customer wishlists.  

In most situations, The Wishlist platform will be the master data source for Wishlists, as it is able to manage wishlist information from multiple sources (e.g. website or physical stores); then trigger events based on saved wishlist items; and send wishlist information to 3rd party systems such as marketing automation platforms like Emarsys, Klaviyo and DotDigital.  

One customer may have mulitple wishlists.  You can only create a wishlist for a valid customer.

A wishlist is created 'empty' and items added later, either one by one, or multiple items can be added at the same time.


***

[**Wishlist API**](#wishlist-api)
- [**Representations**](#representations)
  - [Wishlist](#wishlist-request)
  - [Wishlist Item](#wishlistitem-request)
  - [Product](#wishlistitem-product)
  - [AttributeGroups](#attributegroups)
  - [AttributeGroup](#attributegroup)
- [**Endpoints**](#rest-endpoints)
  - [**Wishlist**](#wishlist-resource)
    - [Create](#create-a-wishlist)
    - [Create a Wishlist](#create-a-wishlist)
    - [Update a Wishlist](#update-a-wishlist)
    - [Update a Wishlist By ID](#update-a-wishlist-by-id)
    - [Update a Wishlist By Ref](#update-a-wishlist-by-ref)
    - [Get Wishlist by id/wishlistRef](#get-wishlist-by-idwishlistref)
    - [Get Wishlist by Id](#get-wishlist-by-id)
    - [Get Wishlist by Wishlist Reference](#get-wishlist-by-wishlist-reference)
    - [Get Wishlist by CustomerId](#get-wishlist-by-customerid)
    - [Get Wishlist by CustomerRef](#get-wishlist-by-customerref)
    - [Get Wishlist By Customer ID or Ref](#get-wishlist-by-customer-id-or-ref)
    - [Delete Wishlist by ID/Ref](#delete-wishlist-by-idref)
    - [Delete Wishlist by ID](#delete-wishlist-by-id)
    - [Delete Wishlist by Ref](#delete-wishlist-by-ref)
  - [**WishlistItem**](#wishlist-item-resource)
    - [Create a Wishlist Item](#create-a-wishlist-item)
- [Add  Wishlist Items](#add--wishlist-items)
  - [Upload multiple Wishlist Items](#upload-multiple-wishlist-items)
  - [Update a Wishlist Item](#update-a-wishlist-item)
  - [Update a Wishlist Item By Ref](#update-a-wishlist-item-by-ref)
  - [Update a Wishlist Item By Id](#update-a-wishlist-item-by-id)
  - [Get all Items in a Wishlist by Wishlist Id](#get-all-items-in-a-wishlist-by-wishlist-id)
  - [Get Wishlist Item by Item Id](#get-wishlist-item-by-item-id)
  - [Get Wishlist Item by Item Ref](#get-wishlist-item-by-item-ref)
  - [Get Wishlist Item by WishlistId and Item Id](#get-wishlist-item-by-wishlistid-and-item-id)
  - [Delete Wishlist Item by Id](#delete-wishlist-item-by-id)
  - [Delete Wishlist Item by itemRef](#delete-wishlist-item-by-itemref)
  - [Delete Wishlist Item by wishlist ID and item Id](#delete-wishlist-item-by-wishlist-id-and-item-id)

## **Representations**

All requests or responses are JSON objects

### Wishlist Request

| Field | Type | Description |
|---|---|---|
| *customerId* | string | TWC generated unique ID of customer. Either customerId or customerRef is mandatory when creating wishlist |
| *customerRef* | string | TWC generated unique ID of customer. Either customerId or customerRef is mandatory when creating wishlist |
| *description* | string | Wishlist description, this field may not always be used by retailers. This field could be useful in case of social shopping scenarios |
| *name* | string | Wishlists name given by customer |
| *wishlistRef* | string | This is a reference Id given to wishlist by retailer. This field may be used to GET/UPDATE/DELETE wishlist |
| *isPrivate* | boolean | making the wishlist private to customer |
| *attributeGroups* |[AttributeGroups](#attributegroups)| This field may be used to add additional attributes to the wishlist. This field is in general available on most entitiesin The Wishlist platform.<br> "attributeGroups":&nbsp;{<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"wishlist_origin":&nbsp;"app",<br>&emsp;&emsp;"ecommerce_wishlist_id":&nbsp;"ecommerce&nbsp;system&nbsp;generated&nbsp;id",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;wishlist"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>}<br> |


### Wishlist Response

| Field | Type | Description |
|---|---|---|
| *id* | string | TWC generated unique ID of the wishlist.|
| *customerId* | string | TWC generated unique ID of customer.|
| *customerRef* | string | TWC generated unique ID of customer.|
| *description* | string | Wishlist description.|
| *name* | string | Wishlists name given by customer |
| *wishlistRef* | string | This is a reference Id given to wishlist by retailer. This field may be used to GET/UPDATE/DELETE wishlist |
| *isPrivate* | boolean | making the wishlist private to customer |
| *attributeGroups* |[AttributeGroups](#attributegroups)| This field may be used to add additional attributes to the wishlist. This field is in general available on most entitiesin The Wishlist platform.<br> "attributeGroups":&nbsp;{<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"wishlist_origin":&nbsp;"app",<br>&emsp;&emsp;"ecommerce_wishlist_id":&nbsp;"ecommerce&nbsp;system&nbsp;generated&nbsp;id",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;wishlist"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>}<br> |

###  WishlistItem Request

| Field | Type | Description |
|---|---|---|
| *addedFromCart* | boolean | This field is to mark that it was added from cart. |
| *disableNotification* | boolean| This field will disable notifications on the wishlist item. |
| *wishlistId* | string | TWC generated unique ID of wishlist, to which the item is being added. Either wishlistId or wishlistRef is mandatory when creating a wishlist item. |
| *wishlistRef* | string | reatailer assigned unique  reference ID of wishlist. Either wishlistId or wishlistRef is mandatory when creating a wishlist item. |
| *wishlistItemRef* | string | reatailer assigned unique  reference ID of wishlist item. |
| *prerelease* | boolean | This field indicates that customer is registering interest to a pre release item. |
| *purchased* | boolean | This field indicates that the item has been purchased. |
| *product* | [Product](#wishlistitem-product) | This field represents the field being added to item [product](#wishlistitem-product). This is a mandatory field. |
| *attributeGroups* | [AttributeGroups](#attributegroups) | This field may be used to add additional attributes to the wishlist. This field is in general available on most entitiesin The Wishlist platform.<br> "attributeGroups":&nbsp;{<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"wishlist_item_origin":&nbsp;"mobile_app",<br>&emsp;&emsp;"ecommerce_wishlist_item_id":&nbsp;"ecommerce&nbsp;system&nbsp;generated&nbsp;id",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;wishlist"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>}<br> |

###  WishlistItem Product

| Field | Type| Description |
|---|---|---|
| *productId* | string| This is the TWC generated product id. Either productId or productRef is mandatory when creating a wishlist item.|
| *productRef* | string | This is the retailer assigned product reference id. Either productId or productRef is mandatory when creating a wishlist item.|
| *selectedVariantId* | string | This is the retailer assigned product reference id. Either selectedVariantId or selectedVariantRef is mandatory when creating a wishlist item.|
| *selectedVariantRef* | string | This is the retailer assigned product reference id. Either selectedVariantId or selectedVariantRef is mandatory when creating a wishlist item.|
| *oldVariantId* | string | When updating a wishlist item to another variant oldVariantId field is mandatory, to switch to another variant. This is TWC generated unique ID.|

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
| *id* | string | This is the TWC generted unique ID of wishlist item.|
| *addedFromCart* | boolean | This field is to mark that it was added from cart.|
| *disableNotification* | boolean | This field will disable notifications on the wishlist item.|
| *wishlistId* | string | TWC generated unique ID of wishlist, to which the item is being added. Either wishlistId or wishlistRef is mandatory when creating a wishlist item.|
| *wishlistRef* | string | reatailer assigned unique  reference ID of wishlist. Either wishlistId or wishlistRef is mandatory when creating a wishlist item.|
| *wishlistItemRef* | string | reatailer assigned unique  reference ID of wishlist item.|
| *prerelease* | boolean | This field indicates that customer is registering interest to a pre release item.|
| *purchased* | boolean | this field indicates that the item has been purchased.|
| *purchasedDate* | boolean | The date on which item was purchased. If orders are pushed to TWC, TWC will mark the item as purchased.|
| *product* |[Product](#wishlistitem-product)| This field represents the field being added to item [product](#wishlistitem-product)|
| *attributeGroups* | object | This field may be used to add additional attributes to the wishlist. This field is in general available on most entitiesin The Wishlist platform.<br> "attributeGroups":&nbsp;{<br>&emsp;"extra_attribute_group1":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"wishlist_item_origin":&nbsp;"mobile_app",<br>&emsp;&emsp;"ecommerce_wishlist_item_id":&nbsp;"ecommerce&nbsp;system&nbsp;generated&nbsp;id",&emsp;&emsp;<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"any&nbsp;additional&nbsp;attribute&nbsp;you&nbsp;want&nbsp;to&nbsp;add&nbsp;to&nbsp;wishlist"<br>&emsp;},<br>&emsp;"retailer_defined_name_of_group":&nbsp;{<br>&emsp;&ensp;"attributes":&nbsp;{<br>&emsp;&emsp;"retailer_defined_attribute1":&nbsp;"user&nbsp;defined&nbsp;attribute&nbsp;value",<br>&emsp;&emsp;"another_attribute":&nbsp;"another&nbsp;value"<br>&emsp;&ensp;},<br>&emsp;&ensp;"description":&nbsp;"retailer&nbsp;defined&nbsp;properties&nbsp;and&nbsp;its&nbsp;values,&nbsp;flexible&nbsp;data&nbsp;model&nbsp;to&nbsp;add&nbsp;additional&nbsp;properties."<br>&emsp;}<br>}<br>|

## **Endpoints**
### **Wishlist**
#### CREATE
Creates a new wishlist.  Requires the customer to be created first.  

| Endpoint| ```/api/wishlists```|
|-----------|---------------|
| Method    | POST          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
|How to get access token| [Tenant Authentication](authenticationsvcApi.md)|


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
  "id":"twc-generated-wishlist-id",
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
  "customerId": "twc-generated-customer-id",
  "customerRef": "retailers_customer_id",
  "description": "wishlists description",
  "isPrivate": "true",
  "name": "wishlist name",
  "wishlistRef": "retailers wishlist id" 
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


#### UPDATE

Used to update any metadata about a wishlist, for example, attribute groups, staff/store ID or wishlist name.  *This API is NOT used to update items on the wishlist*

You can update by internal Wishlist ID or wishlistRef, which is the retailer's own ID (which, for example may be assigned in the ecommerce system)

**THIS API IS DEPRECIATED.  PLEASE USE UDATE WISHLIST BY ID OR WISHLISTREF BELOW**

| Endpoint| ```/api/wishlists```|
|-----------|---------------|
| Method    | PUT          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
|How to get access token| [Tenant Authentication](authenticationsvcApi.md)|

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Sample Request:

<!-- <details> -->
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
      "description": "retailer defined properties and its values, flexible data model to add additional properties."
    }
  },
  "customerId": "twc-generated-customer-id", //either customerId or customerRef is mandatory
  "customerRef": "retailers_customer_id",
  "description": "wishlists description", // This field may not be used for private wishlist scenario. This field however may be key in a social shopping scenario.
  "isPrivate": "true", //marking the wishlist private. not a mandatory field.
  "name": "wishlist name",
  "wishlistRef": "retailers wishlist id" // Either id or wishlistRef is mandatory to update a wishlist using this service.
}
```
<!-- </details> -->

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
- 201 Created
- 204 Deleted
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```



## Update a Wishlist By ID
Used to update any metadata about a wishlist, for example, attribute groups, staff/store ID or wishlist name.  *Note this API is NOT used to update items on the wishlist.*

As this API uses Wishlist ID, then you can use it to update wishlistRef, which is the retailer's own wishlit ID (which, for example may be assigned in the ecommerce system)

Endpoint: ```/api/wishlists/id={id}```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable:

```
id - Wishlist ID
```


Sample Request:

<!-- <details> -->
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
<!-- </details> -->

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
- 201 Created
- 204 Deleted
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Update a Wishlist By Ref
Used to update any metadata about a wishlist, for example, attribute groups, staff/store ID or wishlist name.  *Note this API is NOT used to update items on the wishlist.*

As this API uses wishlistRef, which is the retailer's own wishlit ID (which, for example may be assigned in the ecommerce system)

Endpoint: ```/api/wishlists/ref={ref}```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable:

```
ref - Wishlist Ref
```


Sample Request:

<!-- <details> -->
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
<!-- </details> -->

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
- 201 Created
- 204 Deleted
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Get Wishlist by id/wishlistRef
Retrieves the wishlist and the wishlist items that belongs to the given Id and/or wishlistRef.  If the wishlist does not exist, this method returns a ResourceNotFound error.

The returned item array is paginated - 20 default (50 maximum).  The API will respond with the item count in the page, and the itemID the for the last item (lastitemID) returned for that response, which should then be used for the  subsequent API call to retrieve the next page.  


Endpoint: ```/api/wishlists/```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request Parameters: `Id  : Wishlist Id ,wishlistRef : Wishlist Reference , pageSize: Number of items in the page ,lastItemId: Last evaluated id from the previous request  `

<summary>Response - 200 (OK)</summary>

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "customerId": "string",
  "customerRef": "string",
  "resultCount": 4,
  "lastEvaluatedId": "string",
  "deleted": true,
  "description": "string",
  "id": "string",
  "isPrivate": true,
  "name": "string",
  "wishlistItems": [
    {
      "attributeGroups": {
        "additionalProp1": {
          "attributes": {
            "additionalProp1": "string",
            "additionalProp2": "string",
            "additionalProp3": "string"
          },
          "description": "string"
        },
        "additionalProp2": {
          "attributes": {
            "additionalProp1": "string",
            "additionalProp2": "string",
            "additionalProp3": "string"
          },
          "description": "string"
        },
        "additionalProp3": {
          "attributes": {
            "additionalProp1": "string",
            "additionalProp2": "string",
            "additionalProp3": "string"
          },
          "description": "string"
        }
      },
      "datePurchased": "2022-06-27T15:37:28.595Z",
      "id": "string",
      "product": {
        "productId": "string",
        "productRef": "string",
        "selectedVariantId": "string",
        "selectedVariantRef": "string"
      },
      "purchased": true,
      "addedFromCart": true,
      "wishlistId": "string",
      "wishlistItemRef": "string",
      "createdTime": "2022-08-24T07:28:12.000+0000",
      "modifiedTime": "2022-08-24T07:30:52.051+0000",
      "wishlistRef": "string",
      "prerelease": "boolean",
      "disableNotification" : "boolean"
    }
  ],
  "wishlistRef": "string"
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

## Get Wishlist by Id

Returns the wishlist that matches the given internal TWC Platform identifier, along with the wishlist items.

The returned item array is paginated - 20 default (50 maximum).  The API will respond with the item count in the page, and the itemID the for the last item (lastitemID) returned for that response, which should then be used for the  subsequent API call to retrieve the next page.  

If the wishlist does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/wishlists/{id}```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Path Parameter: `Id  : Wishlist Id , pageSize: Number of items in the page ,lastItemId: Last evaluated id from the previous request`

<summary>Response - 200 (OK)</summary>

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "customerId": "string",
  "customerRef": "string",
  "resultCount": 4,
  "lastEvaluatedId": "string",
  "deleted": true,
  "description": "string",
  "id": "string",
  "isPrivate": true,
  "name": "string",
  "wishlistItems": [
    {
      "attributeGroups": {
        "additionalProp1": {
          "attributes": {
            "additionalProp1": "string",
            "additionalProp2": "string",
            "additionalProp3": "string"
          },
          "description": "string"
        },
        "additionalProp2": {
          "attributes": {
            "additionalProp1": "string",
            "additionalProp2": "string",
            "additionalProp3": "string"
          },
          "description": "string"
        },
        "additionalProp3": {
          "attributes": {
            "additionalProp1": "string",
            "additionalProp2": "string",
            "additionalProp3": "string"
          },
          "description": "string"
        }
      },
      "datePurchased": "2022-06-27T15:37:28.595Z",
      "id": "string",
      "product": {
        "productId": "string",
        "productRef": "string",
        "selectedVariantId": "string",
        "selectedVariantRef": "string"
      },
      "purchased": true,
      "addedFromCart": true,
      "wishlistId": "string",
      "wishlistItemRef": "string",
      "createdTime": "2022-08-24T07:28:12.000+0000",
      "modifiedTime": "2022-08-24T07:30:52.051+0000",
  
      "wishlistRef": "string",
      "prerelease": "boolean",
      "disableNotification" : "boolean"
    }
  ],
  "wishlistRef": "string"
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

## Get Wishlist by Wishlist Reference
Returns the wishlist that matches the provided wishlistRef (which is the retailer's own wishlist identifier), along with the wishlist items.

The returned item array is paginated - 20 default (50 maximum).  The API will respond with the item count in the page, and the itemID the for the last item (lastitemID) returned for that response, which should then be used for the  subsequent API call to retrieve the next page.  

If the wishlist does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/wishlists/{wishlistRef}/byref```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Path Parameter: `wishlistRef : Wishlist Reference , pageSize: Number of items in the page ,lastItemId: Last evaluated id from the previous request`

<summary>Response - 200 (OK)</summary>

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "customerId": "string",
  "customerRef": "string",
  "resultCount": 4,
  "lastEvaluatedId": "string",
  "deleted": true,
  "description": "string",
  "id": "string",
  "isPrivate": true,
  "name": "string",
  "wishlistItems": [
    {
      "attributeGroups": {
        "additionalProp1": {
          "attributes": {
            "additionalProp1": "string",
            "additionalProp2": "string",
            "additionalProp3": "string"
          },
          "description": "string"
        },
        "additionalProp2": {
          "attributes": {
            "additionalProp1": "string",
            "additionalProp2": "string",
            "additionalProp3": "string"
          },
          "description": "string"
        },
        "additionalProp3": {
          "attributes": {
            "additionalProp1": "string",
            "additionalProp2": "string",
            "additionalProp3": "string"
          },
          "description": "string"
        }
      },
      "datePurchased": "2022-06-27T15:37:28.595Z",
      "id": "string",
      "product": {
        "productId": "string",
        "productRef": "string",
        "selectedVariantId": "string",
        "selectedVariantRef": "string"
      },
      "purchased": true,
      "addedFromCart": true,
      "wishlistId": "string",
      "wishlistItemRef": "string",
      "createdTime": "2022-08-24T07:28:12.000+0000",
      "modifiedTime": "2022-08-24T07:30:52.051+0000",
      "wishlistRef": "string",
      "prerelease": "boolean",
      "disableNotification" : "boolean"
    }
  ],
  "wishlistRef": "string"
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

## Get Wishlist by CustomerId
Returns the collection of wishlists that belong to the given customer id (Customer ID is the TWC internal identifier).  

The returned list is paginated - 20 default (50 maximum).  The API will respond with the number of wishlists returned in the page, and the wishlistID for the for the last wishlist returned for that response, which should then be used for the  subsequent API call to retrieve the next page.  

If no wishlists exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/wishlists/customer/{customerId}```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable: `customerId - Unique Customer Id, pageSize: Number of items in the page ,lastItemId: Last evaluated id from the previous request`

<summary>Response - 200 (OK)</summary>

```json
[
  {
    "attributeGroups": {
      "additionalProp1": {
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        },
        "description": "string"
      },
      "additionalProp2": {
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        },
        "description": "string"
      },
      "additionalProp3": {
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        },
        "description": "string"
      }
    },
    "customerId": "string",
    "customerRef": "string",
    "deleted": true,
    "description": "string",
    "id": "string",
    "isPrivate": true,
    "name": "string",
    "resultCount": 4,
    "lastEvaluatedId": "string",
    "wishlistItems": [
      {
        "attributeGroups": {
          "additionalProp1": {
            "attributes": {
              "additionalProp1": "string",
              "additionalProp2": "string",
              "additionalProp3": "string"
            },
            "description": "string"
          },
          "additionalProp2": {
            "attributes": {
              "additionalProp1": "string",
              "additionalProp2": "string",
              "additionalProp3": "string"
            },
            "description": "string"
          },
          "additionalProp3": {
            "attributes": {
              "additionalProp1": "string",
              "additionalProp2": "string",
              "additionalProp3": "string"
            },
            "description": "string"
          }
        },
        "datePurchased": "2022-06-27T15:38:01.546Z",
        "id": "string",
        "product": {
          "productId": "string",
          "productRef": "string",
          "selectedVariantId": "string",
          "selectedVariantRef": "string"
        },
        "purchased": true,
        "addedFromCart": true,
        "wishlistId": "string",
        "wishlistItemRef": "string",
        "createdTime": "2022-08-24T07:28:12.000+0000",
        "modifiedTime": "2022-08-24T07:30:52.051+0000",
  
        "wishlistRef": "string",
        "prerelease": "boolean",
        "disableNotification" : "boolean"
      }
    ],
    "createdTime": "2022-08-24T07:28:12.000+0000",
    "modifiedTime": "2022-08-24T07:30:52.051+0000",
    "wishlistRef": "string"
  }
]
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

## Get Wishlist by CustomerRef
Returns the collection of wishlists that belong to the given customer reference (which is the retailer's own customer identifier)

The returned list is paginated - 20 default (50 maximum).  The API will respond with the number of wishlists returned in the page, and the wishlistID for the for the last wishlist returned for that response, which should then be used for the  subsequent API call to retrieve the next page.  

If no wishlists exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/wishlists/customer/{customerRef}/byref```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable: `customerRef - Unique Customer Ref , pageSize: Number of items in the page ,lastItemId: Last evaluated id from the previous request`

<summary>Response - 200 (OK)</summary>

```json
[
  {
    "attributeGroups": {
      "additionalProp1": {
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        },
        "description": "string"
      },
      "additionalProp2": {
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        },
        "description": "string"
      },
      "additionalProp3": {
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        },
        "description": "string"
      }
    },
    "customerId": "string",
    "customerRef": "string",
    "deleted": true,
    "description": "string",
    "id": "string",
    "isPrivate": true,
    "name": "string",
    "resultCount": 4,
    "lastEvaluatedId": "string",
    "wishlistItems": [
      {
        "attributeGroups": {
          "additionalProp1": {
            "attributes": {
              "additionalProp1": "string",
              "additionalProp2": "string",
              "additionalProp3": "string"
            },
            "description": "string"
          },
          "additionalProp2": {
            "attributes": {
              "additionalProp1": "string",
              "additionalProp2": "string",
              "additionalProp3": "string"
            },
            "description": "string"
          },
          "additionalProp3": {
            "attributes": {
              "additionalProp1": "string",
              "additionalProp2": "string",
              "additionalProp3": "string"
            },
            "description": "string"
          }
        },
        "datePurchased": "2022-06-27T15:43:34.415Z",
        "id": "string",
        "product": {
          "productId": "string",
          "productRef": "string",
          "selectedVariantId": "string",
          "selectedVariantRef": "string"
        },
        "purchased": true,
        "addedFromCart": true,
        "wishlistId": "string",
        "wishlistItemRef": "string",
        "createdTime": "2022-08-24T07:28:12.000+0000",
        "modifiedTime": "2022-08-24T07:30:52.051+0000",
  
        "wishlistRef": "string",
        "prerelease": "boolean",
        "disableNotification" : "boolean"
      }
    ],
    "createdTime": "2022-08-24T07:28:12.000+0000",
    "modifiedTime": "2022-08-24T07:30:52.051+0000",
    "wishlistRef": "string"
  }
]
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

## Get Wishlist By Customer ID or Ref

Returns the collection of wishlists that belong to either the internal TWC customer Id, or the retailer's own customerRef.

The returned list is paginated - 20 default (50 maximum).  The API will respond with the number of wishlists returned in the page, and the wishlistID for the for the last wishlist returned for that response, which should then be used for the  subsequent API call to retrieve the next page.  

If no wishlists exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/wishlists/lookup```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable: `customerId - Unique Customer Id,customerRef: Unique Customer Ref, pageSize: Number of items in the page ,lastItemId: Last evaluated id from the previous request`

<summary>Response - 200 (OK)</summary>

```json
{
    "resultCount": 4,
    "lastEvaluatedId": "string",
    "wishlist": [
        {
            "attributeGroups": {
                "additionalProp1": {
                    "attributes": {
                        "additionalProp1": "string",
                        "additionalProp2": "string",
                        "additionalProp3": "string"
                    },
                    "description": "string"
                },
                "additionalProp2": {
                    "attributes": {
                        "additionalProp1": "string",
                        "additionalProp2": "string",
                        "additionalProp3": "string"
                    },
                    "description": "string"
                },
                "additionalProp3": {
                    "attributes": {
                        "additionalProp1": "string",
                        "additionalProp2": "string",
                        "additionalProp3": "string"
                    },
                    "description": "string"
                }
            },
            "customerId": "string",
            "customerRef": "string",
            "deleted": true,
            "description": "string",
            "id": "string",
            "isPrivate": true,
            "name": "string",
            "resultCount": 4,
            "lastEvaluatedId": "string",
            "wishlistItems": [
                {
                    "attributeGroups": {
                        "additionalProp1": {
                            "attributes": {
                                "additionalProp1": "string",
                                "additionalProp2": "string",
                                "additionalProp3": "string"
                            },
                            "description": "string"
                        },
                        "additionalProp2": {
                            "attributes": {
                                "additionalProp1": "string",
                                "additionalProp2": "string",
                                "additionalProp3": "string"
                            },
                            "description": "string"
                        },
                        "additionalProp3": {
                            "attributes": {
                                "additionalProp1": "string",
                                "additionalProp2": "string",
                                "additionalProp3": "string"
                            },
                            "description": "string"
                        }
                    },
                    "datePurchased": "2022-06-27T15:43:34.415Z",
                    "id": "string",
                    "product": {
                        "productId": "string",
                        "productRef": "string",
                        "selectedVariantId": "string",
                        "selectedVariantRef": "string"
                    },
                    "purchased": true,
                    "addedFromCart": true,
                    "wishlistId": "string",
                    "wishlistItemRef": "string",
                    "createdTime": "2022-08-24T07:28:12.000+0000",
                    "modifiedTime": "2022-08-24T07:30:52.051+0000",
                    "wishlistRef": "string",
                    "prerelease": "boolean",
                    "disableNotification" : "boolean"
                }
            ],
            "createdTime": "2022-08-24T07:28:12.000+0000",
            "modifiedTime": "2022-08-24T07:30:52.051+0000",
            "wishlistRef": "string"
        }
    ]
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


## Delete Wishlist by ID/Ref
Delete Wishlist marks the wishlist as deleted and produces an HTTP response confirming the action.  The Wishlist is identified either by the TWC Internal wishlist Id or the retailers own wishlistRef

If the wishlist does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/wishlists```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request Parameters: `Id  : Wishlist Id ,wishlistRef : Wishlist Reference `

<summary>Response - 204 (Deleted)</summary> 


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

## Delete Wishlist by ID
Delete Wishlist marks the matching wishlist as deleted and produces an HTTP response confirming the action.  In this case the Wishlist is identified by the TWC Internal wishlist Id.

If the wishlist does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/wishlists/{id}```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Path Parameter: `Id  : Wishlist Id `

<summary>Response - 204 (Deleted)</summary> 


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

## Delete Wishlist by Ref
Delete Wishlist marks the matching wishlist as deleted and produces an HTTP response confirming the action.  In this case the Wishlist is identified by the retailer's wishlist identifer - wishlistRef.

If the wishlist does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/wishlists/{wishlistRef}/byref```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Path Parameter: `wishlistRef : Wishlist Reference `

<summary>Response - 204 (Deleted)</summary> 


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



## **Wishlist Item Resource**

## Create a Wishlist Item
Adds a sinble wishlist item into an existing wishlist.  The wishlist can be identified by either the TWC internal ID, or the wishlistRef, which is the retailer's own wishlist identifier.  

Endpoint: ```/api/wishlist/items```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Sample Request:

<!-- <details> -->
```json

{
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "datePurchased": "2022-06-20T06:46:40.643Z",
  "id": "string",
  "product": {
    "oldVariantId": "string",
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
  "addedFromCart": true,
  "wishlistId": "string",
  "wishlistItemRef": "string",
  "wishlistRef": "string",
  "prerelease": "boolean",
  "disableNotification" : "boolean"
}
```

<!-- </details> -->

<summary>Response - 201 (created)</summary>

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "datePurchased": "2022-06-27T15:39:19.224Z",
  "id": "string",
  "product": {
    "oldVariantId": "string",
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
  "addedFromCart": true,
  "wishlistId": "string",
  "wishlistItemRef": "string",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "wishlistRef": "string",
  "prerelease": "boolean",
  "disableNotification" : "boolean"
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
# Add multple Wishlist Items
Add multiple items to an existing wishlist in the TWC system.

Endpoint: ```/api/wishlist/add-items```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Sample Request:

<!-- <details> -->
```json
{
    "wishlistId": "string",
    "wishlistRef": "string",
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
                },
                "additionalProp2": {
                    "attributes": {
                        "additionalProp1": "string",
                        "additionalProp2": "string",
                        "additionalProp3": "string"
                    },
                    "description": "string"
                },
                "additionalProp3": {
                    "attributes": {
                        "additionalProp1": "string",
                        "additionalProp2": "string",
                        "additionalProp3": "string"
                    },
                    "description": "string"
                }
            },
            "datePurchased": "2023-03-31T10:00:17.889Z",
            "disableNotification": true,
            "id": "string",
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
                },
                "additionalProp2": {
                    "attributes": {
                        "additionalProp1": "string",
                        "additionalProp2": "string",
                        "additionalProp3": "string"
                    },
                    "description": "string"
                },
                "additionalProp3": {
                    "attributes": {
                        "additionalProp1": "string",
                        "additionalProp2": "string",
                        "additionalProp3": "string"
                    },
                    "description": "string"
                }
            },
            "datePurchased": "2023-03-31T10:00:17.889Z",
            "disableNotification": true,
            "id": "string",
            "prerelease": true,
            "productRef": "string",
            "purchased": true,
            "selectedVariantRef": "string",
            "wishlistItemRef": "string"
        }
    ]
}
```

<!-- </details> -->

<summary>Response - 202 (Accepted)</summary>

HTTP Status Code:
``` 
- 200 OK
- 201 Created
- 202 Accepted
- 204 Deleted
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
- 409 Conflict
```

## Upload multiple Wishlist Items
Adds multiple wishlist items into an existing wishlist.

**THIS API IS DEPRECIATED.  USE ADD-ITEMS**

Endpoint: ```/api/wishlist/upload-items```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Sample Request:

<!-- <details> -->
```json
[
  {
    "attributeGroups": {
      "additionalProp1": {
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        },
        "description": "string"
      },
      "additionalProp2": {
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        },
        "description": "string"
      },
      "additionalProp3": {
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        },
        "description": "string"
      }
    },

    "product": {
      "oldVariantId": "oldvar3",
      "productId": "prod3",
      "productRef": "prodRef3",
      "selectedVariantId": "selVar3",
      "selectedVariantRef": "selVarRef3"
    },
    "purchased": true,
    "addedFromCart": true,
    "wishlistItemRef": "string4",
    "wishlistRef": "string1",
    "prerelease": "false",
    "disableNotification" : "false"
  },
  {
    "attributeGroups": {
      "additionalProp1": {
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        },
        "description": "string"
      },
      "additionalProp2": {
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        },
        "description": "string"
      },
      "additionalProp3": {
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        },
        "description": "string"
      }
    },


    "product": {
      "oldVariantId": "oldvar24",
      "productId": "prod4",
      "productRef": "prodRef4",
      "selectedVariantId": "selVar4",
      "selectedVariantRef": "selVarRef4"
    },
    "purchased": true,
    "addedFromCart": true,
    "wishlistItemRef": "string5",
    "wishlistRef": "string1",
    "prerelease": "false",
    "disableNotification" : "false"
  }
]

```

<!-- </details> -->

<summary>Response - 201 (created)</summary>

```json
[
  {
    "id": "d1198b27-5047-4793-9b43-8429fec342eb",
    "wishlistItemRef": "string4",
    "purchased": true,
    "product": {
      "productId": "prod3",
      "productRef": "prodRef3",
      "selectedVariantId": "selVar3",
      "selectedVariantRef": "selVarRef3"
    },
    "createdTime": "2022-08-23T09:59:27.746+0000",
    "modifiedTime": "2022-08-23T09:59:27.746+0000",
    "addedFromCart": true,
    "attributeGroups": {
      "additionalProp1": {
        "description": "string",
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        }
      },
      "additionalProp3": {
        "description": "string",
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        }
      },
      "additionalProp2": {
        "description": "string",
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        }
      }
    }
  },
  {
    "id": "fe9e98d0-7b6b-4889-89c2-e473e80c6876",
    "wishlistItemRef": "string5",
    "purchased": true,
    "product": {
      "productId": "prod4",
      "productRef": "prodRef4",
      "selectedVariantId": "selVar4",
      "selectedVariantRef": "selVarRef4"
    },
    "createdTime": "2022-08-23T09:59:27.747+0000",
    "modifiedTime": "2022-08-23T09:59:27.747+0000",
    "addedFromCart": true,
    "attributeGroups": {
      "additionalProp1": {
        "description": "string",
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        }
      },
      "additionalProp3": {
        "description": "string",
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        }
      },
      "additionalProp2": {
        "description": "string",
        "attributes": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        }
      }
    }
  }
]
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
- 409 Conflict
```


## Update a Wishlist Item
Update a wishlist item, for example to change the selected variant.  Developer must supply either the wishlist ID and item ID (both internal TWC values) or the wishlistRef and itemRef (both retailer's own identifiers).

Note that itemRef is the client's unique identifier for a wishlist item associated with a single wishlist.  It is NOT the productRef, which typically could be the retailer's product SKU.

If the variant is being changed, then the original variant ID (TWC internal ID) must also be provided.

Endpoint: ```/api/wishlist/items```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Sample Request:
<!-- <details> -->

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "datePurchased": "2022-06-20T06:51:56.516Z",
  "id": "string",
  "product": {
    "oldVariantId": "string",
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
  "addedFromCart": true,
  "wishlistId": "string",
  "wishlistItemRef": "string",
  "wishlistRef": "string",
  "prerelease": false,
  "disableNotification" : false
}
```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary>

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "datePurchased": "2022-06-27T15:40:09.518Z",
  "id": "string",
  "product": {
    "oldVariantId": "string",
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
  "addedFromCart": true,
  "wishlistId": "string",
  "wishlistItemRef": "string",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "wishlistRef": "string",
  "prerelease": false,
  "disableNotification" : false
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

## Update a Wishlist Item By Ref

Update a wishlist item, for example to change the selected variant.  Developer must supply the wishlistRef and itemRef (both retailer's own identifiers).

Note that itemRef is the client's unique identifier for a wishlist item associated with a single wishlist.  It is NOT the productRef, which typically could be the retailer's product SKU.

If the variant is being changed, then the original variant ID (TWC internal ID) must also be provided.

Endpoint: ```/api/wishlist/items/ref={ref}```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable:

```
ref - wishlist Item Ref
```

Sample Request:
<!-- <details> -->

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "datePurchased": "2022-07-27T12:51:40.193Z",
  "product": {
    "oldVariantId": "string",
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
  "addedFromCart": true,
  "wishlistId": "string",
  "wishlistRef": "string",
  "prerelease": false,
  "disableNotification" : false
}
```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary>

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "datePurchased": "2022-06-27T15:40:09.518Z",
  "id": "string",
  "product": {
    "oldVariantId": "string",
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
  "addedFromCart": true,
  "wishlistId": "string",
  "wishlistItemRef": "string",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "wishlistRef": "string",
  "prerelease": false,
  "disableNotification" : false
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
## Update a Wishlist Item By Id

Update a wishlist item, for example to change the selected variant.  Developer must supply the wishlist ID and item ID (both TWC internal identifiers).

If the variant is being changed, then the original variant ID (TWC internal ID) must also be provided.

Endpoint: ```/api/wishlist/items/id={id}```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable:

```
id - wishlist Item id
```

Sample Request:
<!-- <details> -->

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "datePurchased": "2022-07-27T12:51:40.193Z",
  "product": {
    "oldVariantId": "string",
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
  "addedFromCart": true,
  "wishlistId": "string",
  "wishlistRef": "string",
  "prerelease": false,
  "disableNotification" : false
}
```
<!-- </details> -->

<summary>Response - 200 (OK Updated)</summary>

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "datePurchased": "2022-06-27T15:40:09.518Z",
  "id": "string",
  "product": {
    "oldVariantId": "string",
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
  "addedFromCart": true,
  "wishlistId": "string",
  "wishlistItemRef": "string",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "wishlistRef": "string",
   "prerelease": false,
  "disableNotification" : false
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

## Get all Items in a Wishlist by Wishlist Id
Returns a list of all wishlist items belonging to the given wishlist Id (TWC internal identifier).

Results are paginated, page size is 20, maximum 50.

If item does not exist, this method returns a ResourceNotFound error.

Endpoint: ```​/api​/wishlist​​/items​```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Param:  ` id - Wishlist Id `

<summary>Response - 200 (OK)</summary>

```json
[
    {
        "attributeGroups": {
            "additionalProp1": {
                "attributes": {
                    "additionalProp1": "string",
                    "additionalProp2": "string",
                    "additionalProp3": "string"
                },
                "description": "string"
            },
            "additionalProp2": {
                "attributes": {
                    "additionalProp1": "string",
                    "additionalProp2": "string",
                    "additionalProp3": "string"
                },
                "description": "string"
            },
            "additionalProp3": {
                "attributes": {
                    "additionalProp1": "string",
                    "additionalProp2": "string",
                    "additionalProp3": "string"
                },
                "description": "string"
            }
        },
        "datePurchased": "2022-06-27T15:40:39.119Z",
        "id": "string",
        "product": {
            "oldVariantId": "string",
            "productId": "string",
            "productRef": "string",
            "selectedVariantId": "string",
            "selectedVariantRef": "string"
        },
        "purchased": true,
        "addedFromCart": true,
        "wishlistId": "string",
        "wishlistItemRef": "string",
        "createdTime": "2022-08-24T07:28:12.000+0000",
        "modifiedTime": "2022-08-24T07:30:52.051+0000",
        "wishlistRef": "string",
         "prerelease": false,
         "disableNotification" : false
    }
]
```
git

## Get Wishlist Item by Item Id
Returns the wishlist item belonging to the given item Id (TWC internal item ID)

If the item does not exist, this method returns a ResourceNotFound error.

Endpoint: ```​/api​/wishlist​​/items​/{id}```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable: `, id - Wishlist Item Id `

<summary>Response - 200 (OK)</summary>

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "datePurchased": "2022-06-27T15:40:39.119Z",
  "id": "string",
  "product": {
    "oldVariantId": "string",
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
  "addedFromCart": true,
  "wishlistId": "string",
  "wishlistItemRef": "string",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "wishlistRef": "string",
   "prerelease": false,
  "disableNotification" : false
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

## Get Wishlist Item by Item Ref
Returns the wishlist item belonging to the given itemRef (retailer's own item identifier).

Note that itemRef is the client's unique identifier for a wishlist item associated with a single wishlist.  It is NOT the productRef, which typically could be the retailer's product SKU.

If the item does not exist, this method returns a ResourceNotFound error.

Endpoint: ```​/api​/wishlist​​/items​/ref/{wishlistItemRef}```
Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable: `, wishlistItemRef - Wishlist Item Ref `

<summary>Response - 200 (OK)</summary>

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "datePurchased": "2022-06-27T15:40:39.119Z",
  "id": "string",
  "product": {
    "oldVariantId": "string",
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
  "addedFromCart": true,
  "wishlistId": "string",
  "wishlistItemRef": "string",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "wishlistRef": "string",
   "prerelease": false,
  "disableNotification" : false
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


## Get Wishlist Item by WishlistId and Item Id
Returns the  wishlist item belonging to the given wishlist id and item id.

If the item does not exist, this method returns a ResourceNotFound error.

**THIS API IS DEPRECIATED**

Endpoint: ```​/api​/wishlist​/{wishlistId}​/items​/{id}```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable: `id - Id , wishlistId - Wishlist Id `

<summary>Response - 200 (OK)</summary>

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp2": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    },
    "additionalProp3": {
      "attributes": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "description": "string"
    }
  },
  "datePurchased": "2022-06-27T15:40:39.119Z",
  "id": "string",
  "product": {
    "oldVariantId": "string",
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
  "addedFromCart": true,
  "wishlistId": "string",
  "wishlistItemRef": "string",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "wishlistRef": "string",
  "prerelease": false,
  "disableNotification" : false
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
## Delete Wishlist Item by Id
Delete Wishlist item marks the item matching the given item ID (TWC internal platform ID) as deleted and produces an HTTP response confirming the action. 

If the wishlist/item does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/wishlist/items/{id}```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Parameters: `Id  : Wishlist item Id`

<summary>Response - 204 (Deleted)</summary> 

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

## Delete Wishlist Item by itemRef
Delete Wishlist Item by itemRef marks the item matching the given itemRef (retailer's own identifier) as deleted and produces an HTTP response confirming the action. 

Note that itemRef is the client's unique identifier for a wishlist item associated with a single wishlist.  It is NOT the productRef, which typically could be the retailer's product SKU.

If the wishlist/item does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/wishlist/items/{wishlistItemRef}/ref```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `wishlistItemRef  : Wishlist item Reference`

<summary>Response - 204 (Deleted)</summary> 

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
## Delete Wishlist Item by wishlist ID and item Id
Delete Wishlist item marks the item matching the given wishlist ID and item ID (TWC internal platform IDs) as deleted and produces an HTTP response confirming the action. 

If the wishlist/item does not exist, this method returns a ResourceNotFound error.

**THIS API IS DEPRECIATED**

Endpoint: ```/api/wishlist/{wishlistId}/items/{id}```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `Id  : Wishlist item Id, wishlistId : Wishlist Id`

<summary>Response - 204 (Deleted)</summary> 

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

***
[Back to Top](#wishlist-api)

[Back to Home](index.md#welcome-to-the-wishlist)

