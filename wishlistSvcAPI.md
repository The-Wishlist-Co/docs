
[Back to Home](index.md#welcome-to-the-wishlist)


# **Wishlist API**
The Wishlist resource stores information about a customer's wishlist.

One customer may have mulitple wishlists.  You can only create a wishlist for a valid customer.

### Index

***

- [**Wishlist API**](#wishlist-api)
    - [Index](#index)
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
  - [Lookup Wishlist By Customer](#lookup-wishlist-by-customer)
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
  - [Add multiple Items to a Wishlist](#add-multiple-wishlist-items)

## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.

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

<!-- </details>

<details> -->
##  Add Multiple Wishlist Item
 <!-- <summary>WishList Item</summary> -->


```wishlistId``` - string - the unique id of the respective wishlist. please provide either id or ref

```wishlistRef``` - string- reference of the respective wishlist. please provide either id or ref

```itemId``` - List- the list of items with id value like product id ,variant id. Please provide either itemId or itemRef

```itemRef``` - List- the list of items with id value like product ref ,variant ref. Please provide  either itemId or itemRef 



<!-- </details>


<!-- </details> -->



## **REST Endpoints**

## **Wishlist Resource**

## Create a Wishlist
Creates a new wishlist data set in the TWC system, then the wishlist is assigned to the respective customer.

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
  "customerId": "string",
  "customerRef": "string",
  "deleted": "true",
  "description": "string",
  "id": "string",
  "isPrivate": "true",
  "name": "string",
  "id":"string",
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


## Update a Wishlist
Updates Wishlist data set in the TWC system.

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
  "customerId": "string",
  "customerRef": "string",
  "deleted": "true",
  "description": "string",
  "id": "string",
  "isPrivate": "true",
  "name": "string",
  "id":"string",
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



## Update a Wishlist By ID
Updates Wishlist data set in the TWC system.

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
  "customerId": "string",
  "customerRef": "string",
  "deleted": "true",
  "description": "string",
  "id": "string",
  "isPrivate": "true",
  "name": "string",
  "id":"string",
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


## Update a Wishlist By Ref
Updates Wishlist data set in the TWC system.

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
  "customerId": "string",
  "customerRef": "string",
  "deleted": "true",
  "description": "string",
  "id": "string",
  "isPrivate": "true",
  "name": "string",
  "id":"string",
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




## Find Wishlist by id/wishlistRef
Returns the wishlist that belongs to the given Id and/or Ref.  If the wishlist does not exist, this method returns a ResourceNotFound error.

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

## Find Wishlist by Id

Returns the  wishlist belongs to the given  Id.
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

## Find Wishlist by Wishlist Reference
Returns the wishlist that belongs to the given Ref.
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

## Find Wishlist by CustomerId
Returns the list of wishlists that belong to the given customer id.  If no wishlists exist, this method returns a ResourceNotFound error.

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

## Find Wishlist by CustomerRef
Returns the list of wishlists that belong to the given customer reference.
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

## Lookup Wishlist By Customer

Returns the list of wishlists belonging to the given customer reference.
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
Deleting a Wishlist marks the wishlist as deleted and produces an HTTP response confirming the action.
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
Deleting a Wishlist marks the wishlist as deleted and produces an HTTP response confirming the action.
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
Deleting a Wishlist marks the wishlist as deleted and produces an HTTP response confirming the action.
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
Creates a new wishlist item data set into an existing wishlist in the TWC system.

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
Upload (add) multiple wishlist items into an existing wishlist in the TWC system.

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
Updates the Wishlist item data set in the TWC system.

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

Updates Wishlist item data set in the TWC system based on Wish list Item Ref.

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

Updates Wishlist item data set in the TWC system based on Wish list Item Ref.

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

## Find all Items in a Wishlist by Wishlist Id
Returns a list of all wishlist items belonging to the given wishlist id.
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



## Find Wishlist Item by Item Id
Returns the  wishlist item belonging to the given wishlist item id
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

## Find Wishlist Item by Item Ref
Returns the  wishlist item belonging to the given wishlist item Ref
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


## Find Wishlist Item by WishlistId and Item Id
Returns the  wishlist item belonging to the given wishlist id and item id
If the item does not exist, this method returns a ResourceNotFound error.

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
Deleting a Wishlist item marks the item as deleted and produces an HTTP response confirming the action.
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

## Delete Wishlist Item by WishlistItemRef
Deleting a Wishlist item marks the item as deleted and produces an HTTP response confirming the action.
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
## Delete Wishlist Item by wishlist Id and item Id
Deleting a Wishlist item marks the item as deleted and produces an HTTP response confirming the action.
If the wishlist/item does not exist, this method returns a ResourceNotFound error.

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

## Add multiple Wishlist Items
Add  multiple items to an existing wishlist in the TWC system.

Endpoint: ```/api/wishlist/add-multiple-items```

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


***
[Back to Top](#wishlist-api)

[Back to Home](index.md#welcome-to-the-wishlist)

