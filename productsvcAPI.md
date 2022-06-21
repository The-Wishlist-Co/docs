# **Product API**
The Product resource stores information about a product, its variants.

## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.

##  Product
***
Represents a product. 

<details>
 <summary>Expand for details</summary>
 
 `active` - boolean - To enable  a product.
 
 `additionalImageLink` - string - Image link.
 
 `attributeGroups` - [AttributeGroup](Common_Fields/attributeGroup.md) - The group of attibute values stored under as a object in group of atributeGroups.
 
 `availability` - string - Product Availablity and value should be one of the below values.
 - available
 - preorder
 - disabled 
 
 `availabilityDescription` - String- In detailed details of the product availability.
 
 `brandId` - string - Product brand Id.
 
 `brandName` - string - Product brand Name.
 
 `calculatedPrice` - number - Product calculated price.
 
 `color` - string  - Product Color.
 
 `condition` - String - Product Condition and it can be either of the below values.
 - New
 - Used
 - Refurbished 
 
 `cost`- number - Product's Cost
 
 `defaultVariant` - string - Default variant for the Product.
 
 `deleted` -  boolean
 
 `description` -  string
 
 `digitalProduct` -  
 
 `disabled` - 
 
 `expirationDate` - 
 
 `featured` - boolean
 
 `gtin` - 
 
 `gtinType` -
- GTIN8
- GTIN12
- GTIN13
- ITF
- MPN
- UPC
- JAN
- EAN
- GTIN14 
  
 `id` - string - 
 
 `imageLink` - string -
 
 `inventoryLevel` - integer - 
 
 `inventoryTracking` - string -
 - none
 - product
 - variant 
 
 `isbn` - string -
 
 `link` - string -
 
 `maxOrderQuantity` - 
 
 `minOrderQuantity` - 
 
 `mobileLink` - 
 
 `physicalSpecs	` - [PhysicalSpecifications](Common_Fields/physicalspecs.md) -
  
 `productRef` - string -
 
 `status` - 
 - APPROVED
 - UNAPPROVED
 - CHECK
 - VERIFICATION_PENDING 
 
 `title` - string  -
  
 `variance` - The array for vaiants.
  
 `variantOptions` - [VariantOptions](Common_Fields/variantoptions.md) - Array of variant Options.
 
 `variants` - [productVariants](Common_Fields/productvariant.md) - Array of variant Options.
 
 `variantsAvailable` - boolean -
 </details>
 
### Create a Product
Creates a new Product data set in the TWC system.

Endpoint: ```/api/v2/products```

Method: ``` POST ```

Method Name: `createProduct`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Payload</summary>
 
 {
  "active": true,
  "additionalImageLink": "string",
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
  "availability": "available",
  "availabilityDescription": "string",
  "brandId": "string",
  "brandName": "string",
  "calculatedPrice": 0,
  "color": "string",
  "condition": "New",
  "cost": 0,
  "defaultVariant": "string",
  "deleted": true,
  "description": "string",
  "digitalProduct": true,
  "disabled": true,
  "expirationDate": "2022-06-20T11:25:28.525Z",
  "featured": true,
  "gtin": "string",
  "gtinType": "GTIN8",
  "imageLink": "string",
  "inventoryLevel": 0,
  "inventoryTracking": "none",
  "isbn": "string",
  "link": "string",
  "maxOrderQuantity": 0,
  "minOrderQuantity": 0,
  "mobileLink": "string",
  "physicalSpecs": {
    "dimensionUnitCode": "string",
    "dimensionUnitName": "string",
    "maxDepth": 0,
    "maxHeight": 0,
    "maxWeight": 0,
    "maxWidth": 0,
    "minWeight": 0,
    "weightUnitCode": "string",
    "weightUnitName": "string"
  },
  "productRef": "string",
  "status": "APPROVED",
  "title": "string",
  "variance": [
    "string"
  ],
  "variantOptions": [
    {
      "optionId": "string",
      "optionName": "string"
    }
  ],
  "variantsAvailable": true
}
 
</details>

<details>
 <summary>Response</summary>
	
	{
  "active": true,
  "additionalImageLink": "string",
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
  "availability": "available",
  "availabilityDescription": "string",
  "brandId": "string",
  "brandName": "string",
  "calculatedPrice": 0,
  "color": "string",
  "condition": "New",
  "cost": 0,
  "defaultVariant": "string",
  "deleted": true,
  "description": "string",
  "digitalProduct": true,
  "disabled": true,
  "expirationDate": "2022-06-21T05:56:37.582Z",
  "featured": true,
  "gtin": "string",
  "gtinType": "GTIN8",
  "id": "string",
  "imageLink": "string",
  "inventoryLevel": 0,
  "inventoryTracking": "none",
  "isbn": "string",
  "link": "string",
  "maxOrderQuantity": 0,
  "minOrderQuantity": 0,
  "mobileLink": "string",
  "physicalSpecs": {
    "dimensionUnitCode": "string",
    "dimensionUnitName": "string",
    "maxDepth": 0,
    "maxHeight": 0,
    "maxWeight": 0,
    "maxWidth": 0,
    "minWeight": 0,
    "weightUnitCode": "string",
    "weightUnitName": "string"
  },
  "productRef": "string",
  "status": "APPROVED",
  "title": "string",
  "variance": [
    "string"
  ],
  "variantOptions": [
    {
      "optionId": "string",
      "optionName": "string"
    }
  ],
  "variants": [
    {
      "active": true,
      "additionalImageLink": "string",
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
      "availability": "available",
      "availabilityDescription": "string",
      "baseProductId": "string",
      "baseProductRef": "string",
      "brandId": "string",
      "brandName": "string",
      "calculatedPrice": 0,
      "color": "string",
      "condition": "New",
      "cost": 0,
      "defaultVariant": "string",
      "deleted": true,
      "description": "string",
      "digitalProduct": true,
      "disabled": true,
      "expirationDate": "2022-06-21T05:56:37.582Z",
      "featured": true,
      "gtin": "string",
      "gtinType": "GTIN8",
      "id": "string",
      "imageLink": "string",
      "inventoryLevel": 0,
      "inventoryTracking": "none",
      "isbn": "string",
      "link": "string",
      "maxOrderQuantity": 0,
      "minOrderQuantity": 0,
      "mobileLink": "string",
      "physicalSpecs": {
        "dimensionUnitCode": "string",
        "dimensionUnitName": "string",
        "maxDepth": 0,
        "maxHeight": 0,
        "maxWeight": 0,
        "maxWidth": 0,
        "minWeight": 0,
        "weightUnitCode": "string",
        "weightUnitName": "string"
      },
      "productRef": "string",
      "status": "APPROVED",
      "stock": {
        "stockLevels": [
          {
            "locationRef": "string",
            "locationid": "string",
            "stock": "string"
          }
        ],
        "totalStock": "string"
      },
      "title": "string",
      "variance": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "variantOptions": [
        {
          "optionDefaultImage": "string",
          "optionId": "string",
          "optionLabel": "string",
          "optionValue": "string",
          "optionsImageId": "string"
        }
      ]
    }
  ],
  "variantsAvailable": true
}
	
</details> 

HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Update a Product
Update Product data set in the TWC system.

Endpoint: ```/api/v2/products```

Method: ``` PUT ```

