
[Back to Home](index.md#welcome-to-the-wishlist)


# **Inventory API**

The inventory API is used to manage locations (both warehouses and stores), and stock levels within these locations

TWC automatically synchronises inventory with our Shopify App, so this API is typically not used by retailers.   It is is provided for those retailers that want to update inventory in real-time within TWC, however in most non-Shopify situations, inventory is synchronised via regular batch updates.

There is a 1:1 relationship between a product variant and an inventory level. Each product variant includes the ID of its related inventory level. You can use the product variant ID to query the InventoryLevel resource to retrieve the location and quantity for an inventory item.

Each **inventory level** belongs to one product variant and has one location. For every location where an inventory item can be stocked, there's an inventory level that represents the product variant quantities relating to that location.

An **inventory location** represents a geographical location where your stores, pop-up stores, headquarters, and warehouses exist. You can use the Location resource to track sales, manage inventory, and configure the tax rates to apply at checkout. 

### Index

***

- [**Inventory API**](#inventory-api)
    <!-- - [Index](#index) -->
    - [**Representations**](#representations)
    - [**REST Endpoints**](#rest-endpoints)
      - [**Location Resource**](#location-resource)
        - [Create an inventory Location](#create-an-inventory-location)
        - [Create multiple inventory Locations](#create-multiple-inventory-locations)
        - [Update an inventory Location By Id](#update-an-inventory-location-by-id)
        - [Update an inventory Location By Ref](#update-an-inventory-location-by-ref)
        - [Find Inventory Location by id and locationRef](#find-inventory-location-by-id-and-locationref)
        - [Delete Inventory Location](#delete-inventory-location)
      - [**Stock Level Resource**](#stock-level-resource)
        - [Create an inventory level](#create-an-inventory-level)
        - [Create Multiple inventory level](#create-multiple-inventory-level)
        - [Update an inventory level](#update-an-inventory-level)
        - [Update Stock By Id](#update-stock-by-id)
        - [Update Stock By Ref](#update-stock-by-ref)
        - [Find Inventory level by id and stockRef](#find-inventory-level-by-id-and-stockref)
        - [Find Inventory level for product and location](#find-inventory-level-for-product-and-location)
        - [Find Aggregated inventory level for a product variant](#find-aggregated-inventory-level-for-a-product-variant)

## **Representations**

All requests or responses are JSON objects.


<!-- <details> -->
 <summary><font size="4">Location </font></summary>

```id``` - string -The unique ID of the location. It will autmatically generate while creating the location.

```locationRef``` - string -The unique reference of the location.

```locationType``` - string -The location type  of the location: STORE OR PICKUP_POINT

```email``` - string -The email  of the store

```url``` - string -The url   of the store location

```name``` - string -The name   of the store

```longitude``` - string -The longitude  of the location

```latitude``` - string -The latitude  of the location

<!-- <details> -->
 <summary><font size="4">Address </font></summary>

```building``` - string - The location's building address.

```city``` - string - The city the location is in.

```contactPerson``` - string - The location's contact person

```countryIsocode``` - string - The two-letter code (ISO 3166-1 alpha-2 format) corresponding to country the location is in.

```countryName``` - string - The location's country name

```country``` - string - The country the location is in.

```fax``` - string - The location's fax details

```level``` - string - 

```phone``` - string - The phone number of the location. This value can contain special characters, such as - or +.

```postcode``` - string - The location's post code

```state``` - string - The location's state name

```street``` - string - The location's street address.

```streetNumber``` - string - The location's street number.

```createdTime``` - Date - ISo date format for the resource creation time.

```modifiedTime``` -  Date - ISo date format for the resource update time.

 <!-- </details> -->
<!-- </details> -->

<!-- <details> -->
 <summary><font size="4">Inventory Level </font></summary>

```deleted``` - boolean - The inventory level is deleted or not

```excludedQuantity``` - number - 

```futureStock``` - boolean 

```id``` - string - The unique id of the inventory level.

```locationId``` - string - The ID of the location that the inventory level belongs to. To find the ID of the location, use the Location resource.

```productVariantId``` - string - The ID of the product variant that the inventory level belongs to. To find the ID of the variant, use the product resource.

```reserved``` - number - 

```status``` - string - The currenc status of the inventory level. such as IN_STOCK,OUT_OF_STOCK, etc

```stockDate``` - The date and time (ISO 8601 format) when the inventory level was created.

```stockOnHand``` - number - The available quantity of an product variant at the inventory level's associated location

```stockRef``` - string - The unique reference of the inventory level

<!-- </details> -->

## **REST Endpoints**

## **Location Resource**

### Create a Location

Method : ``` POST ``` 

Endpoint : ```/api/location```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<!-- <details> -->
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- </details> -->


<!-- <details> --> 
<summary> Sample Request : </summary>

```json
{
  "address": {
    "building": "string",
    "city": "string",
    "contactPerson": "string",
    "countryIsocode": "string",
    "countryName": "string",
    "county": "string",
    "fax": "string",
    "level": "string",
    "phone": "string",
    "postcode": "string",
    "state": "string",
    "street": "string",
    "streetNumber": "string"
  },
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "id": "string",
  "locationRef": "string",
  "locationType": "STORE",
  "email": "string",
  "latitude": 0,
  "longitude": 0,
  "name": "string",
  "url": "string"
}   
```
<!-- </details> -->

<!-- <details> --> 
<summary>Response - 201 (Created)</summary>

``` json
{
  "address": {
    "building": "string",
    "city": "string",
    "contactPerson": "string",
    "countryIsocode": "string",
    "countryName": "string",
    "county": "string",
    "fax": "string",
    "level": "string",
    "phone": "string",
    "postcode": "string",
    "state": "string",
    "street": "string",
    "streetNumber": "string"
  },
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "id": "string",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "locationRef": "string",
  "locationType": "STORE",
  "email": "string",
  "latitude": 0,
  "longitude": 0,
  "name": "string",
  "url": "string"
}

```
<!-- </details> --> 


HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Create multiple Locations

Method : ``` POST ``` 

Endpoint : ```/api/locations```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- <details>  -->

<summary> Sample Request : </summary>

```json
[
  {
    "address": {
      "building": "string",
      "city": "string",
      "contactPerson": "string",
      "countryIsocode": "string",
      "countryName": "string",
      "county": "string",
      "fax": "string",
      "level": "string",
      "phone": "string",
      "postcode": "string",
      "state": "string",
      "street": "string",
      "streetNumber": "string"
    },
    "attributeGroups": {
      "additionalProp1": {
        "attribute_group": "string",
        "attributes": {
          "additionalProp1": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp2": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp3": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          }
        },
        "is_obsolete": true
      },
      "additionalProp2": {
        "attribute_group": "string",
        "attributes": {
          "additionalProp1": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp2": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp3": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          }
        },
        "is_obsolete": true
      },
      "additionalProp3": {
        "attribute_group": "string",
        "attributes": {
          "additionalProp1": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp2": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp3": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          }
        },
        "is_obsolete": true
      }
    },
    "id": "string",
    "locationRef": "string",
    "locationType": "STORE",
    "email": "string",
    "latitude": 0,
    "longitude": 0,
    "name": "string",
    "url": "string"
  }
]
```

<!-- </details> -->

<summary>Response - 201 (Created)</summary>

```json
{
  "address": {
    "building": "string",
    "city": "string",
    "contactPerson": "string",
    "countryIsocode": "string",
    "countryName": "string",
    "county": "string",
    "fax": "string",
    "level": "string",
    "phone": "string",
    "postcode": "string",
    "state": "string",
    "street": "string",
    "streetNumber": "string"
  },
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "id": "string",
  "locationRef": "string",
  "locationType": "STORE",
  "email": "string",
  "latitude": 0,
  "longitude": 0,
  "name": "string",
  "url": "string"
}
```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

<!--
## Validate an inventory Location

Method : ``` POST ``` 

Endpoint : ```​/api​/location​/validate```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


<summary> Sample Request : </summary>

```json
{
  "address": {
    "building": "string",
    "city": "string",
    "contactPerson": "string",
    "countryIsocode": "string",
    "countryName": "string",
    "county": "string",
    "fax": "string",
    "level": "string",
    "phone": "string",
    "postcode": "string",
    "state": "string",
    "street": "string",
    "streetNumber": "string"
  },
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "id": "string",
  "locationRef": "string",
  "locationType": "STORE",
  "email": "string",
  "latitude": 0,
  "longitude": 0,
  "name": "string",
  "url": "string"
}
```


<summary>Response - 200 (OK)</summary>

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

-->
<!--
## Update an inventory Location By Id

Update an inventory Location data set in the TWC system based on ID.

Endpoint: ```/api/location/id={id}"```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)


 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |



 Path Variable: 
 
 ```
 id - inventory Location Id
 
 ```
 

 <summary>Sample Request</summary>

```json

 {
  "address": {
    "building": "string",
    "city": "string",
    "contactPerson": "string",
    "countryIsocode": "string",
    "countryName": "string",
    "county": "string",
    "fax": "string",
    "level": "string",
    "phone": "string",
    "postcode": "string",
    "state": "string",
    "street": "string",
    "streetNumber": "string"
  },
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "locationType": "STORE",
  "email": "string",
  "latitude": 0,
  "longitude": 0,
  "name": "string",
  "url": "string"
}

```



<summary>Response - 200 (OK)</summary>

```json

{
  "address": {
    "building": "string",
    "city": "string",
    "contactPerson": "string",
    "countryIsocode": "string",
    "countryName": "string",
    "county": "string",
    "fax": "string",
    "level": "string",
    "phone": "string",
    "postcode": "string",
    "state": "string",
    "street": "string",
    "streetNumber": "string"
  },
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "id": "string",
  "locationRef": "string",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "locationType": "STORE",
  "email": "string",
  "latitude": 0,
  "longitude": 0,
  "name": "string",
  "url": "string"
} 

```


HTTP Status Code: 
``` json
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

### Update an inventory Location By Ref
Update an inventory Location data set in the The Wishlist system based on locationRef.

Endpoint: ```/api/location/locationRef={locationRef}"```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)


 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |



 Path Variable: 
 
 ```
 locationRef - inventory Location Ref
 
 ```
 

 <summary>Sample Request</summary>

```json
{
  "address": {
    "building": "string",
    "city": "string",
    "contactPerson": "string",
    "countryIsocode": "string",
    "countryName": "string",
    "county": "string",
    "fax": "string",
    "level": "string",
    "phone": "string",
    "postcode": "string",
    "state": "string",
    "street": "string",
    "streetNumber": "string"
  },
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "locationType": "STORE",
  "email": "string",
  "latitude": 0,
  "longitude": 0,
  "name": "string",
  "url": "string"
}
```

<summary>Response - 200 (OK)</summary>

```json
{
  "address": {
    "building": "string",
    "city": "string",
    "contactPerson": "string",
    "countryIsocode": "string",
    "countryName": "string",
    "county": "string",
    "fax": "string",
    "level": "string",
    "phone": "string",
    "postcode": "string",
    "state": "string",
    "street": "string",
    "streetNumber": "string"
  },
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "id": "string",
  "locationRef": "string",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "locationType": "STORE",
  "email": "string",
  "latitude": 0,
  "longitude": 0,
  "name": "string",
  "url": "string"
}
```

HTTP Status Code: 
``` json
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```
-->
### Get Location by id or Ref

Endpoint : ```/api/location```

Method : ``` GET ```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- <details> --> 
 <summary> Request Parameters : </summary>
 
``` json
"id": "{{Location Id}}",
"locationRef":"{{Location reference}}"
```
<!-- </details> --> 

<!-- <details> --> 
 <summary> Sample Response : </summary>
 
``` json
{
  "address": {
    "building": "string",
    "city": "string",
    "contactPerson": "string",
    "countryIsocode": "string",
    "countryName": "string",
    "county": "string",
    "fax": "string",
    "level": "string",
    "phone": "string",
    "postcode": "string",
    "state": "string",
    "street": "string",
    "streetNumber": "string"
  },
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "id": "string",
  "locationRef": "string",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "locationType": "STORE",
  "email": "string",
  "latitude": 0,
  "longitude": 0,
  "name": "string",
  "url": "string"
}

```
<!-- </details> --> 
<summary>Response - 200 (OK)</summary>

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

### Delete Location by Id or Ref

Endpoint: ```/api/location```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


<!-- <details> --> 
 <summary> Request Parameters : </summary>
 
``` json
"id": "{{Location Id}}",
"locationRef":"{{Location reference}}"
```
<!-- </details> --> 

<summary>Response - 204 (Deleted)</summary> 

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## **Stock Level Resource**

### Create a stock level

Method : ``` POST ``` 

Endpoint : ```/api/stocklevel```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- <details> --> 
<summary> Sample Request : </summary>

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "deleted": true,
  "excludedQuantity": 0,
  "futureStock": true,
  "id": "string",
  "locationId": "string",
  "productVariantId": "string",
  "reserved": 0,
  "status": "IN_STOCK",
  "stockDate": "2022-06-20T09:11:12.418Z",
  "stockOnHand": 0,
  "stockRef": "string"
}
```
<!-- </details> -->

<!-- <details> --> 
<summary>Response - 201 (Created)</summary>
 
``` json
{
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "deleted": true,
  "excludedQuantity": 0,
  "futureStock": true,
  "id": "string",
  "locationId": "string",
  "productVariantId": "string",
  "reserved": 0,
  "status": "IN_STOCK",
  "stockDate": "2022-06-27T06:37:59.881Z",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "stockOnHand": 0,
  "stockRef": "string"
}

```
<!-- </details> --> 

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

### Create multiple stock levels

Method : ``` POST ``` 

Endpoint : ```/api/stocklevels```

OAuth 2.0 Scopes : `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- <details> --> 
<summary> Sample Request : </summary>

```json
[
  {
    "attributeGroups": {
      "additionalProp1": {
        "attribute_group": "string",
        "attributes": {
          "additionalProp1": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp2": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp3": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          }
        },
        "is_obsolete": true
      },
      "additionalProp2": {
        "attribute_group": "string",
        "attributes": {
          "additionalProp1": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp2": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp3": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          }
        },
        "is_obsolete": true
      },
      "additionalProp3": {
        "attribute_group": "string",
        "attributes": {
          "additionalProp1": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp2": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp3": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          }
        },
        "is_obsolete": true
      }
    },
    "deleted": true,
    "excludedQuantity": 0,
    "futureStock": true,
    "id": "string",
    "locationId": "string",
    "productVariantId": "string",
    "reserved": 0,
    "status": "IN_STOCK",
    "stockDate": "2022-06-20T09:51:51.654Z",
    "stockOnHand": 0,
    "stockRef": "string"
  }
]
```
<!-- </details> -->

<!-- <details> --> 
<summary>Response - 201 (Created)</summary>
 
``` json
{
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "deleted": true,
  "excludedQuantity": 0,
  "futureStock": true,
  "id": "string",
  "locationId": "string",
  "productVariantId": "string",
  "reserved": 0,
  "status": "IN_STOCK",
  "stockDate": "2022-06-27T06:38:28.943Z",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "stockOnHand": 0,
  "stockRef": "string"
}

```
<!-- </details> --> 

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```
<!--
## Validate inventory level

Method: ``` POST ``` 

Endpoint: ```/api/stocklevel/validate```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


<summary> Sample Request : </summary>

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "deleted": true,
  "excludedQuantity": 0,
  "futureStock": true,
  "id": "string",
  "locationId": "string",
  "productVariantId": "string",
  "reserved": 0,
  "status": "IN_STOCK",
  "stockDate": "2022-06-20T09:54:12.586Z",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "stockOnHand": 0,
  "stockRef": "string"
}
```


<summary>Response - 200 (OK)</summary>

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```
-->
### Update a stock level

Method: ``` PUT ``` 

Endpoint: ```/api/stocklevel```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- <details> --> 
<summary> Sample Request : </summary>

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "deleted": true,
  "excludedQuantity": 0,
  "futureStock": true,
  "id": "string",
  "reserved": 0,
  "status": "IN_STOCK",
  "stockDate": "2022-06-20T09:51:02.857Z",
  "stockOnHand": 0,
  "stockRef": "string"
}
```
<!-- </details> -->

<!-- <details> --> 
<summary>Response - 200 (OK Updated)</summary>
 
``` json
{
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "deleted": true,
  "excludedQuantity": 0,
  "futureStock": true,
  "id": "string",
  "locationId": "string",
  "productVariantId": "string",
  "reserved": 0,
  "status": "IN_STOCK",
  "stockDate": "2022-06-27T06:39:30.214Z",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "stockOnHand": 0,
  "stockRef": "string"
}

```
<!-- </details> --> 

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```
<!--

## Update stock By stock Id

Method: ``` PUT ``` 

Endpoint: ```/api/stocklevel/id={id}```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable:

```
id - Stock Id
```

<summary> Sample Request : </summary>

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "deleted": true,
  "excludedQuantity": 0,
  "futureStock": true,
  "id": "string",
  "reserved": 0,
  "status": "IN_STOCK",
  "stockDate": "2022-06-20T09:51:02.857Z",
  "stockOnHand": 0,
  "stockRef": "string"
}
```

<summary>Response - 200 (OK Updated)</summary>
 
``` json
{
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "deleted": true,
  "excludedQuantity": 0,
  "futureStock": true,
  "id": "string",
  "locationId": "string",
  "productVariantId": "string",
  "reserved": 0,
  "status": "IN_STOCK",
  "stockDate": "2022-06-27T06:39:30.214Z",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "stockOnHand": 0,
  "stockRef": "string"
}

```


HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Update Stock By Ref

Method: ``` PUT ``` 

Endpoint: ```/api/stocklevel/ref={ref}```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Path Variable:

```
ref - Stock ref
```


<summary> Sample Request : </summary>

```json
{
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "deleted": true,
  "excludedQuantity": 0,
  "futureStock": true,
  "reserved": 0,
  "status": "IN_STOCK",
  "stockDate": "2022-07-27T10:53:23.113Z",
  "stockOnHand": 0
}
```

<summary>Response - 200 (OK Updated)</summary>
 
``` json
{
  "attributeGroups": {
    "additionalProp1": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp2": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    },
    "additionalProp3": {
      "attribute_group": "string",
      "attributes": {
        "additionalProp1": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp2": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        },
        "additionalProp3": {
          "attribute_value": "string",
          "value_type": "INTEGER"
        }
      },
      "is_obsolete": true
    }
  },
  "deleted": true,
  "excludedQuantity": 0,
  "futureStock": true,
  "id": "string",
  "locationId": "string",
  "locationRef": "string",
  "productVariantId": "string",
  "productVariantRef": "string",
  "reserved": 0,
  "status": "IN_STOCK",
  "stockDate": "2022-07-27T10:55:12.604Z",
  "createdTime": "2022-08-24T07:28:12.000+0000",
  "modifiedTime": "2022-08-24T07:30:52.051+0000",
  "stockOnHand": 0,
  "stockRef": "string"
}

```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```
-->

### Get stock level by stock id or stockRef

Endpoint: ```/api/stocklevel```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- <details> --> 
 <summary> Request Parameters : </summary>
 
``` json
"id": "{{inventory level Id}}",
"locationRef": "{{Inventory level reference}}"
```
<!-- </details> --> 

<summary>Response - 200 (OK)</summary>

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


### Get stock level for a product and location
This API gets stock level by locaiton and product identifiers.  It requires either location ID and productVariantId, OR locationRef and product VariantRef.

Endpoint: ```/api/product/stocklevels```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

Request Parameters: `locationId  : inventory location Id, locationRef : Inventory location reference,productId: unique Product Id,productRef: unique product reference`

<!-- <details> --> 
 <summary> Request Parameters : </summary>
 
``` json
"locationId"  : "{{inventory location Id}}",
"locationRef" : "{{Inventory location reference}}",
"productId": "{{unique Product Id}}",
"productRef": "{{unique product reference}}"
```
<!-- </details> --> 

<!-- <details> --> 
<summary>Response - 200 (OK)</summary>
 
``` json
[
  {
    "attributeGroups": {
      "additionalProp1": {
        "attribute_group": "string",
        "attributes": {
          "additionalProp1": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp2": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp3": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          }
        },
        "is_obsolete": true
      },
      "additionalProp2": {
        "attribute_group": "string",
        "attributes": {
          "additionalProp1": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp2": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp3": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          }
        },
        "is_obsolete": true
      },
      "additionalProp3": {
        "attribute_group": "string",
        "attributes": {
          "additionalProp1": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp2": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          },
          "additionalProp3": {
            "attribute_value": "string",
            "value_type": "INTEGER"
          }
        },
        "is_obsolete": true
      }
    },
    "deleted": true,
    "excludedQuantity": 0,
    "futureStock": true,
    "id": "string",
    "locationId": "string",
    "productVariantId": "string",
    "reserved": 0,
    "status": "IN_STOCK",
    "stockDate": "2022-06-27T06:40:40.732Z",
    "createdTime": "2022-08-24T07:28:12.000+0000",
    "modifiedTime": "2022-08-24T07:30:52.051+0000",
    "stockOnHand": 0,
    "stockRef": "string"
  }
]

```
<!-- </details> --> 

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

### Get Aggregate stock level for a product variant using variant ID or variant Ref
This API retrieves the aggregate of stock levels across all locations for a given variant.

Endpoint: ```/api/stocklevel/{id}```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

<!-- <details> --> 
 <summary> Request Parameters : </summary>
 
``` json
"id": "{{inventory level Id}}"
```
<!-- </details> --> 

<!-- <details> --> 
<summary>Response - 200 (OK)</summary>
 
``` json
{
  "productVariantId": "string",
  "stockLevels": [
    {
      "locationRef": "string",
      "locationid": "string",
      "stock": "string"
    }
  ],
  "totalStock": "string"
}

```
<!-- </details> --> 


HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


***
[Back to Top](#inventory-api)

[Back to Home](index.md#welcome-to-the-wishlist)
