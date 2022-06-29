
[Back to Index](index.md)
***

# **Inventory API**
An inventory item represents a physical good. It holds essential information about the physical good.

There is a 1:1 relationship between a product variant and an inventory level. Each product variant includes the ID of its related inventory level. You can use the product variant ID to query the InventoryLevel resource to retrieve the location and quantity for an inventory item.


Each **inventory level** belongs to one product variant and has one location. For every location where an inventory item can be stocked, there's an inventory level that represents the product variant quantities relating to that location.

An **inventory location** represents a geographical location where your stores, pop-up stores, headquarters, and warehouses exist. You can use the Location resource to track sales, manage inventory, and configure the tax rates to apply at checkout. 

### Index

***

- [**Inventory API**](#inventory-api)
    <!-- - [Index](#index) -->
  - [**Representations**](#representations)
  - [**REST Endpoints**](#rest-endpoints)
    - [Create an inventory Location](#create-an-inventory-location)
    - [Create multiple inventory Locations](#create-multiple-inventory-locations)
    - [Validate an inventory Location](#validate-an-inventory-location)
    - [Find Inventory Location by id and locationRef](#find-inventory-location-by-id-and-locationref)
    - [Delete Inventory Location](#delete-inventory-location)
    - [Create an inventory level](#create-an-inventory-level)
    - [Create Multiple inventory level](#create-multiple-inventory-level)
    - [Validate inventory level](#validate-inventory-level)
    - [Update an inventory level](#update-an-inventory-level)
    - [Find Inventory level by id and stockRef](#find-inventory-level-by-id-and-stockref)
    - [Find Inventory level for product and location](#find-inventory-level-for-product-and-location)
    - [Find Aggregated inventory level for a product variant](#find-aggregated-inventory-level-for-a-product-variant)
    

## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.


<!-- <details> -->
 <summary><font size="4">Location </font></summary>

```id``` - string -The unique ID of the location.It will auotmatically generate while creating the location.

```locationRef``` - string -The unique reference of the location.

```locationType``` - string -The location type  of the location. whether its STORE OR PICKUP_POINT

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

- ## **Location Resource**

## Create an inventory Location

Method : ``` POST ``` 

Endpoint : ```/api/location```

OAuth 2.0 Scopes : `Tenant authentication`

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
  "locationType": "STORE"
}   
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
  "locationType": "STORE"
}

```
<!-- </details> --> 


HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

## Create multiple inventory Locations

Method : ``` POST ``` 

Endpoint : ```/api/locations```

OAuth 2.0 Scopes : `Tenant authentication`

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
    "locationType": "STORE"
  }
]
```
<!-- </details> -->

<summary> Sample Response : </summary>
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
  "locationType": "STORE"
}
```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


## Validate an inventory Location

Method : ``` POST ``` 

Endpoint : ```​/api​/location​/validate```

OAuth 2.0 Scopes : `Tenant authentication`

<summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

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
  "locationType": "STORE"
}
```
<!-- </details> -->


HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

## Find Inventory Location by id and locationRef

Endpoint : ```/api/location```

Method : ``` GET ```

OAuth 2.0 Scopes : `Tenant authentication`

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
  "locationType": "STORE"
}

```
<!-- </details> --> 

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

## Delete Inventory Location

Endpoint: ```/api/location```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication`

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

HTTP Status Code: 

``` 
- 200 OK
- 201 Created
- 401 Unauthorized
- 403 Forbidden 
```

- ## **Stock Level Resource**

## Create an inventory level

Method : ``` POST ``` 

Endpoint : ```/api/stocklevel```

OAuth 2.0 Scopes : `Tenant authentication`

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
 <summary> Sample Response : </summary>
 
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
  "stockOnHand": 0,
  "stockRef": "string"
}

```
<!-- </details> --> 

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

## Create Multiple inventory level

Method : ``` POST ``` 

Endpoint : ```/api/stocklevels```

OAuth 2.0 Scopes : `Tenant authentication`

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
 <summary> Sample Response : </summary>
 
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
  "stockOnHand": 0,
  "stockRef": "string"
}

```
<!-- </details> --> 

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

## Validate inventory level

Method: ``` POST ``` 

Endpoint: ```/api/stocklevel/validate```

OAuth 2.0 Scopes: `Tenant authentication`

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
  "stockDate": "2022-06-20T09:54:12.586Z",
  "stockOnHand": 0,
  "stockRef": "string"
}
```
<!-- </details> -->



HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

## Update an inventory level

Method: ``` PUT ``` 

Endpoint: ```/api/stocklevel```

OAuth 2.0 Scopes: `Tenant authentication`

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
 <summary> Sample Response : </summary>
 
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
  "stockOnHand": 0,
  "stockRef": "string"
}

```
<!-- </details> --> 


HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


## Find Inventory level by id and stockRef

Endpoint: ```/api/stocklevel```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication`

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

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


## Find Inventory level for product and location

Endpoint: ```/api/product/stocklevels```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication`

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
 <summary> Sample Response : </summary>
 
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
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

## Find Aggregated inventory level for a product variant

Endpoint: ```/api/stocklevel/{id}```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication`

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
 <summary> Sample Response : </summary>
 
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
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```


***
[Back to Index](index.md)