Method Name: `updateProduct`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Payload</summary>
 
 {
  "active": true,
  "additionalImageLink": "string",
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
  "availability": "available",
  "availabilityDescription": "string",
  "brandId": "string",
  "brandName": "string",
  "calculatedPrice": 0,
  "color": "string",
  "condition": "New",
  "cost": 0,
  "defaultVariant": "string",
  "deleted": true,
  "description": "string",
  "digitalProduct": true,
  "disabled": true,
  "expirationDate": "2022-06-20T14:22:00.119Z",
  "featured": true,
  "gtin": "string",
  "gtinType": "GTIN8",
  "id": "string",
  "imageLink": "string",
  "inventoryLevel": 0,
  "inventoryTracking": "none",
  "isbn": "string",
  "link": "string",
  "maxOrderQuantity": 0,
  "minOrderQuantity": 0,
  "mobileLink": "string",
  "physicalSpecs": {
    "dimensionUnitCode": "string",
    "dimensionUnitName": "string",
    "maxDepth": 0,
    "maxHeight": 0,
    "maxWeight": 0,
    "maxWidth": 0,
    "minWeight": 0,
    "weightUnitCode": "string",
    "weightUnitName": "string"
  },
  "productRef": "string",
  "status": "APPROVED",
  "title": "string",
  "variance": [
    "string"
  ],
  "variantOptions": [
    {
      "optionId": "string",
      "optionName": "string"
    }
  ],
  "variants": [
    {
      "active": true,
      "additionalImageLink": "string",
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
      "availability": "available",
      "availabilityDescription": "string",
      "baseProductId": "string",
      "baseProductRef": "string",
      "brandId": "string",
      "brandName": "string",
      "calculatedPrice": 0,
      "color": "string",
      "condition": "New",
      "cost": 0,
      "defaultVariant": "string",
      "deleted": true,
      "description": "string",
      "digitalProduct": true,
      "disabled": true,
      "expirationDate": "2022-06-20T14:22:00.119Z",
      "featured": true,
      "gtin": "string",
      "gtinType": "GTIN8",
      "id": "string",
      "imageLink": "string",
      "inventoryLevel": 0,
      "inventoryTracking": "none",
      "isbn": "string",
      "link": "string",
      "maxOrderQuantity": 0,
      "minOrderQuantity": 0,
      "mobileLink": "string",
      "physicalSpecs": {
        "dimensionUnitCode": "string",
        "dimensionUnitName": "string",
        "maxDepth": 0,
        "maxHeight": 0,
        "maxWeight": 0,
        "maxWidth": 0,
        "minWeight": 0,
        "weightUnitCode": "string",
        "weightUnitName": "string"
      },
      "productRef": "string",
      "status": "APPROVED",
      "stock": {
        "stockLevels": [
          {
            "locationRef": "string",
            "locationid": "string",
            "stock": "string"
          }
        ],
        "totalStock": "string"
      },
      "title": "string",
      "variance": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "variantOptions": [
        {
          "optionDefaultImage": "string",
          "optionId": "string",
          "optionLabel": "string",
          "optionValue": "string",
          "optionsImageId": "string"
        }
      ]
    }
  ],
  "variantsAvailable": true
}
 
</details>

<details>
 <summary>Response</summary>
	
	{
  "active": true,
  "additionalImageLink": "string",
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
  "availability": "available",
  "availabilityDescription": "string",
  "brandId": "string",
  "brandName": "string",
  "calculatedPrice": 0,
  "color": "string",
  "condition": "New",
  "cost": 0,
  "defaultVariant": "string",
  "deleted": true,
  "description": "string",
  "digitalProduct": true,
  "disabled": true,
  "expirationDate": "2022-06-21T05:57:31.432Z",
  "featured": true,
  "gtin": "string",
  "gtinType": "GTIN8",
  "id": "string",
  "imageLink": "string",
  "inventoryLevel": 0,
  "inventoryTracking": "none",
  "isbn": "string",
  "link": "string",
  "maxOrderQuantity": 0,
  "minOrderQuantity": 0,
  "mobileLink": "string",
  "physicalSpecs": {
    "dimensionUnitCode": "string",
    "dimensionUnitName": "string",
    "maxDepth": 0,
    "maxHeight": 0,
    "maxWeight": 0,
    "maxWidth": 0,
    "minWeight": 0,
    "weightUnitCode": "string",
    "weightUnitName": "string"
  },
  "productRef": "string",
  "status": "APPROVED",
  "title": "string",
  "variance": [
    "string"
  ],
  "variantOptions": [
    {
      "optionId": "string",
      "optionName": "string"
    }
  ],
  "variants": [
    {
      "active": true,
      "additionalImageLink": "string",
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
      "availability": "available",
      "availabilityDescription": "string",
      "baseProductId": "string",
      "baseProductRef": "string",
      "brandId": "string",
      "brandName": "string",
      "calculatedPrice": 0,
      "color": "string",
      "condition": "New",
      "cost": 0,
      "defaultVariant": "string",
      "deleted": true,
      "description": "string",
      "digitalProduct": true,
      "disabled": true,
      "expirationDate": "2022-06-21T05:57:31.432Z",
      "featured": true,
      "gtin": "string",
      "gtinType": "GTIN8",
      "id": "string",
      "imageLink": "string",
      "inventoryLevel": 0,
      "inventoryTracking": "none",
      "isbn": "string",
      "link": "string",
      "maxOrderQuantity": 0,
      "minOrderQuantity": 0,
      "mobileLink": "string",
      "physicalSpecs": {
        "dimensionUnitCode": "string",
        "dimensionUnitName": "string",
        "maxDepth": 0,
        "maxHeight": 0,
        "maxWeight": 0,
        "maxWidth": 0,
        "minWeight": 0,
        "weightUnitCode": "string",
        "weightUnitName": "string"
      },
      "productRef": "string",
      "status": "APPROVED",
      "stock": {
        "stockLevels": [
          {
            "locationRef": "string",
            "locationid": "string",
            "stock": "string"
          }
        ],
        "totalStock": "string"
      },
      "title": "string",
      "variance": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "variantOptions": [
        {
          "optionDefaultImage": "string",
          "optionId": "string",
          "optionLabel": "string",
          "optionValue": "string",
          "optionsImageId": "string"
        }
      ]
    }
  ],
  "variantsAvailable": true
}

	
</details> 

HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Look up Product by gtin/productRef
Returns a list of  products  from a specific Store while passing the gtin/productRef as a query params in the endpoint. The Tenant authentication maps to a Store.
If the products does not exist, this method returns a empty list.

Endpoint: ```/api/v2/products/lookup```

Method: ``` GET ``` 

Method Name: `lookupProduct`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Query Parameters</summary>
 
 - {gtin}
 - {productRef}
 
</details>

<details>
 <summary>Response</summary>
 
 {
  "products": [
    {
      "active": true,
      "additionalImageLink": "string",
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
      "availability": "available",
      "availabilityDescription": "string",
      "brandId": "string",
      "brandName": "string",
      "calculatedPrice": 0,
      "color": "string",
      "condition": "New",
      "cost": 0,
      "defaultVariant": "string",
      "deleted": true,
      "description": "string",
      "digitalProduct": true,
      "disabled": true,
      "expirationDate": "2022-06-21T05:58:10.365Z",
      "featured": true,
      "gtin": "string",
      "gtinType": "GTIN8",
      "id": "string",
      "imageLink": "string",
      "inventoryLevel": 0,
      "inventoryTracking": "none",
      "isbn": "string",
      "link": "string",
      "maxOrderQuantity": 0,
      "minOrderQuantity": 0,
      "mobileLink": "string",
      "physicalSpecs": {
        "dimensionUnitCode": "string",
        "dimensionUnitName": "string",
        "maxDepth": 0,
        "maxHeight": 0,
        "maxWeight": 0,
        "maxWidth": 0,
        "minWeight": 0,
        "weightUnitCode": "string",
        "weightUnitName": "string"
      },
      "productRef": "string",
      "status": "APPROVED",
      "title": "string",
      "variance": [
        "string"
      ],
      "variantOptions": [
        {
          "optionId": "string",
          "optionName": "string"
        }
      ],
      "variants": [
        {
          "active": true,
          "additionalImageLink": "string",
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
          "availability": "available",
          "availabilityDescription": "string",
          "baseProductId": "string",
          "baseProductRef": "string",
          "brandId": "string",
          "brandName": "string",
          "calculatedPrice": 0,
          "color": "string",
          "condition": "New",
          "cost": 0,
          "defaultVariant": "string",
          "deleted": true,
          "description": "string",
          "digitalProduct": true,
          "disabled": true,
          "expirationDate": "2022-06-21T05:58:10.365Z",
          "featured": true,
          "gtin": "string",
          "gtinType": "GTIN8",
          "id": "string",
          "imageLink": "string",
          "inventoryLevel": 0,
          "inventoryTracking": "none",
          "isbn": "string",
          "link": "string",
          "maxOrderQuantity": 0,
          "minOrderQuantity": 0,
          "mobileLink": "string",
          "physicalSpecs": {
            "dimensionUnitCode": "string",
            "dimensionUnitName": "string",
            "maxDepth": 0,
            "maxHeight": 0,
            "maxWeight": 0,
            "maxWidth": 0,
            "minWeight": 0,
            "weightUnitCode": "string",
            "weightUnitName": "string"
          },
          "productRef": "string",
          "status": "APPROVED",
          "stock": {
            "stockLevels": [
              {
                "locationRef": "string",
                "locationid": "string",
                "stock": "string"
              }
            ],
            "totalStock": "string"
          },
          "title": "string",
          "variance": {
            "additionalProp1": "string",
            "additionalProp2": "string",
            "additionalProp3": "string"
          },
          "variantOptions": [
            {
              "optionDefaultImage": "string",
              "optionId": "string",
              "optionLabel": "string",
              "optionValue": "string",
              "optionsImageId": "string"
            }
          ]
        }
      ],
      "variantsAvailable": true
    }
  ],
  "variants": [
    {
      "active": true,
      "additionalImageLink": "string",
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
      "availability": "available",
      "availabilityDescription": "string",
      "baseProductId": "string",
      "baseProductRef": "string",
      "brandId": "string",
      "brandName": "string",
      "calculatedPrice": 0,
      "color": "string",
      "condition": "New",
      "cost": 0,
      "defaultVariant": "string",
      "deleted": true,
      "description": "string",
      "digitalProduct": true,
      "disabled": true,
      "expirationDate": "2022-06-21T05:58:10.365Z",
      "featured": true,
      "gtin": "string",
      "gtinType": "GTIN8",
      "id": "string",
      "imageLink": "string",
      "inventoryLevel": 0,
      "inventoryTracking": "none",
      "isbn": "string",
      "link": "string",
      "maxOrderQuantity": 0,
      "minOrderQuantity": 0,
      "mobileLink": "string",
      "physicalSpecs": {
        "dimensionUnitCode": "string",
        "dimensionUnitName": "string",
        "maxDepth": 0,
        "maxHeight": 0,
        "maxWeight": 0,
        "maxWidth": 0,
        "minWeight": 0,
        "weightUnitCode": "string",
        "weightUnitName": "string"
      },
      "productRef": "string",
      "status": "APPROVED",
      "stock": {
        "stockLevels": [
          {
            "locationRef": "string",
            "locationid": "string",
            "stock": "string"
          }
        ],
        "totalStock": "string"
      },
      "title": "string",
      "variance": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "variantOptions": [
        {
          "optionDefaultImage": "string",
          "optionId": "string",
          "optionLabel": "string",
          "optionValue": "string",
          "optionsImageId": "string"
        }
      ]
    }
  ]
}

