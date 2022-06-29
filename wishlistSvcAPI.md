
[Back to Index](index.md)
***

# **Wishlist API**
The Wishlist resource stores information about a customer's wishlist, which includes the list products which the customer wish to buy.

one customer may have mulitple wishlist and also need a valid customer to create a wishlist.

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
      - [Delete Wishlist by ID/Ref](#delete-wishlist-by-idref)
      - [Find Wishlist by id/wishlistRef](#find-wishlist-by-idwishlistref)
      - [Find Wishlist by CustomerId](#find-wishlist-by-customerid)
      - [Find Wishlist by CustomerRef](#find-wishlist-by-customerref)
    - [**Wishlist Item Resource**](#wishlist-item-resource)
      - [Create a Wishlist Item](#create-a-wishlist-item)
      - [Update a Wishlist Item](#update-a-wishlist-item)
      - [Delete Wishlist Item by wishlist Id and item Id](#delete-wishlist-item-by-wishlist-id-and-item-id)
      - [Find Wishlist Item by WishlistId and Item Id](#find-wishlist-item-by-wishlistid-and-item-id)

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
Creates a new wishlist data set in the TWC system, then the wishlist is assigned to the respective customer.

Endpoint: ```/api/wishlists```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication`

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
      "datePurchased": "2022-06-20T05:55:48.831Z",
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
      "wishlistRef": "string"
    }
  ],
  "wishlistRef": "string"
}
```
<!-- </details> -->

Sample Response : 

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
    "oldVariantId": "string",
    "productId": "string",
    "productRef": "string",
    "selectedVariantId": "string",
    "selectedVariantRef": "string"
  },
  "purchased": true,
  "wishlistId": "string",
  "wishlistItemRef": "string",
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

OAuth 2.0 Scopes: `Tenant authentication`

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
      "datePurchased": "2022-06-20T06:29:49.032Z",
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
      "wishlistRef": "string"
    }
  ],
  "wishlistRef": "string"
}
```
<!-- </details> -->

Sample Response : 

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


## Delete Wishlist by ID/Ref
Deleting a Wishlist marks the wishlist as deleted and produces the HTTP response confirming the action.
If the wishlist does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/wishlist```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication`

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request Parameters: `Id  : Wishlist Id ,wishlistRef : Wishlist Reference `



 
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
Returns the  wishlist belongs to the given  Id and Ref.
If the wishlist does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/wishlists/```

Method: ``` GET ``` 

OAuth 2.0 Scopes: `Tenant authentication`

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request Parameters: `Id  : Wishlist Id ,wishlistRef : Wishlist Reference `  

Sample Response:
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
        "oldVariantId": "string",
        "productId": "string",
        "productRef": "string",
        "selectedVariantId": "string",
        "selectedVariantRef": "string"
      },
      "purchased": true,
      "wishlistId": "string",
      "wishlistItemRef": "string",
      "wishlistRef": "string"
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
Returns the list of wishlists belongs to the given customer id.
If the wishlist does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/wishlists/customer/{customerId}```

Method: ``` GET ``` 

OAuth 2.0 Scopes: `Tenant authentication`

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable: `customerId - Unique Customer Id`

Sample Response:

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
          "oldVariantId": "string",
          "productId": "string",
          "productRef": "string",
          "selectedVariantId": "string",
          "selectedVariantRef": "string"
        },
        "purchased": true,
        "wishlistId": "string",
        "wishlistItemRef": "string",
        "wishlistRef": "string"
      }
    ],
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
Returns the list of wishlists belongs to the given customer reference.
If the wishlist does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/wishlists/customer/{customerRef}/byref```

Method: ``` GET ``` 

OAuth 2.0 Scopes: `Tenant authentication`

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable: `customerRef - Unique Customer Ref`

Sample Response:

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
          "oldVariantId": "string",
          "productId": "string",
          "productRef": "string",
          "selectedVariantId": "string",
          "selectedVariantRef": "string"
        },
        "purchased": true,
        "wishlistId": "string",
        "wishlistItemRef": "string",
        "wishlistRef": "string"
      }
    ],
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
## **Wishlist Item Resource**

## Create a Wishlist Item
Creates a new wishlist item data set  into an existing wishlist in the TWC system.

Endpoint: ```/api/wishlist/items```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication`

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
  "wishlistId": "string",
  "wishlistItemRef": "string",
  "wishlistRef": "string"
}
```

<!-- </details> -->

Sample Response:

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
  "wishlistId": "string",
  "wishlistItemRef": "string",
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

### Update a Wishlist Item
Updates Wishlist item data set in the TWC system.

Endpoint: ```/api/wishlist/items```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication`

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
  "wishlistId": "string",
  "wishlistItemRef": "string",
  "wishlistRef": "string"
}
```
<!-- </details> -->

Sample Response

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
  "wishlistId": "string",
  "wishlistItemRef": "string",
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
### Delete Wishlist Item by wishlist Id and item Id
Deleting a Wishlist item marks the item as deleted and produces the HTTP response confirming the action.
If the wishlist/item does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/wishlist/{wishlistId}/items/{id}```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication`

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `Id  : Wishlist item Id, wishlistId : Wishlist Id`

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


### Find Wishlist Item by WishlistId and Item Id
Returns the  wishlist item belongs to the given wishlist id and item id
If the item does not exist, this method returns a ResourceNotFound error.

Endpoint: ```​/api​/wishlist​/{wishlistId}​/items​/{id}```

Method: ``` GET ``` 

OAuth 2.0 Scopes: `Tenant authentication`

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable: `id - Id , wishlistId - Wishlist Id `

Sample Response:

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
  "wishlistId": "string",
  "wishlistItemRef": "string",
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

***
[Back to Home](index.md)

[Back to Index](index.md)