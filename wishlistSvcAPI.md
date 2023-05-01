
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
    - [Create a wishlist](#ceate-a-wishlist)
    - [Update a Wishlist](#update-a-wishlist)
    - [Get a Wishlist](#get-wishlist)
    - [Get customer wishlists](#get-customer-wishlists)
    - [Delete Wishlist](#delete-wishlist)
  - [**WishlistItem**](#wishlistitem)
    - [Create a Wishlist Item](#create-a-wishlist-item)
    - [Add  Wishlist Item](#create-a-wishlist-item)
    - [Add multiple items to wishlist](#add-multple-wishlist-items)
    - [Update Wishlist Item](#update-wishlistitems)
    - [Get Wishlist Items](#get-wishlist-items)
    - [Delete Wishlist Item](#delete-wishlist-item)

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

# **Endpoints**
## **Wishlist**
### Ceate a wishlist
Creates a new wishlist. This API requires wishlist request to be passed to API. Customer must be created before creating a wishlist.

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
Used to update any metadata about a wishlist, for example, attribute groups, staff/store ID or wishlist name.  *Note this API is NOT used to update items on the wishlist.*

As this API uses Wishlist ID, then you can use it to update wishlistRef, which is the retailer's own wishlit ID (which, for example may be assigned in the ecommerce system)

Endpoint: ```/api/wishlists/id={id}```


| Endpoint| ```/api/wishlists/id={id}``` |
|-----------|---------------|
| Method    | PUT          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```id``` This is the TWC generated unique ID of the wishlist being updated. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|


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
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
- 400 Invalid input
```

### Update Wishlist By Ref
Used to update any metadata about a wishlist, for example, attribute groups, staff/store ID or wishlist name.  *Note this API is NOT used to update items on the wishlist.*

As this API uses wishlistRef, which is the retailer's own wishlit ID (which, for example may be assigned in the ecommerce system)

| Endpoint| ```/api/wishlists/ref={ref}``` |
|-----------|---------------|
| Method    | PUT          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| url path variable |```ref``` This is the retailers reference ID of the wishlist being updated |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|


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
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
- 400 Invalid input
```

### Update wishlist with either ID/Ref

Used to update any metadata about a wishlist, for example, attribute groups, staff/store ID or wishlist name.  *This API is NOT used to update items on the wishlist*

You can update by internal Wishlist ID or wishlistRef, which is the retailer's own ID (which, for example may be assigned in the ecommerce system)

**THIS API IS DEPRECIATED.  PLEASE USE UDATE WISHLIST BY ID OR WISHLISTREF BELOW**

| Endpoint| ```/api/wishlists```|
|-----------|---------------|
| Method    | PUT          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
|How to get access token| [Tenant Authentication](authenticationsvcApi.md)|


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
<details>
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
</details>

<details>
<summary>HTTP Status Codes </summary>

``` 
- 200 OK
- 400 Bad request
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```
</details>

## GET Wishlist
Below APIs provide mechanism to get wishlists by ID, reference ID or customer. 

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
| ```pageSize``` | This parameter will determine the number of wishlist items returned in the API response. Default page size is 20 and max is 50. |
| ```lastItemId``` | This parameter will determine which items to return. API returns wishlist items in the ascending order of their TWC generated wishlist ID. This parameter will inform API to respond items with ID greater than, but excluding the provided value. |


When provided with valid inputs, API responds with a ```application/json``` type content.
<details>
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
</details>


The API responds with below statuses. HTTP status differ depending on the input, access token etc.
<details>
<summary>HTTP Status Codes </summary>

``` 
- 200 OK
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```
</details>


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
| ```pageSize``` | This parameter will determine the number of wishlist items returned in the API response. Default page size is 20 and max is 50. |
| ```lastItemId``` | This parameter will determine which items to return. API returns wishlist items in the ascending order of their TWC generated wishlist ID. This parameter will inform API to respond items with ID greater than, but excluding the provided value. |


When provided with valid inputs, API responds with a ```application/json``` type content.

<details>
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
</details>


The API responds with below statuses. HTTP status differ depending on the input, access token etc.

<details>
<summary>HTTP Status Codes </summary>

``` 
- 200 OK
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```
</details>



### Get Wishlist by id/wishlistRef
Retrieves the wishlist and the wishlist items that belongs to the given Id and/or wishlistRef.  If the wishlist does not exist, this method returns a ResourceNotFound error.

The returned item array is paginated - 20 default (50 maximum).  The API will respond with the item count in the page, and the itemID the for the last item (lastitemID) returned for that response, which should then be used for the  subsequent API call to retrieve the next page.  


| Endpoint| ```/api/wishlists/```|
|-----------|---------------|
| Method    | GET          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|


| Query Parameters | What is it for ? |
|---|---|
| ```id``` | This is the TWC system generated unique wishlist ID. e.g: ```67ccc612-0f1b-4d9d-b69e-d43511c6782d```. API will query database to for wishlists by ID. |
| ```wishlistRef``` | This is the retailer assigned unique wishlist reference ID. e.g: ```WISH0001```. API will query database to for wishlists by reference ID. |
| ```pageSize``` | This parameter will determine the number of wishlist items returned in the API response. Default page size is 20 and max is 50. |
| ```lastItemId``` | This parameter will determine which items to return. API returns wishlist items in the ascending order of their TWC generated wishlist ID. This parameter will inform API to respond items with ID greater than, but excluding the provided value. |



When provided with valid inputs, API responds with a ```application/json``` type content.

<details>
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
</details>        

<details>
<summary>HTTP Status Code:</summary>

``` 
- 200 OK
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

</details>

## Get customer wishlists

Returns the collection of wishlists that belong to either the internal TWC customer Id, or the retailer's own customerRef.

The returned list is paginated - 20 default (50 maximum).  The API will respond with the number of wishlists returned in the page, and the wishlistID for the for the last wishlist returned for that response, which should then be used for the  subsequent API call to retrieve the next page.  

If no wishlists exist, this method returns a ResourceNotFound error.


| Endpoint| ```/api/wishlists/lookup```|
|-----------|---------------|
| Method    | GET          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

| Query Parameters | What is it for ? |
|---|---|
| ```customerId``` | This is the TWC generated unique customer ID. e.g: ```67ccc612-0f1b-4d9d-b69e-d43511c6782d```. API will query database to for wishlists that belong to customer with the given ID. |
| ```customerRef``` | This is the retailer assigned unique customer reference ID. e.g: ```CUST1111```. API will query database to for wishlists that belong to customer with the given reference ID. |
| ```pageSize``` | This parameter will determine the number of wishlist items returned in the API response. Default page size is 20 and max is 50. |
| ```lastItemId``` | This parameter will determine which items to return. API returns wishlist items in the ascending order of their TWC generated wishlist ID. This parameter will inform API to respond items with ID greater than, but excluding the provided value. |

<details>
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
</details>


<details>
<summary>HTTP Status Codes</summary>

``` 
- 200 OK
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```
</details>


## Delete Wishlist
### Delete Wishlist by ID/Ref
Delete Wishlist marks the wishlist as deleted and produces an HTTP response confirming the action.  The Wishlist is identified either by the TWC Internal wishlist Id or the retailers own wishlistRef

If the wishlist does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlists/```|
|-----------|---------------|
| Method    | DELETE          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

| Query Parameters | What is it for ? |
|---|---|
| ```id``` | This is the TWC system generated unique wishlist ID. e.g: ```67ccc612-0f1b-4d9d-b69e-d43511c6782d```. API will remove the wishlists for the given ID. Either ```id``` or ```wishlistRef``` must be provided with this API call.|
| ```wishlistRef``` | This is the retailer assigned unique wishlist reference ID. e.g: ```WISH0001```. API will remove the wishlists for the given retailer wishlist reference ID. Either ```id``` or ```wishlistRef``` must be provided with this API call.|

<summary>Response - 204 (Deleted)</summary> 

<details>
<summary>HTTP Status Code</summary> 

``` 
- 204 Deleted
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```
</details>

## Delete Wishlist by ID
Delete Wishlist marks the matching wishlist as deleted and produces an HTTP response confirming the action.  In this case the Wishlist is identified by the TWC Internal wishlist Id.

If the wishlist does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlists/{id}```|
|-----------|---------------|
| Method    | DELETE          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

| Path Parameters | What is it for ? |
|---|---|
| ```id``` | This is the TWC system generated unique wishlist ID. e.g: ```67ccc612-0f1b-4d9d-b69e-d43511c6782d```. API will remove the wishlists for the given ID.|


<summary>Response - 204 (Deleted)</summary> 

<details>
<summary>HTTP Status Code</summary> 

``` 
- 204 Deleted
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```
</details>

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
| ```wishlistRef``` | This is the retailer generated wishlist reference ID. e.g: ```WISH1111```. API will remove the wishlists for the given reference ID, if exists. |


<summary>Response - 204 (Deleted)</summary> 

<details>
<summary>HTTP Status Code</summary> 

``` 
- 204 Deleted
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```
</details>

# **WishlistItem**

## Create a Wishlist Item
Adds a sinble wishlist item into an existing wishlist.  The wishlist can be identified by either the TWC internal ID, or the wishlistRef, which is the retailer's own wishlist identifier.  


| Endpoint| ```/api/wishlist/items```|
|-----------|---------------|
| Method    | POST          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|


<details>
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

</details>


<details>
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
</details>

<details>
<summary>HTTP Status Code: </summary>


``` 
- 200 OK
- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```
</details>

## Add multple Wishlist Items
Add multiple items to an existing wishlist in the TWC system.


| Endpoint| ```/api/wishlist/add-items```|
|-----------|---------------|
| Method    | POST          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|


<details>
<summary>Sample Request</summary>

```json
{
    "wishlistId": "67ccc612-0f1b-4d9d-b69e-d43511c6782d",
    "itemId": [
        {
            "addedFromCart": true,
            "attributeGroups": {
                "cart_info": {
                    "attributes": {
                        "cart_id": "CART1111",
                        "channel": "mobile-app"
                    },
                    "description": "cart related attributes"
                }
            },
            "productId": "ede20e6c-88c8-41d9-b0a5-a631871b23d2",
            "selectedVariantId": "b72e501d-d87a-40bb-b0bb-2d4c3cbb4f0a",
            "wishlistItemRef": "WI2000131662"
        }
    ]
}
```
</details>

<details>
<summary>Status Codes</summary>

``` 
- 202 Accepted
- 400 Bad request
- 401 Unauthorized
- 403 Forbidden 
- 409 Conflict
```

</details>

## Update WishlistItems

Below APIs provide mechanisms to update wishlist items. Retailer may choose the most appropriate API that suite their circumstance.

### Update a Wishlist Item

Update a wishlist item, for example to change the selected variant.  Developer must supply either the wishlist ID and item ID (both internal TWC values) or the wishlistRef and itemRef (both retailer's own identifiers).

Note that itemRef is the client's unique identifier for a wishlist item associated with a single wishlist.  It is NOT the productRef, which typically could be the retailer's product SKU.

If the variant is being changed, then the original variant ID (TWC internal ID) must also be provided.


| Endpoint| ```/api/wishlist/items```|
|-----------|---------------|
| Method    | PUT           |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|


<details>
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
</details>


<details>
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
</details>

<details>
<summary>HTTP Status Code:</summary>

``` 
- 200 OK
- 400 Bad request
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

</details>


### Update a Wishlist Item By Ref

Update a wishlist item, for example to change the selected variant.  Developer must supply the wishlistRef and itemRef (both retailer's own identifiers).

Note that itemRef is the client's unique identifier for a wishlist item associated with a single wishlist.  It is NOT the productRef, which typically could be the retailer's product SKU.

If the variant is being changed, then the original variant ID (TWC internal ID) must also be provided.

| Endpoint| ```/api/wishlist/items/ref={ref}```|
|-----------|---------------|
| Method    | PUT           |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| path variable | ```ref``` ref is the retailer assigned unique the wishlist item ID. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|


<details>
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
</details>


<details>
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
</details>

<details>
<summary>HTTP Status Code:</summary>

``` 
- 200 OK
- 400 Bad request
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

</details>

### Update a Wishlist Item By Id

Update a wishlist item, for example to change the selected variant.  Developer must supply the wishlist ID and item ID (both TWC internal identifiers).

If the variant is being changed, then the original variant ID (TWC internal ID) must also be provided.

| Endpoint| ```/api/wishlist/items/id={id}```|
|-----------|---------------|
| Method    | PUT           |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| path variable | ```id``` id is the TWC generated unique ID of the wishlist item. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|


<details>
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
</details>


<details>
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
</details>

<details>
<summary>HTTP Status Code:</summary>

``` 
- 200 OK
- 400 Bad request
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

</details>

## Get Wishlist Items

Below APIs provide mechanisms to get all items in a single wishlist or a single wishlist item.

### Get all Items in a Wishlist by Wishlist Id
Returns a list of all wishlist items belonging to the given wishlist Id (TWC internal identifier).

Results are paginated, page size is 20, maximum 50.

If item does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlist/items```|
|-----------|---------------|
| Method    | GET           |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|


| Query Parameters | What is it for ? |
|---|---|
| ```id``` | This is the TWC system generated unique wishlist ID. e.g: ```67ccc612-0f1b-4d9d-b69e-d43511c6782d```. API will query database to for wishlists by ID. |
| ```wishlistRef``` | This is the retailer assigned unique wishlist reference ID. e.g: ```WISH0001```. API will query database to for wishlists by reference ID. |
| ```pageSize``` | This parameter will determine the number of wishlist items returned in the API response. Default page size is 20 and max is 50. |
| ```lastItemId``` | This parameter will determine which items to return. API returns wishlist items in the ascending order of their TWC generated wishlist ID. This parameter will inform API to respond items with ID greater than, but excluding the provided value. |


<details>
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
</details>


### Get Wishlist Item by Item Id
Returns the wishlist item belonging to the given item Id (TWC internal item ID)

If the item does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlist/items/{id}```|
|-----------|---------------|
| Method    | GET           |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| path variable | ```id``` id is the TWC generated unique ID of the wishlist item. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<details>
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

</details>

</details>
<summary>HTTP Status Code: </summary>

``` 
- 200 OK
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```
</details>

### Get Wishlist Item by Item Ref
Returns the wishlist item belonging to the given itemRef (retailer's own item identifier).

Note that itemRef is the client's unique identifier for a wishlist item associated with a single wishlist.  It is NOT the productRef, which typically could be the retailer's product SKU.

If the item does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlist/items/ref={wishlistItemRef}```|
|-----------|---------------|
| Method    | GET           |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| path variable | ```wishlistItemRef``` is the retailer assigned unique wishlist reference ID. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<details>
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

</details>

</details>
<summary>HTTP Status Code: </summary>

``` 
- 200 OK
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```
</details>


## Delete Wishlist Item

### Delete Wishlist Item by Id
Delete Wishlist item marks the item matching the given item ID (TWC internal platform ID) as deleted and produces an HTTP response confirming the action. 

If the wishlist/item does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlist/items/{id}```|
|-----------|---------------|
| Method    | DELETE          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| ```id``` | This is the TWC system generated unique wishlist item ID. e.g: ```67ccc612-0f1b-4d9d-b69e-d43511c6782d```. API will remove the wishlist item for the given ID, if exists. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<summary>Response - 204 (Deleted)</summary> 

<details>
<summary>HTTP Status Code</summary> 

``` 
- 204 Deleted
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```
</details>


### Delete Wishlist Item by itemRef
Delete Wishlist Item by itemRef marks the item matching the given itemRef (retailer's own identifier) as deleted and produces an HTTP response confirming the action. 

Note that itemRef is the client's unique identifier for a wishlist item associated with a single wishlist.  It is NOT the productRef, which typically could be the retailer's product SKU.

If the wishlist/item does not exist, this method returns a ResourceNotFound error.

| Endpoint| ```/api/wishlist/items/{wishlistItemRef}/ref```|
|-----------|---------------|
| Method    | DELETE          |
| Headers   | Content-Type: ```application/json``` <br> X-TWC-Tenant ```<tenant-key>``` <br> Authorization ```<tenant-access-token>```
| ```wishlistItemRef``` | This is the TWC retailer assigned unique wishlist item ID. e.g: ```WISHITEM111111```. API will remove the wishlist item for the given reference ID, if exists. |
| How to get access token | [Tenant Authentication](authenticationsvcApi.md)|

<summary>Response - 204 (Deleted)</summary> 

<details>
<summary>HTTP Status Code</summary> 

``` 
- 204 Deleted
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```
</details>



***
[Back to Top](#wishlist-api)

[Back to Home](index.md#welcome-to-the-wishlist)