</details> 
HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Validate Request

Validates the Prodcut Request 

Endpoint: ```/api/v2/products/validate```

Method: ``` POST ```

Method Name: `validateRequest`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Payload</summary>

{
  "active": true,
  "additionalImageLink": "string",
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
  "availability": "available",
  "availabilityDescription": "string",
  "brandId": "string",
  "brandName": "string",
  "calculatedPrice": 0,
  "color": "string",
  "condition": "New",
  "cost": 0,
  "defaultVariant": "string",
  "deleted": true,
  "description": "string",
  "digitalProduct": true,
  "disabled": true,
  "expirationDate": "2022-06-20T14:27:52.893Z",
  "featured": true,
  "gtin": "string",
  "gtinType": "GTIN8",
  "id": "string",
  "imageLink": "string",
  "inventoryLevel": 0,
  "inventoryTracking": "none",
  "isbn": "string",
  "link": "string",
  "maxOrderQuantity": 0,
  "minOrderQuantity": 0,
  "mobileLink": "string",
  "physicalSpecs": {
    "dimensionUnitCode": "string",
    "dimensionUnitName": "string",
    "maxDepth": 0,
    "maxHeight": 0,
    "maxWeight": 0,
    "maxWidth": 0,
    "minWeight": 0,
    "weightUnitCode": "string",
    "weightUnitName": "string"
  },
  "productRef": "string",
  "status": "APPROVED",
  "title": "string",
  "variance": [
    "string"
  ],
  "variantOptions": [
    {
      "optionId": "string",
      "optionName": "string"
    }
  ],
  "variants": [
    {
      "active": true,
      "additionalImageLink": "string",
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
      "availability": "available",
      "availabilityDescription": "string",
      "baseProductId": "string",
      "baseProductRef": "string",
      "brandId": "string",
      "brandName": "string",
      "calculatedPrice": 0,
      "color": "string",
      "condition": "New",
      "cost": 0,
      "defaultVariant": "string",
      "deleted": true,
      "description": "string",
      "digitalProduct": true,
      "disabled": true,
      "expirationDate": "2022-06-20T14:27:52.893Z",
      "featured": true,
      "gtin": "string",
      "gtinType": "GTIN8",
      "id": "string",
      "imageLink": "string",
      "inventoryLevel": 0,
      "inventoryTracking": "none",
      "isbn": "string",
      "link": "string",
      "maxOrderQuantity": 0,
      "minOrderQuantity": 0,
      "mobileLink": "string",
      "physicalSpecs": {
        "dimensionUnitCode": "string",
        "dimensionUnitName": "string",
        "maxDepth": 0,
        "maxHeight": 0,
        "maxWeight": 0,
        "maxWidth": 0,
        "minWeight": 0,
        "weightUnitCode": "string",
        "weightUnitName": "string"
      },
      "productRef": "string",
      "status": "APPROVED",
      "stock": {
        "stockLevels": [
          {
            "locationRef": "string",
            "locationid": "string",
            "stock": "string"
          }
        ],
        "totalStock": "string"
      },
      "title": "string",
      "variance": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "variantOptions": [
        {
          "optionDefaultImage": "string",
          "optionId": "string",
          "optionLabel": "string",
          "optionValue": "string",
          "optionsImageId": "string"
        }
      ]
    }
  ],
  "variantsAvailable": true
}

</details>

<details>
 <summary>Response</summary>
 OK
</details> 
HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Validate Product
Validates the product based on ID and ID will be passed as path variable.

Endpoint: ```/api/v2/products/validate/{id}```

Method: ``` GET ```

Method Name: `validateProduct`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Path Variable</summary>
 - {id}
</details>

