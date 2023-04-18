
[Back to Home](index.md#welcome-to-the-wishlist)


# **Wishlist API**
The Wishlist API enables the management of customer wishlists.  

In most situations, The Wishlist platform will be the master data source for Wishlists, as it is able to manage wishlist information from multiple sources (e.g. website or physical stores); then trigger events based on saved wishlist items; and send wishlist information to 3rd party systems such as marketing automation platforms like Emarsys, Klaviyo and DotDigital.  

One customer may have mulitple wishlists.  You can only create a wishlist for a valid customer.

A wishlist is created 'empty' and items added later, either one by one, or multiple items can be added at the same time.

### Index

***

- [**Wishlist API**](#wishlist-api)
    <!-- - [Index](#index) -->
    - [**Representations**](#representations)
        - [Wishlist](#wishlist)
        - [Wishlist Item](#wishlist-item)
        - [Product](#product)
    - [**REST Endpoints**](#rest-endpoints)
        - [**Wishlist Resource**](#wishlist-resource)
            - [Create a Wishlist](#create-a-wishlist)
            - [Update a Wishlist](#update-a-wishlist)
            - [Update a Wishlist By ID](#update-a-wishlist-by-id)
            - [Update a Wishlist By Ref](#update-a-wishlist-by-ref)
            - [Find Wishlist by id/wishlistRef](#find-wishlist-by-idwishlistref)
            - [Find Wishlist by Id](#find-wishlist-by-id)
            - [Find Wishlist by Wishlist Reference](#find-wishlist-by-wishlist-reference)
            - [Find Wishlist by CustomerId](#find-wishlist-by-customerid)
            - [Find Wishlist by CustomerRef](#find-wishlist-by-customerref)
            - [Lookup Wishlist By CustomerId](#lookup-wishlist-by-customer)
            - [Delete Wishlist by ID/Ref](#delete-wishlist-by-idref)
            - [Delete Wishlist by ID](#delete-wishlist-by-id)
            - [Delete Wishlist by Ref](#delete-wishlist-by-ref)
        - [**Wishlist Item Resource**](#wishlist-item-resource)
            - [Create a Wishlist Item](#create-a-wishlist-item)
            - [Upload multiple Wishlist Items](#upload-multiple-wishlist-items)
            - [Update a Wishlist Item](#update-a-wishlist-item)
            - [Update a Wishlist Item By Ref](#update-a-wishlist-item-by-ref)
            - [Update a Wishlist Item By Id](#update-a-wishlist-item-by-id)
            - [Find all Items in a Wishlist by Wishlist Id](#find-all-items-in-a-wishlist-by-wishlist-id)
            - [Find Wishlist Item by Item Id](#find-wishlist-item-by-item-id)
            - [Find Wishlist Item by Item Ref](#find-wishlist-item-by-item-ref)
            - [Find Wishlist Item by WishlistId and Item Id](#find-wishlist-item-by-wishlistid-and-item-id)
            - [Delete Wishlist Item by Id](#delete-wishlist-item-by-id)
            - [Delete Wishlist Item by WishlistItemRef](#delete-wishlist-item-by-wishlistitemref)
            - [Delete Wishlist Item by wishlist Id and item Id](#delete-wishlist-item-by-wishlist-id-and-item-id)

## **Representations**

All requests or responses are JSON objects

##  Wishlist

<!-- <details> -->
 <!-- <summary>WishList</summary> -->

```customerId``` - string - the unique id of the customer

```customerRef``` - string - the reference of the customer

```deleted``` - boolean - to indicate the wishlist is deleted to not

```description``` - string - description of the wishlist

```id``` - string - the unique id of the wishlist. it will automatically generate at the time of wishlist creation.

```isPrivate``` - boolean

```name``` - string - name of the wishlist

```wishlistRef``` - string- reference of the wishlist

```attributeGroups```- to add any additional information

```lastEvaluatedId```- Last ealuated UID of the list of Wishlists or wishlist items in a wishlist depending on api.

```resultCount``` Count of items present in in the response.

<!-- </details>
<details> -->
##  Wishlist Item
 <!-- <summary>WishList Item</summary> -->

```datePurchased``` - DateTime - the Date of purchase if the wishlist items is purchased.

```wishlistId``` - string - the unique id of the respective wishlist.

```purchased``` - boolean - to indicate the wishlist item is purchased to not

```wishlistItemRef``` - string - the unique reference of the wishlist item

```id``` - string - the unique id of the wishlist item. it will automatically generate at the time of wishlist item creation.

```wishlistRef``` - string- reference of the respective wishlist

```addedFromCart``` - boolean - to indicate whether added from Cart or not.

```prerelease``` - boolean- product prerelease notification enabled

```disableNotification``` - boolean- disable notification 

<!-- </details>

<details> -->
 <!-- <summary>Product</summary> -->
## Product


```oldVariantId``` - string - the existing product variant id. this needs only incase of updating an existing variant in a wishlist item.

```productId``` - string - the unique id of the product

```productRef``` - string - the unique ref of the product

```selectedVariantId``` - string- the unique id of the product variant which the customer need to add.

```selectedVariantRef``` - string- the unique ref of the product variant which the customer need to add.

<!-- </details> -->

## **REST Endpoints**

## **Wishlist Resource**

## Create a Wishlist
Creates a new wishlist.  Requires the customer to be created first.  

Endpoint: ```/api/wishlists```

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
  "customerId": "string",
  "customerRef": "string",
  "deleted": "true",
  "description": "string",
  "id": "string",
  "isPrivate": "true",
  "name": "string"
  ,
  "wishlistRef": "string"
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
  "datePurchased": "2022-06-27T15:34:58.540Z",
  "id": "string",
  "product": {
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
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


## Update a Wishlist
Used to update any metadata about a wishlist, for example, attribute groups, staff/store ID or wishlist name.  *This API is NOT used to update items on the wishlist*

You can update by internal Wishlist ID or wishlistRef, which is the retailer's own ID (which, for example may be assigned in the ecommerce system)

**THIS API IS DEPRECIATED.  PLEASE USE UDATE WISHLIST BY ID OR WISHLISTREF BELOW**

Endpoint: ```/api/wishlists```

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
  "customerId": "string",
  "customerRef": "string",
  "deleted": true,
  "description": "string",
  "id": "string",
  "isPrivate": true,
  "name": "string",
  "wishlistRef": "string"
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
  "datePurchased": "2022-06-27T15:35:39.044Z",
  "id": "string",
  "product": {
    "oldVariantId": "string",
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
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
  "deleted": true,
  "description": "string",
  "isPrivate": true,
  "name": "string",
  
  "wishlistRef": "string"
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
  "datePurchased": "2022-06-27T15:35:39.044Z",
  "id": "string",
  "product": {
    "oldVariantId": "string",
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
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
  "deleted": true,
  "description": "string",
  "isPrivate": true,
  "name": "string",
  "wishlistRef": "string"
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
  "datePurchased": "2022-06-27T15:35:39.044Z",
  "id": "string",
  "product": {
    "oldVariantId": "string",
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
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




## Get Wishlist by id/wishlistRef
Retrieves the wishlist that belongs to the given Id and/or wishlistRef.  If the wishlist does not exist, this method returns a ResourceNotFound error.

**THIS API IS DEPRECIATED.  PLEASE USE GET WISHLIST BY ID OR GET WISHLIST BY WISHLISTREF**

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

Returns the wishlist that matches the given internal TWC Platform identifier.

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
Returns the wishlist that matches the provided wishlistRef (which is the retailer's own wishlist identifier).

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
Returns the list of wishlists that belong to the given customer id (Customer ID is the TWC internal identifier).  

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
Returns the list of wishlists that belong to the given customer reference (which is the retailer's own customer identifier)

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

Returns the list of wishlists that belong to either the internal TWC customer Id, or the retailer's own customerRef.

Results are paginated.  Maximum page size is 50, with the default being 20.

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
Adds a wishlist item into an existing wishlist.  The wishlist can be identified by either the TWC internal ID, or the wishlistRef, which is the retailer's own wishlist identifier.  

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


## Upload multiple Wishlist Items
Adds multiple wishlist items into an existing wishlist.

**THIS API IS DEPRECIATED.  USE ADD-MULTIPLE-ITEMS**

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