<details>
 <summary>Response</summary>
 {
  "product": {
    "active": true,
    "additionalImageLink": "string",
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
    "availability": "available",
    "availabilityDescription": "string",
    "brandId": "string",
    "brandName": "string",
    "calculatedPrice": 0,
    "color": "string",
    "condition": "New",
    "cost": 0,
    "defaultVariant": "string",
    "deleted": true,
    "description": "string",
    "digitalProduct": true,
    "disabled": true,
    "expirationDate": "2022-06-21T06:00:13.842Z",
    "featured": true,
    "gtin": "string",
    "gtinType": "GTIN8",
    "id": "string",
    "imageLink": "string",
    "inventoryLevel": 0,
    "inventoryTracking": "none",
    "isbn": "string",
    "link": "string",
    "maxOrderQuantity": 0,
    "minOrderQuantity": 0,
    "mobileLink": "string",
    "physicalSpecs": {
      "dimensionUnitCode": "string",
      "dimensionUnitName": "string",
      "maxDepth": 0,
      "maxHeight": 0,
      "maxWeight": 0,
      "maxWidth": 0,
      "minWeight": 0,
      "weightUnitCode": "string",
      "weightUnitName": "string"
    },
    "productRef": "string",
    "status": "APPROVED",
    "title": "string",
    "variance": [
      "string"
    ],
    "variantOptions": [
      {
        "optionId": "string",
        "optionName": "string"
      }
    ],
    "variants": [
      {
        "active": true,
        "additionalImageLink": "string",
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
        "availability": "available",
        "availabilityDescription": "string",
        "baseProductId": "string",
        "baseProductRef": "string",
        "brandId": "string",
        "brandName": "string",
        "calculatedPrice": 0,
        "color": "string",
        "condition": "New",
        "cost": 0,
        "defaultVariant": "string",
        "deleted": true,
        "description": "string",
        "digitalProduct": true,
        "disabled": true,
        "expirationDate": "2022-06-21T06:00:13.842Z",
        "featured": true,
        "gtin": "string",
        "gtinType": "GTIN8",
        "id": "string",
        "imageLink": "string",
        "inventoryLevel": 0,
        "inventoryTracking": "none",
        "isbn": "string",
        "link": "string",
        "maxOrderQuantity": 0,
        "minOrderQuantity": 0,
        "mobileLink": "string",
        "physicalSpecs": {
          "dimensionUnitCode": "string",
          "dimensionUnitName": "string",
          "maxDepth": 0,
          "maxHeight": 0,
          "maxWeight": 0,
          "maxWidth": 0,
          "minWeight": 0,
          "weightUnitCode": "string",
          "weightUnitName": "string"
        },
        "productRef": "string",
        "status": "APPROVED",
        "stock": {
          "stockLevels": [
            {
              "locationRef": "string",
              "locationid": "string",
              "stock": "string"
            }
          ],
          "totalStock": "string"
        },
        "title": "string",
        "variance": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        },
        "variantOptions": [
          {
            "optionDefaultImage": "string",
            "optionId": "string",
            "optionLabel": "string",
            "optionValue": "string",
            "optionsImageId": "string"
          }
        ]
      }
    ],
    "variantsAvailable": true
  },
  "variant": true,
  "variantProduct": {
    "active": true,
    "additionalImageLink": "string",
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
    "availability": "available",
    "availabilityDescription": "string",
    "baseProductId": "string",
    "baseProductRef": "string",
    "brandId": "string",
    "brandName": "string",
    "calculatedPrice": 0,
    "color": "string",
    "condition": "New",
    "cost": 0,
    "defaultVariant": "string",
    "deleted": true,
    "description": "string",
    "digitalProduct": true,
    "disabled": true,
    "expirationDate": "2022-06-21T06:00:13.842Z",
    "featured": true,
    "gtin": "string",
    "gtinType": "GTIN8",
    "id": "string",
    "imageLink": "string",
    "inventoryLevel": 0,
    "inventoryTracking": "none",
    "isbn": "string",
    "link": "string",
    "maxOrderQuantity": 0,
    "minOrderQuantity": 0,
    "mobileLink": "string",
    "physicalSpecs": {
      "dimensionUnitCode": "string",
      "dimensionUnitName": "string",
      "maxDepth": 0,
      "maxHeight": 0,
      "maxWeight": 0,
      "maxWidth": 0,
      "minWeight": 0,
      "weightUnitCode": "string",
      "weightUnitName": "string"
    },
    "productRef": "string",
    "status": "APPROVED",
    "stock": {
      "stockLevels": [
        {
          "locationRef": "string",
          "locationid": "string",
          "stock": "string"
        }
      ],
      "totalStock": "string"
    },
    "title": "string",
    "variance": {
      "additionalProp1": "string",
      "additionalProp2": "string",
      "additionalProp3": "string"
    },
    "variantOptions": [
      {
        "optionDefaultImage": "string",
        "optionId": "string",
        "optionLabel": "string",
        "optionValue": "string",
        "optionsImageId": "string"
      }
    ]
  }
}
</details> 
HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Validate Product by Ref
Validates the product based on ref and ref will be passed as path variable.

Endpoint: ```/api/v2/products/validateRef/{ref}```

Method: ``` GET ```

Method Name: `validateProductRef`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Path Variable</summary>
 - {ref}
</details>

<details>
 <summary>Response</summary>
 {
  "product": {
    "active": true,
    "additionalImageLink": "string",
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
    "availability": "available",
    "availabilityDescription": "string",
    "brandId": "string",
    "brandName": "string",
    "calculatedPrice": 0,
    "color": "string",
    "condition": "New",
    "cost": 0,
    "defaultVariant": "string",
    "deleted": true,
    "description": "string",
    "digitalProduct": true,
    "disabled": true,
    "expirationDate": "2022-06-21T06:00:41.481Z",
    "featured": true,
    "gtin": "string",
    "gtinType": "GTIN8",
    "id": "string",
    "imageLink": "string",
    "inventoryLevel": 0,
    "inventoryTracking": "none",
    "isbn": "string",
    "link": "string",
    "maxOrderQuantity": 0,
    "minOrderQuantity": 0,
    "mobileLink": "string",
    "physicalSpecs": {
      "dimensionUnitCode": "string",
      "dimensionUnitName": "string",
      "maxDepth": 0,
      "maxHeight": 0,
      "maxWeight": 0,
      "maxWidth": 0,
      "minWeight": 0,
      "weightUnitCode": "string",
      "weightUnitName": "string"
    },
    "productRef": "string",
    "status": "APPROVED",
    "title": "string",
    "variance": [
      "string"
    ],
    "variantOptions": [
      {
        "optionId": "string",
        "optionName": "string"
      }
    ],
    "variants": [
      {
        "active": true,
        "additionalImageLink": "string",
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
        "availability": "available",
        "availabilityDescription": "string",
        "baseProductId": "string",
        "baseProductRef": "string",
        "brandId": "string",
        "brandName": "string",
        "calculatedPrice": 0,
        "color": "string",
        "condition": "New",
        "cost": 0,
        "defaultVariant": "string",
        "deleted": true,
        "description": "string",
        "digitalProduct": true,
        "disabled": true,
        "expirationDate": "2022-06-21T06:00:41.481Z",
        "featured": true,
        "gtin": "string",
        "gtinType": "GTIN8",
        "id": "string",
        "imageLink": "string",
        "inventoryLevel": 0,
        "inventoryTracking": "none",
        "isbn": "string",
        "link": "string",
        "maxOrderQuantity": 0,
        "minOrderQuantity": 0,
        "mobileLink": "string",
        "physicalSpecs": {
          "dimensionUnitCode": "string",
          "dimensionUnitName": "string",
          "maxDepth": 0,
          "maxHeight": 0,
          "maxWeight": 0,
          "maxWidth": 0,
          "minWeight": 0,
          "weightUnitCode": "string",
          "weightUnitName": "string"
        },
        "productRef": "string",
        "status": "APPROVED",
        "stock": {
          "stockLevels": [
            {
              "locationRef": "string",
              "locationid": "string",
              "stock": "string"
            }
          ],
          "totalStock": "string"
        },
        "title": "string",
        "variance": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        },
        "variantOptions": [
          {
            "optionDefaultImage": "string",
            "optionId": "string",
            "optionLabel": "string",
            "optionValue": "string",
            "optionsImageId": "string"
          }
        ]
      }
    ],
    "variantsAvailable": true
  },
  "variant": true,
  "variantProduct": {
    "active": true,
    "additionalImageLink": "string",
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
    "availability": "available",
    "availabilityDescription": "string",
    "baseProductId": "string",
    "baseProductRef": "string",
    "brandId": "string",
    "brandName": "string",
    "calculatedPrice": 0,
    "color": "string",
    "condition": "New",
    "cost": 0,
    "defaultVariant": "string",
    "deleted": true,
    "description": "string",
    "digitalProduct": true,
    "disabled": true,
    "expirationDate": "2022-06-21T06:00:41.481Z",
    "featured": true,
    "gtin": "string",
    "gtinType": "GTIN8",
    "id": "string",
    "imageLink": "string",
    "inventoryLevel": 0,
    "inventoryTracking": "none",
    "isbn": "string",
    "link": "string",
    "maxOrderQuantity": 0,
    "minOrderQuantity": 0,
    "mobileLink": "string",
    "physicalSpecs": {
      "dimensionUnitCode": "string",
      "dimensionUnitName": "string",
      "maxDepth": 0,
      "maxHeight": 0,
      "maxWeight": 0,
      "maxWidth": 0,
      "minWeight": 0,
      "weightUnitCode": "string",
      "weightUnitName": "string"
    },
    "productRef": "string",
    "status": "APPROVED",
    "stock": {
      "stockLevels": [
        {
          "locationRef": "string",
          "locationid": "string",
          "stock": "string"
        }
      ],
      "totalStock": "string"
    },
    "title": "string",
    "variance": {
      "additionalProp1": "string",
      "additionalProp2": "string",
      "additionalProp3": "string"
    },
    "variantOptions": [
      {
        "optionDefaultImage": "string",
        "optionId": "string",
        "optionLabel": "string",
        "optionValue": "string",
        "optionsImageId": "string"
      }
    ]
  }
}
</details> 
HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Find Product by ID

Returns a Product by its ID from a specific Store while passing the respective ID as a path variable in the endpoint. The Tenant authentication maps to a Store.
If the Product does not exist, this method returns a Blank.

Endpoint: ```/api/v2/products/{id}```

Method: ``` GET ```

Method Name: `getProduct`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Path Variable</summary>
 - {id}
 
</details>

<details>
 <summary>Response</summary>

{
  "active": true,
  "additionalImageLink": "string",
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
  "availability": "available",
  "availabilityDescription": "string",
  "brandId": "string",
  "brandName": "string",
  "calculatedPrice": 0,
  "color": "string",
  "condition": "New",
  "cost": 0,
  "defaultVariant": "string",
  "deleted": true,
  "description": "string",
  "digitalProduct": true,
  "disabled": true,
  "expirationDate": "2022-06-21T06:02:15.257Z",
  "featured": true,
  "gtin": "string",
  "gtinType": "GTIN8",
  "id": "string",
  "imageLink": "string",
  "inventoryLevel": 0,
  "inventoryTracking": "none",
  "isbn": "string",
  "link": "string",
  "maxOrderQuantity": 0,
  "minOrderQuantity": 0,
  "mobileLink": "string",
  "physicalSpecs": {
    "dimensionUnitCode": "string",
    "dimensionUnitName": "string",
    "maxDepth": 0,
    "maxHeight": 0,
    "maxWeight": 0,
    "maxWidth": 0,
    "minWeight": 0,
    "weightUnitCode": "string",
    "weightUnitName": "string"
  },
  "productRef": "string",
  "status": "APPROVED",
  "title": "string",
  "variance": [
    "string"
  ],
  "variantOptions": [
    {
      "optionId": "string",
      "optionName": "string"
    }
  ],
  "variants": [
    {
      "active": true,
      "additionalImageLink": "string",
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
      "availability": "available",
      "availabilityDescription": "string",
      "baseProductId": "string",
      "baseProductRef": "string",
      "brandId": "string",
      "brandName": "string",
      "calculatedPrice": 0,
      "color": "string",
      "condition": "New",
      "cost": 0,
      "defaultVariant": "string",
      "deleted": true,
      "description": "string",
      "digitalProduct": true,
      "disabled": true,
      "expirationDate": "2022-06-21T06:02:15.257Z",
      "featured": true,
      "gtin": "string",
      "gtinType": "GTIN8",
      "id": "string",
      "imageLink": "string",
      "inventoryLevel": 0,
      "inventoryTracking": "none",
      "isbn": "string",
      "link": "string",
      "maxOrderQuantity": 0,
      "minOrderQuantity": 0,
      "mobileLink": "string",
      "physicalSpecs": {
        "dimensionUnitCode": "string",
        "dimensionUnitName": "string",
        "maxDepth": 0,
        "maxHeight": 0,
        "maxWeight": 0,
        "maxWidth": 0,
        "minWeight": 0,
        "weightUnitCode": "string",
        "weightUnitName": "string"
      },
      "productRef": "string",
      "status": "APPROVED",
      "stock": {
        "stockLevels": [
          {
            "locationRef": "string",
            "locationid": "string",
            "stock": "string"
          }
        ],
        "totalStock": "string"
      },
      "title": "string",
      "variance": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "variantOptions": [
        {
          "optionDefaultImage": "string",
          "optionId": "string",
          "optionLabel": "string",
          "optionValue": "string",
          "optionsImageId": "string"
        }
      ]
    }
  ],
  "variantsAvailable": true
}

</details> 
HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Delete Product by ID
Deleting a Product marks the Product as deleted and produces the HTTP response confirming the action.
If the Product does not exist, this method returns a empty response.

Endpoint: ```/api/v2/products/{id}```

Method: ``` DELETE ```

Method Name: `deleteProduct`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Path Variable</summary>
	- {id}
</details>

<details>
 <summary>Response</summary>
 OK
</details> 
HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Find Product by Ref

Returns a Product by its Ref from a specific Store while passing the respective Ref as a path param in the endpoint. The Tenant authentication maps to a Store.
If the Product does not exist, this method returns a blank response.

Endpoint: ```/api/v2/products/{productRef}/byref```

Method: ``` GET ``` 

Method Name: `getProductByRef`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Path Variable</summary>
- {productRef}
</details>

<details>
 <summary>Response</summary>
 
 {
  "active": true,
  "additionalImageLink": "string",
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
  "availability": "available",
  "availabilityDescription": "string",
  "brandId": "string",
  "brandName": "string",
  "calculatedPrice": 0,
  "color": "string",
  "condition": "New",
  "cost": 0,
  "defaultVariant": "string",
  "deleted": true,
  "description": "string",
  "digitalProduct": true,
  "disabled": true,
  "expirationDate": "2022-06-21T06:05:12.697Z",
  "featured": true,
  "gtin": "string",
  "gtinType": "GTIN8",
  "id": "string",
  "imageLink": "string",
  "inventoryLevel": 0,
  "inventoryTracking": "none",
  "isbn": "string",
  "link": "string",
  "maxOrderQuantity": 0,
  "minOrderQuantity": 0,
  "mobileLink": "string",
  "physicalSpecs": {
    "dimensionUnitCode": "string",
    "dimensionUnitName": "string",
    "maxDepth": 0,
    "maxHeight": 0,
    "maxWeight": 0,
    "maxWidth": 0,
    "minWeight": 0,
    "weightUnitCode": "string",
    "weightUnitName": "string"
  },
  "productRef": "string",
  "status": "APPROVED",
  "title": "string",
  "variance": [
    "string"
  ],
  "variantOptions": [
    {
      "optionId": "string",
      "optionName": "string"
    }
  ],
  "variants": [
    {
      "active": true,
      "additionalImageLink": "string",
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
      "availability": "available",
      "availabilityDescription": "string",
      "baseProductId": "string",
      "baseProductRef": "string",
      "brandId": "string",
      "brandName": "string",
      "calculatedPrice": 0,
      "color": "string",
      "condition": "New",
      "cost": 0,
      "defaultVariant": "string",
      "deleted": true,
      "description": "string",
      "digitalProduct": true,
      "disabled": true,
      "expirationDate": "2022-06-21T06:05:12.697Z",
      "featured": true,
      "gtin": "string",
      "gtinType": "GTIN8",
      "id": "string",
      "imageLink": "string",
      "inventoryLevel": 0,
      "inventoryTracking": "none",
      "isbn": "string",
      "link": "string",
      "maxOrderQuantity": 0,
      "minOrderQuantity": 0,
      "mobileLink": "string",
      "physicalSpecs": {
        "dimensionUnitCode": "string",
        "dimensionUnitName": "string",
        "maxDepth": 0,
        "maxHeight": 0,
        "maxWeight": 0,
        "maxWidth": 0,
        "minWeight": 0,
        "weightUnitCode": "string",
        "weightUnitName": "string"
      },
      "productRef": "string",
      "status": "APPROVED",
      "stock": {
        "stockLevels": [
          {
            "locationRef": "string",
            "locationid": "string",
            "stock": "string"
          }
        ],
        "totalStock": "string"
      },
      "title": "string",
      "variance": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "variantOptions": [
        {
          "optionDefaultImage": "string",
          "optionId": "string",
          "optionLabel": "string",
          "optionValue": "string",
          "optionsImageId": "string"
        }
      ]
    }
  ],
  "variantsAvailable": true
}
 
</details> 
HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Delete Product by Ref

Deleting a Product by ref marks the Product as deleted and produces the HTTP response confirming the action.
If the product does not exist, this method returns a empty response.

Endpoint: ```/api/v2/products/{productRef}/byref```

Method: ``` DELETE ``` 

Method Name: `deleteProductByExternalRef`

OAuth 2.0 Scopes: `Tenant authentication`

<details>

 <summary>Path Variable</summary>
	- {productRef}
	
</details>

<details>
 <summary>Response</summary>
 OK
</details> 

HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Upload Products
Creates an array of new products in the TWC system.

Endpoint: ```/api/v2/uploadProducts```

Method: ``` POST ```

Method Name: `/api/v2/uploadProducts`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Payload</summary>
  
  [
  {
    "active": true,
    "additionalImageLink": "string",
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
    "availability": "available",
    "availabilityDescription": "string",
    "brandId": "string",
    "brandName": "string",
    "calculatedPrice": 0,
    "color": "string",
    "condition": "New",
    "cost": 0,
    "defaultVariant": "string",
    "deleted": true,
    "description": "string",
    "digitalProduct": true,
    "disabled": true,
    "expirationDate": "2022-06-21T04:59:19.592Z",
    "featured": true,
    "gtin": "string",
    "gtinType": "GTIN8",
    "id": "string",
    "imageLink": "string",
    "inventoryLevel": 0,
    "inventoryTracking": "none",
    "isbn": "string",
    "link": "string",
    "maxOrderQuantity": 0,
    "minOrderQuantity": 0,
    "mobileLink": "string",
    "physicalSpecs": {
      "dimensionUnitCode": "string",
      "dimensionUnitName": "string",
      "maxDepth": 0,
      "maxHeight": 0,
      "maxWeight": 0,
      "maxWidth": 0,
      "minWeight": 0,
      "weightUnitCode": "string",
      "weightUnitName": "string"
    },
    "productRef": "string",
    "status": "APPROVED",
    "title": "string",
    "variance": [
      "string"
    ],
    "variantOptions": [
      {
        "optionId": "string",
        "optionName": "string"
      }
    ],
    "variants": [
      {
        "active": true,
        "additionalImageLink": "string",
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
        "availability": "available",
        "availabilityDescription": "string",
        "baseProductId": "string",
        "baseProductRef": "string",
        "brandId": "string",
        "brandName": "string",
        "calculatedPrice": 0,
        "color": "string",
        "condition": "New",
        "cost": 0,
        "defaultVariant": "string",
        "deleted": true,
        "description": "string",
        "digitalProduct": true,
        "disabled": true,
        "expirationDate": "2022-06-21T04:59:19.592Z",
        "featured": true,
        "gtin": "string",
        "gtinType": "GTIN8",
        "id": "string",
        "imageLink": "string",
        "inventoryLevel": 0,
        "inventoryTracking": "none",
        "isbn": "string",
        "link": "string",
        "maxOrderQuantity": 0,
        "minOrderQuantity": 0,
        "mobileLink": "string",
        "physicalSpecs": {
          "dimensionUnitCode": "string",
          "dimensionUnitName": "string",
          "maxDepth": 0,
          "maxHeight": 0,
          "maxWeight": 0,
          "maxWidth": 0,
          "minWeight": 0,
          "weightUnitCode": "string",
          "weightUnitName": "string"
        },
        "productRef": "string",
        "status": "APPROVED",
        "stock": {
          "stockLevels": [
            {
              "locationRef": "string",
              "locationid": "string",
              "stock": "string"
            }
          ],
          "totalStock": "string"
        },
        "title": "string",
        "variance": {
          "additionalProp1": "string",
          "additionalProp2": "string",
          "additionalProp3": "string"
        },
        "variantOptions": [
          {
            "optionDefaultImage": "string",
            "optionId": "string",
            "optionLabel": "string",
            "optionValue": "string",
            "optionsImageId": "string"
          }
        ]
      }
    ],
    "variantsAvailable": true
  }
]
  
</details>

<details>
 <summary>Response</summary>
 OK
</details> 

HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`



##  Product Variant
***
Represents a product Variant.

<details>
 <summary>Expand for details</summary>
  `active` - boolean - To enable  a product variant.
 
 `additionalImageLink` - string - Image link.
 
 `attributeGroups` - [AttributeGroup](Common_Fields/attributeGroup.md) - The group of attibute values stored under as a object in group of atributeGroups.
 
 `availability` - string - Product Availablity and value should be one of the below values.
 - available
 - preorder
 - disabled 
 
 `availabilityDescription` - String- In detailed details of the product availability.
 
 `baseProductId` - string - Base Product Id.
 
 `baseProductRef` - string - Base Product Name.
 
 `brandId` - string - Product brand Id.
 
 `brandName` - string - Product brand Name.
 
 `calculatedPrice` - number - Product calculated price.
 
 `color` - string  - Product Color.
 
 `condition` - String - Product Condition and it can be either of the below values.
 - New
 - Used
 - Refurbished 
 
 `cost`- number - Product's Cost
 
 `defaultVariant` - string - Default variant for the Product.
 
 `deleted` -  boolean
 
 `description` -  string
 
 `digitalProduct` -  
 
 `disabled` - 
 
 `expirationDate` - 
 
 `featured` - boolean
 
 `gtin` - 
 
 `gtinType` -
- GTIN8
- GTIN12
- GTIN13
- ITF
- MPN
- UPC
- JAN
- EAN
- GTIN14 
  
 `id` - string - 
 
 `imageLink` - string -
 
 `inventoryLevel` - integer - 
 
 `inventoryTracking` - string -
 - none
 - product
 - variant 
 
 `isbn` - string -
 
 `link` - string -
 
 `maxOrderQuantity` - 
 
 `minOrderQuantity` - 
 
 `mobileLink` - 
 
 `physicalSpecs	` - [PhysicalSpecifications](Common_Fields/physicalspecs.md) -
  
 `productRef` - string -
 
 `status` - 
 - APPROVED
 - UNAPPROVED
 - CHECK
 - VERIFICATION_PENDING 
 
 `stock` - [Stock](Common_Fields/stock.md)
 
 `title` - string  - Title
  
 `variance` - The array for vaiants.
  
 `variantOptions` - [VariantOptions](Common_Fields/variantoptions.md) - Array of variant Options. 
 
</details> 

### Create a Product Variants

Creates a new Product Variants data set in the TWC system.

Endpoint: ```/api/v2/products/variants```

Method: ``` POST ```

Method Name: `createVariantProduct`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Payload</summary>
 
 {
  "active": true,
  "additionalImageLink": "string",
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
  "availability": "available",
  "availabilityDescription": "string",
  "baseProductId": "string",
  "baseProductRef": "string",
  "brandId": "string",
  "brandName": "string",
  "calculatedPrice": 0,
  "color": "string",
  "condition": "New",
  "cost": 0,
  "defaultVariant": "string",
  "deleted": true,
  "description": "string",
  "digitalProduct": true,
  "disabled": true,
  "expirationDate": "2022-06-21T06:11:41.075Z",
  "featured": true,
  "gtin": "string",
  "gtinType": "GTIN8",
  "id": "string",
  "imageLink": "string",
  "inventoryLevel": 0,
  "inventoryTracking": "none",
  "isbn": "string",
  "link": "string",
  "maxOrderQuantity": 0,
  "minOrderQuantity": 0,
  "mobileLink": "string",
  "physicalSpecs": {
    "dimensionUnitCode": "string",
    "dimensionUnitName": "string",
    "maxDepth": 0,
    "maxHeight": 0,
    "maxWeight": 0,
    "maxWidth": 0,
    "minWeight": 0,
    "weightUnitCode": "string",
    "weightUnitName": "string"
  },
  "productRef": "string",
  "status": "APPROVED",
  "stock": {
    "stockLevels": [
      {
        "locationRef": "string",
        "locationid": "string",
        "stock": "string"
      }
    ],
    "totalStock": "string"
  },
  "title": "string",
  "variance": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "variantOptions": [
    {
      "optionDefaultImage": "string",
      "optionId": "string",
      "optionLabel": "string",
      "optionValue": "string",
      "optionsImageId": "string"
    }
  ]
}
 
</details>

<details>
 <summary>Response</summary>
 
 {
  "active": true,
  "additionalImageLink": "string",
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
  "availability": "available",
  "availabilityDescription": "string",
  "baseProductId": "string",
  "baseProductRef": "string",
  "brandId": "string",
  "brandName": "string",
  "calculatedPrice": 0,
  "color": "string",
  "condition": "New",
  "cost": 0,
  "defaultVariant": "string",
  "deleted": true,
  "description": "string",
  "digitalProduct": true,
  "disabled": true,
  "expirationDate": "2022-06-21T06:11:41.093Z",
  "featured": true,
  "gtin": "string",
  "gtinType": "GTIN8",
  "id": "string",
  "imageLink": "string",
  "inventoryLevel": 0,
  "inventoryTracking": "none",
  "isbn": "string",
  "link": "string",
  "maxOrderQuantity": 0,
  "minOrderQuantity": 0,
  "mobileLink": "string",
  "physicalSpecs": {
    "dimensionUnitCode": "string",
    "dimensionUnitName": "string",
    "maxDepth": 0,
    "maxHeight": 0,
    "maxWeight": 0,
    "maxWidth": 0,
    "minWeight": 0,
    "weightUnitCode": "string",
    "weightUnitName": "string"
  },
  "productRef": "string",
  "status": "APPROVED",
  "stock": {
    "stockLevels": [
      {
        "locationRef": "string",
        "locationid": "string",
        "stock": "string"
      }
    ],
    "totalStock": "string"
  },
  "title": "string",
  "variance": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "variantOptions": [
    {
      "optionDefaultImage": "string",
      "optionId": "string",
      "optionLabel": "string",
      "optionValue": "string",
      "optionsImageId": "string"
    }
  ]
}

</details> 

HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`


### Update a Product Variant
Update Product Variant data set in the TWC system.

Endpoint: ```/api/v2/products/variants```

Method: ``` PUT ```

Method Name: `updateVariantProduct`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Payload</summary>
 
 {
  "active": true,
  "additionalImageLink": "string",
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
  "availability": "available",
  "availabilityDescription": "string",
  "baseProductId": "string",
  "baseProductRef": "string",
  "brandId": "string",
  "brandName": "string",
  "calculatedPrice": 0,
  "color": "string",
  "condition": "New",
  "cost": 0,
  "defaultVariant": "string",
  "deleted": true,
  "description": "string",
  "digitalProduct": true,
  "disabled": true,
  "expirationDate": "2022-06-21T06:12:22.906Z",
  "featured": true,
  "gtin": "string",
  "gtinType": "GTIN8",
  "id": "string",
  "imageLink": "string",
  "inventoryLevel": 0,
  "inventoryTracking": "none",
  "isbn": "string",
  "link": "string",
  "maxOrderQuantity": 0,
  "minOrderQuantity": 0,
  "mobileLink": "string",
  "physicalSpecs": {
    "dimensionUnitCode": "string",
    "dimensionUnitName": "string",
    "maxDepth": 0,
    "maxHeight": 0,
    "maxWeight": 0,
    "maxWidth": 0,
    "minWeight": 0,
    "weightUnitCode": "string",
    "weightUnitName": "string"
  },
  "productRef": "string",
  "status": "APPROVED",
  "stock": {
    "stockLevels": [
      {
        "locationRef": "string",
        "locationid": "string",
        "stock": "string"
      }
    ],
    "totalStock": "string"
  },
  "title": "string",
  "variance": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "variantOptions": [
    {
      "optionDefaultImage": "string",
      "optionId": "string",
      "optionLabel": "string",
      "optionValue": "string",
      "optionsImageId": "string"
    }
  ]
}
 
</details>

<details>
 <summary>Response</summary>
 
{
  "active": true,
  "additionalImageLink": "string",
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
  "availability": "available",
  "availabilityDescription": "string",
  "baseProductId": "string",
  "baseProductRef": "string",
  "brandId": "string",
  "brandName": "string",
  "calculatedPrice": 0,
  "color": "string",
  "condition": "New",
  "cost": 0,
  "defaultVariant": "string",
  "deleted": true,
  "description": "string",
  "digitalProduct": true,
  "disabled": true,
  "expirationDate": "2022-06-21T06:12:22.925Z",
  "featured": true,
  "gtin": "string",
  "gtinType": "GTIN8",
  "id": "string",
  "imageLink": "string",
  "inventoryLevel": 0,
  "inventoryTracking": "none",
  "isbn": "string",
  "link": "string",
  "maxOrderQuantity": 0,
  "minOrderQuantity": 0,
  "mobileLink": "string",
  "physicalSpecs": {
    "dimensionUnitCode": "string",
    "dimensionUnitName": "string",
    "maxDepth": 0,
    "maxHeight": 0,
    "maxWeight": 0,
    "maxWidth": 0,
    "minWeight": 0,
    "weightUnitCode": "string",
    "weightUnitName": "string"
  },
  "productRef": "string",
  "status": "APPROVED",
  "stock": {
    "stockLevels": [
      {
        "locationRef": "string",
        "locationid": "string",
        "stock": "string"
      }
    ],
    "totalStock": "string"
  },
  "title": "string",
  "variance": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "variantOptions": [
    {
      "optionDefaultImage": "string",
      "optionId": "string",
      "optionLabel": "string",
      "optionValue": "string",
      "optionsImageId": "string"
    }
  ]
}

</details> 

HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Validate Product Variant

Validates the Product Variant 

Endpoint: ```/api/v2/products/variants/validate```

Method: ``` POST ```

Method Name: `validateVariantProduct`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Payload</summary>
 
 {
  "active": true,
  "additionalImageLink": "string",
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
  "availability": "available",
  "availabilityDescription": "string",
  "baseProductId": "string",
  "baseProductRef": "string",
  "brandId": "string",
  "brandName": "string",
  "calculatedPrice": 0,
  "color": "string",
  "condition": "New",
  "cost": 0,
  "defaultVariant": "string",
  "deleted": true,
  "description": "string",
  "digitalProduct": true,
  "disabled": true,
  "expirationDate": "2022-06-21T06:13:22.644Z",
  "featured": true,
  "gtin": "string",
  "gtinType": "GTIN8",
  "id": "string",
  "imageLink": "string",
  "inventoryLevel": 0,
  "inventoryTracking": "none",
  "isbn": "string",
  "link": "string",
  "maxOrderQuantity": 0,
  "minOrderQuantity": 0,
  "mobileLink": "string",
  "physicalSpecs": {
    "dimensionUnitCode": "string",
    "dimensionUnitName": "string",
    "maxDepth": 0,
    "maxHeight": 0,
    "maxWeight": 0,
    "maxWidth": 0,
    "minWeight": 0,
    "weightUnitCode": "string",
    "weightUnitName": "string"
  },
  "productRef": "string",
  "status": "APPROVED",
  "stock": {
    "stockLevels": [
      {
        "locationRef": "string",
        "locationid": "string",
        "stock": "string"
      }
    ],
    "totalStock": "string"
  },
  "title": "string",
  "variance": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "variantOptions": [
    {
      "optionDefaultImage": "string",
      "optionId": "string",
      "optionLabel": "string",
      "optionValue": "string",
      "optionsImageId": "string"
    }
  ]
}


</details>

<details>
 <summary>Response</summary>
 OK
</details> 
HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`



### Find Product Variant by ID

Returns a Product Variant by its ID from a specific Store while passing the respective ID as a query param in the endpoint. The Tenant authentication maps to a Store.
If the Product Variant does not exist, this method returns a Blank.
Endpoint: ```/api/v2/products/variants/{id}```

Method: ``` GET ```

Method Name: `getVariantProduct`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Request Parameters</summary>
 
 - Query Paramters
	- {aggregateStock}
	- {queryStock}
	
 - Path variables
	- {id}
</details>

<details>
 <summary>Response</summary>
 
 {
  "active": true,
  "additionalImageLink": "string",
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
  "availability": "available",
  "availabilityDescription": "string",
  "baseProductId": "string",
  "baseProductRef": "string",
  "brandId": "string",
  "brandName": "string",
  "calculatedPrice": 0,
  "color": "string",
  "condition": "New",
  "cost": 0,
  "defaultVariant": "string",
  "deleted": true,
  "description": "string",
  "digitalProduct": true,
  "disabled": true,
  "expirationDate": "2022-06-21T06:14:04.176Z",
  "featured": true,
  "gtin": "string",
  "gtinType": "GTIN8",
  "id": "string",
  "imageLink": "string",
  "inventoryLevel": 0,
  "inventoryTracking": "none",
  "isbn": "string",
  "link": "string",
  "maxOrderQuantity": 0,
  "minOrderQuantity": 0,
  "mobileLink": "string",
  "physicalSpecs": {
    "dimensionUnitCode": "string",
    "dimensionUnitName": "string",
    "maxDepth": 0,
    "maxHeight": 0,
    "maxWeight": 0,
    "maxWidth": 0,
    "minWeight": 0,
    "weightUnitCode": "string",
    "weightUnitName": "string"
  },
  "productRef": "string",
  "status": "APPROVED",
  "stock": {
    "stockLevels": [
      {
        "locationRef": "string",
        "locationid": "string",
        "stock": "string"
      }
    ],
    "totalStock": "string"
  },
  "title": "string",
  "variance": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "variantOptions": [
    {
      "optionDefaultImage": "string",
      "optionId": "string",
      "optionLabel": "string",
      "optionValue": "string",
      "optionsImageId": "string"
    }
  ]
}
 
</details> 
HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Find Product Variant by Ref

Returns a Product variant by its Ref from a specific Store while passing the respective Ref as a path param in the endpoint. The Tenant authentication maps to a Store.
If the Product does not exist, this method returns a blank response.

Endpoint: ```/api/v2/products/variants/{variantRef}/byref```

Method: ``` GET ``` 

Method Name: `getVariantProductByRef`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Request Parameters</summary>
 
- Query Paramters
	- {aggregateStock}	
	- {queryStock}
	
- Path variables

	- {variantRef}
	
</details>

<details>
 <summary>Response</summary>
 
 {
  "active": true,
  "additionalImageLink": "string",
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
  "availability": "available",
  "availabilityDescription": "string",
  "baseProductId": "string",
  "baseProductRef": "string",
  "brandId": "string",
  "brandName": "string",
  "calculatedPrice": 0,
  "color": "string",
  "condition": "New",
  "cost": 0,
  "defaultVariant": "string",
  "deleted": true,
  "description": "string",
  "digitalProduct": true,
  "disabled": true,
  "expirationDate": "2022-06-21T06:17:47.571Z",
  "featured": true,
  "gtin": "string",
  "gtinType": "GTIN8",
  "id": "string",
  "imageLink": "string",
  "inventoryLevel": 0,
  "inventoryTracking": "none",
  "isbn": "string",
  "link": "string",
  "maxOrderQuantity": 0,
  "minOrderQuantity": 0,
  "mobileLink": "string",
  "physicalSpecs": {
    "dimensionUnitCode": "string",
    "dimensionUnitName": "string",
    "maxDepth": 0,
    "maxHeight": 0,
    "maxWeight": 0,
    "maxWidth": 0,
    "minWeight": 0,
    "weightUnitCode": "string",
    "weightUnitName": "string"
  },
  "productRef": "string",
  "status": "APPROVED",
  "stock": {
    "stockLevels": [
      {
        "locationRef": "string",
        "locationid": "string",
        "stock": "string"
      }
    ],
    "totalStock": "string"
  },
  "title": "string",
  "variance": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "variantOptions": [
    {
      "optionDefaultImage": "string",
      "optionId": "string",
      "optionLabel": "string",
      "optionValue": "string",
      "optionsImageId": "string"
    }
  ]
}
 
</details> 
HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Delete Product variant by Ref

Deleting a Product variant by ref marks the Product variant as deleted and produces the HTTP response confirming the action.
If the product variant does not exist, this method returns a empty response.

Endpoint: ```/api/v2/products/{baseProductRef}/variants/{variantRef}/byref```

Method: ``` DELETE ``` 

Method Name: `deleteVariantProductbyRef`

OAuth 2.0 Scopes: `Tenant authentication`

<details>

 <summary>Path Variable</summary>
 
	- {baseProductRef}
	- {variantRef}
	
</details>

<details>
 <summary>Response</summary> 
</details> 

HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Find  Product variants by productId
Returns a list of  Product variants  from a specific Store while passing the productId as a Path variable in the endpoint. The Tenant authentication maps to a Store.
If the Product variants does not exist, this method returns a empty list.

Endpoint: ```/api/v2/products/{productId}/variants```

Method: ``` GET ``` 

Method Name: `getAllVariantProducts`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Path Variable</summary>
 - {productId}
 
</details>

<details>
 <summary>Response</summary>
 OK
</details> 
HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Find  Product variants by productId
Returns Product variant from a specific Store while passing the productId as a Path variable in the endpoint. The Tenant authentication maps to a Store.
If the Product variant does not exist, this method returns a empty list.

Endpoint: ```/api/v2/products/{productId}/variants```

Method: ``` GET ``` 

Method Name: `getVariantProducts`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Path Variable</summary>
 - {productId}
 
</details>

<details>
 <summary>Response</summary>
 
 [
  {
    "active": true,
    "additionalImageLink": "string",
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
    "availability": "available",
    "availabilityDescription": "string",
    "baseProductId": "string",
    "baseProductRef": "string",
    "brandId": "string",
    "brandName": "string",
    "calculatedPrice": 0,
    "color": "string",
    "condition": "New",
    "cost": 0,
    "defaultVariant": "string",
    "deleted": true,
    "description": "string",
    "digitalProduct": true,
    "disabled": true,
    "expirationDate": "2022-06-21T06:20:54.485Z",
    "featured": true,
    "gtin": "string",
    "gtinType": "GTIN8",
    "id": "string",
    "imageLink": "string",
    "inventoryLevel": 0,
    "inventoryTracking": "none",
    "isbn": "string",
    "link": "string",
    "maxOrderQuantity": 0,
    "minOrderQuantity": 0,
    "mobileLink": "string",
    "physicalSpecs": {
      "dimensionUnitCode": "string",
      "dimensionUnitName": "string",
      "maxDepth": 0,
      "maxHeight": 0,
      "maxWeight": 0,
      "maxWidth": 0,
      "minWeight": 0,
      "weightUnitCode": "string",
      "weightUnitName": "string"
    },
    "productRef": "string",
    "status": "APPROVED",
    "stock": {
      "stockLevels": [
        {
          "locationRef": "string",
          "locationid": "string",
          "stock": "string"
        }
      ],
      "totalStock": "string"
    },
    "title": "string",
    "variance": {
      "additionalProp1": "string",
      "additionalProp2": "string",
      "additionalProp3": "string"
    },
    "variantOptions": [
      {
        "optionDefaultImage": "string",
        "optionId": "string",
        "optionLabel": "string",
        "optionValue": "string",
        "optionsImageId": "string"
      }
    ]
  }
]
 
</details> 
HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`

### Delete Product variants by product Id/variantId

Deleting a Product variants marks the Product variants as deleted and produces the HTTP response confirming the action.
If the Product variants does not exist, this method returns a empty response.

Endpoint: ```/api/v2/products/{productId}/variants/{variantId}```

Method: ``` DELETE ```

Method Name: `deleteVariantProduct`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Path Variable</summary>
 
	- {productId}
	- {variantId}
	
</details>

<details>
 <summary>Response</summary>
 OK
</details> 
HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`



### Upload Product Variants
Creates an array of new Product variants in the TWC system.

Endpoint: ```/api/v2/uploadVariants```

Method: ``` POST ```

Method Name: `uploadProducts`

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Payload</summary>
 
 [
  {
    "active": true,
    "additionalImageLink": "string",
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
    "availability": "available",
    "availabilityDescription": "string",
    "baseProductId": "string",
    "baseProductRef": "string",
    "brandId": "string",
    "brandName": "string",
    "calculatedPrice": 0,
    "color": "string",
    "condition": "New",
    "cost": 0,
    "defaultVariant": "string",
    "deleted": true,
    "description": "string",
    "digitalProduct": true,
    "disabled": true,
    "expirationDate": "2022-06-21T06:22:48.286Z",
    "featured": true,
    "gtin": "string",
    "gtinType": "GTIN8",
    "id": "string",
    "imageLink": "string",
    "inventoryLevel": 0,
    "inventoryTracking": "none",
    "isbn": "string",
    "link": "string",
    "maxOrderQuantity": 0,
    "minOrderQuantity": 0,
    "mobileLink": "string",
    "physicalSpecs": {
      "dimensionUnitCode": "string",
      "dimensionUnitName": "string",
      "maxDepth": 0,
      "maxHeight": 0,
      "maxWeight": 0,
      "maxWidth": 0,
      "minWeight": 0,
      "weightUnitCode": "string",
      "weightUnitName": "string"
    },
    "productRef": "string",
    "status": "APPROVED",
    "stock": {
      "stockLevels": [
        {
          "locationRef": "string",
          "locationid": "string",
          "stock": "string"
        }
      ],
      "totalStock": "string"
    },
    "title": "string",
    "variance": {
      "additionalProp1": "string",
      "additionalProp2": "string",
      "additionalProp3": "string"
    },
    "variantOptions": [
      {
        "optionDefaultImage": "string",
        "optionId": "string",
        "optionLabel": "string",
        "optionValue": "string",
        "optionsImageId": "string"
      }
    ]
  }
]
  
</details>

<details>
 <summary>Response</summary>
 OK
</details> 

HTTP Status Code: `200 OK ,201	Created, 401 Unauthorized, 403 Forbidden, 404 Not Found`
