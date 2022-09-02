
[Back to Home](index.md#welcome-to-the-wishlist)


# **Product API**
The Product resource stores information about a product, its variants.

### Index

***

 - [**Price API**](#price-api)  
    - [**Index**](#index)
      - [**Representations**](#representations)
        - [Product](#product)
        - [Product Variant](#product-variant)
      - [**REST Endpoints**](#rest-endpoints)
        - [**Product Service**](#product-service)
          - [Create a Product](#create-a-product)
          - [Update a Product](#update-a-product)
		  - [Update a Product By ID](#update-a-product-by-id)
		  - [Update a Product By Prodref](#update-a-product-by-prodref)
          - [Look up Product by gtin/productRef](#look-up-product-by-gtinproductref)
          - [Validate Request](#validate-request)
          - [Validate Product](#validate-product)
          - [Validate Product by Ref](#validate-product-by-ref)
          - [Find Product by ID](#find-product-by-id)
          - [Delete Product by ID](#delete-product-by-id)
          - [Find Product by Ref](#find-product-by-ref)
          - [Delete Product by Ref](#delete-product-by-ref)
          - [Upload Products](#upload-products)
        - [**Product Variant Service**](#product-variant-service)
          - [Create a Product Variants](#create-a-product-variants)
          - [Update a Product Variant](#update-a-product-variant)
		  - [Update a Product Variant By ID](#update-a-product-variant-by-id)
		  - [Update a Product Variant By Variant Ref](#update-a-product-variant-by-variant-ref)
          - [Validate Product Variant](#validate-product-variant)
          - [Find Product Variant by ID](#find-product-variant-by-id)
          - [Find Product Variant by Ref](#find-product-variant-by-ref)
          - [Delete Product variant by Ref](#delete-product-variant-by-ref)
      


## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.


##  Product

***
Represents a product. 
 
 `active` - boolean - To enable  a product.
 
 `additionalImageLink` - string - Image link.
 
 `attributeGroups` - [AttributeGroup](Common_Fields/attributeGroup.md) - The group of attibute values stored under as a object in group of atributeGroups.
 
 `availability` - string - Product Availablity and value should be one of the below values.
 - available
 - preorder
 - disabled 
 
 `availabilityDescription` - String- In detail of the product availability.
 
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
 
 `variants` - [productVariants](Common_Fields/productVariant.md) - Array of variant Options.
 
 `variantsAvailable` - boolean -

 `createdDate` - The date and time (ISO 8601 format) when the customer was created.

 `lastModifiedDate` - The date and time (ISO 8601 format) when the customer information was last updated.



##  Product Variant
***
Represents a product Variant.

 
  `active` - boolean - To enable  a product variant.
 
 `additionalImageLink` - string - Image link.
 
 `attributeGroups` - [AttributeGroup](Common_Fields/attributeGroup.md) - The group of attibute values stored under as a object in group of atributeGroups.
 
 `availability` - string - Product Availablity and value should be one of the below values.
 - available
 - preorder
 - disabled 
 
 `availabilityDescription` - String- In detailed <!-- <details> -->
 of the product availability.
 
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

`createdDate` - The date and time (ISO 8601 format) when the customer was created.

`lastModifiedDate` - The date and time (ISO 8601 format) when the customer information was last updated.


## **REST Endpoints**

## **Product Service**
 
## Create a Product
Creates a new Product data set in the TWC system.

Endpoint: ```/api/v2/products```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Sample Request :</summary>
 
 ```json
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
 ```

<summary>Response - 201 (Created)</summary>

```json
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
      ],
      "createdDate": "2022-08-31T04:46:13.275Z",
      "lastModifiedDate": "2022-08-31T04:48:33.731Z"
    }
  ],
  "variantsAvailable": true,
  "createdDate": "2022-08-31T04:46:13.275Z",
  "lastModifiedDate": "2022-08-31T04:48:33.731Z"
}

```


HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Update a Product
Update Product data set in the TWC system.

Endpoint: ```/api/v2/products```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)


 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Sample Request :</summary>
 
 ```json
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

 ```
 

<summary>Response - 200 (OK)</summary>
 
 ```json
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
  "expirationDate": "2022-06-22T07:32:52.279Z",
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
      "expirationDate": "2022-06-22T07:32:52.279Z",
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
      ],
      
      "createdDate": "2022-08-31T04:46:13.275Z",
      "lastModifiedDate": "2022-08-31T04:48:33.731Z"
    }
  ],
  "variantsAvailable": true,
  "createdDate": "2022-08-31T04:46:13.275Z",
  "lastModifiedDate": "2022-08-31T04:48:33.731Z"
}
```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Update a Product By ID
Update Product data set in the TWC system.

Endpoint: ```/api/v2/products/variants/id={id}```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)


 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable:

```
id= Product id

```
 

 <summary>Sample Request :</summary>
 
 ```json
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

 ```
 

<summary>Response - 200 (OK)</summary>
 
 ```json
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
  "expirationDate": "2022-06-22T07:32:52.279Z",
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
      "expirationDate": "2022-06-22T07:32:52.279Z",
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
      ],
      "createdDate": "2022-08-31T04:46:13.275Z",
      "lastModifiedDate": "2022-08-31T04:48:33.731Z"
    }
  ],
  "variantsAvailable": true,
  "createdDate": "2022-08-31T04:46:13.275Z",
  "lastModifiedDate": "2022-08-31T04:48:33.731Z"
}
```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Update a Product By Prodref

Update Product data set in the TWC system based on Prodref.

Endpoint: ```/api/v2/products/ref={productRef}```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)


 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |


Path Variable:

```
ref - variantRef
```
 

 <summary>Sample Request :</summary>
 
 ```json
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

 ```
 

<summary>Response - 200 (OK)</summary>
 
 ```json
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
  "expirationDate": "2022-06-22T07:32:52.279Z",
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
      "expirationDate": "2022-06-22T07:32:52.279Z",
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
      ],
      "createdDate": "2022-08-31T04:46:13.275Z",
      "lastModifiedDate": "2022-08-31T04:48:33.731Z"
    }
  ],
  "variantsAvailable": true,
  "createdDate": "2022-08-31T04:46:13.275Z",
  "lastModifiedDate": "2022-08-31T04:48:33.731Z"
}
```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Look up Product by gtin/productRef
Returns a list of  products  from a specific Store while passing the gtin/productRef as a query params in the endpoint. The Tenant authentication maps to a Store.
If the products does not exist, this method returns a empty list.

Endpoint: ```/api/v2/products/lookup```

Method: ``` GET ``` 

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)



 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Query Parameters :</summary>
 
 ```
 - {gtin}
 - {productRef}
```

<summary>Response - 200 (OK)</summary>
 
 ```json
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
          ],
          "createdDate": "2022-08-31T04:46:13.275Z",
          "lastModifiedDate": "2022-08-31T04:48:33.731Z"
        }
      ],
      "variantsAvailable": true,
      "createdDate": "2022-08-31T04:46:13.275Z",
      "lastModifiedDate": "2022-08-31T04:48:33.731Z"
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
      ],
      "createdDate": "2022-08-31T04:46:13.275Z",
      "lastModifiedDate": "2022-08-31T04:48:33.731Z"
    }
  ]
}

```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Validate Request

Validates the Product Request 

Endpoint: ```/api/v2/products/validate```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Sample Request : </summary>

```json
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
```

<summary>Response - 200 (OK)</summary>


HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Validate Product
Validates the product based on ID and ID will be passed as path variable.

Endpoint: ```/api/v2/products/validate/{id}```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)


 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Path Variable : </summary>

```
 - {id}
```

<summary>Response - 200 (OK)</summary>
 
 ```json
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
        ],
        "createdDate": "2022-08-31T04:46:13.275Z",
        "lastModifiedDate": "2022-08-31T04:48:33.731Z"
      }
    ],
    "variantsAvailable": true,
    "createdDate": "2022-08-31T04:46:13.275Z",
    "lastModifiedDate": "2022-08-31T04:48:33.731Z"
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
    ],
    "createdDate": "2022-08-31T04:46:13.275Z",
    "lastModifiedDate": "2022-08-31T04:48:33.731Z"
  }
}
```


HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Validate Product by Ref
Validates the product based on ref and ref will be passed as path variable.

Endpoint: ```/api/v2/products/validateRef/{ref}```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Path Variable :

</summary>

```
 - {ref}
```
<summary>Response - 200 (OK)</summary>
 
 ```json
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
        ],
        "createdDate": "2022-08-31T04:46:13.275Z",
        "lastModifiedDate": "2022-08-31T04:48:33.731Z"
      }
    ],
    "variantsAvailable": true,
    "createdDate": "2022-08-31T04:46:13.275Z",
    "lastModifiedDate": "2022-08-31T04:48:33.731Z"
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
    ],
    "createdDate": "2022-08-31T04:46:13.275Z",
    "lastModifiedDate": "2022-08-31T04:48:33.731Z"
  }
}
```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Find Product by ID

Returns a Product by its ID from a specific Store while passing the respective ID as a path variable in the endpoint. The Tenant authentication maps to a Store.
If the Product does not exist, this method returns a Blank.

Endpoint: ```/api/v2/products/{id}```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)


 <summary>Request Headers :

</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

 <summary>Path Variable :

</summary>

```
 - {id}
```

<summary>Response - 200 (OK)</summary>
 
 ```json
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
      ],
      "createdDate": "2022-08-31T04:46:13.275Z",
      "lastModifiedDate": "2022-08-31T04:48:33.731Z"
    }
  ],
  "variantsAvailable": true,
  "createdDate": "2022-08-31T04:46:13.275Z",
  "lastModifiedDate": "2022-08-31T04:48:33.731Z"
}
```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Delete Product by ID
Deleting a Product marks the Product as deleted and produces the HTTP response confirming the action.
If the Product does not exist, this method returns a empty response.

Endpoint: ```/api/v2/products/{id}```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Path Variable :</summary>
 
 ```
	- {id}
 ```


<summary>Response - 204 (Deleted)</summary> 

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Find Product by Ref

Returns a Product by its Ref from a specific Store while passing the respective Ref as a path param in the endpoint. The Tenant authentication maps to a Store.
If the Product does not exist, this method returns a blank response.

Endpoint: ```/api/v2/products/{productRef}/byref```

Method: ``` GET ``` 

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Path Variable :

</summary>

```
- {productRef}
```

<summary>Response - 200 (OK)</summary>
 
 ```json
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
      ],
      "createdDate": "2022-08-31T04:46:13.275Z",
      "lastModifiedDate": "2022-08-31T04:48:33.731Z"
    }
  ],
  "variantsAvailable": true,
  "createdDate": "2022-08-31T04:46:13.275Z",
  "lastModifiedDate": "2022-08-31T04:48:33.731Z"
}
```

HTTP Status Code: 
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Delete Product by Ref

Deleting a Product by ref marks the Product as deleted and produces the HTTP response confirming the action.
If the product does not exist, this method returns a empty response.

Endpoint: ```/api/v2/products/{productRef}/byref```

Method: ``` DELETE ``` 

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)


 <summary>Request Headers :

</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Path Variable :

</summary>

```
	- {productRef}
```	

<summary>Response - 204 (Deleted)</summary> 

HTTP Status Code:
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Upload Products
Creates an array of new products in the TWC system.

Endpoint: ```/api/v2/uploadProducts```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)


 <summary>Request Headers :

</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Sample Request :

</summary>
 
  ```json
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
  ```

<summary>Response - 201 (Created)</summary>  

HTTP Status Code:
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## **Product Variant Service**

## Create a Product Variant

Creates a new Product Variants data set in the TWC system.

Endpoint: ```/api/v2/products/variants```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)


 <summary>Request Headers :

</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

 <summary>Sample Request :

</summary>
 
 ```json
 
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
 ```

<summary>Response - 201 (Created)</summary>
 
 ```json
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
  ],
  "createdDate": "2022-08-31T04:46:13.275Z",
  "lastModifiedDate": "2022-08-31T04:48:33.731Z"
}

```

HTTP Status Code:

``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Update a Product Variant
Update Product Variant data set in the TWC system.

Endpoint: ```/api/v2/products/variants```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :

</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Sample Request :

</summary>
 
 ```json
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
```

<summary>Response - 200 (OK)</summary>

 ```json
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
  ],
  "createdDate": "2022-08-31T04:46:13.275Z",
  "lastModifiedDate": "2022-08-31T04:48:33.731Z"
}
```

HTTP Status Code:
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Update a Product Variant By ID
Update Product Variant data set in the TWC system.

Endpoint: ```/api/v2/products/variants/id={id}```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :

</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

Path Variable:

```
id - Product vatiant ID
```
 

 <summary>Sample Request :

</summary>
 
 ```json
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
```

<summary>Response - 200 (OK)</summary>

 ```json
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
  ],
  "createdDate": "2022-08-31T04:46:13.275Z",
  "lastModifiedDate": "2022-08-31T04:48:33.731Z"
}
```

HTTP Status Code:
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```



## Update a Product Variant By Variant Ref

Update Product Variant data set in the TWC system based on Variant Ref.

Endpoint: ```/api/v2/products/variants/ref={variantRef}```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :

</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 
Path Variable:

```
ref - variantRef
``` 

 <summary>Sample Request :

</summary>
 
 ```json
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
  "condition": "USED",
  "cost": 0,
  "defaultVariant": "string",
  "deleted": true,
  "description": "string",
  "digitalProduct": true,
  "disabled": true,
  "expirationDate": "2022-07-27T12:12:59.505Z",
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
```

<summary>Response - 200 (OK)</summary>

 ```json
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
  ],
  "createdDate": "2022-08-31T04:46:13.275Z",
  "lastModifiedDate": "2022-08-31T04:48:33.731Z"
}
```

HTTP Status Code:
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```



## Validate Product Variant

Validates the Product Variant 

Endpoint: ```/api/v2/products/variants/validate```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)


 <summary>Request Headers :

</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Sample Request :

</summary>
 
 ```json
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
```

<summary>Response - 200 (OK)</summary>

HTTP Status Code:
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Find Product Variant by ID

Returns a Product Variant by its ID from a specific Store while passing the respective ID as a query param in the endpoint. The Tenant authentication maps to a Store.
If the Product Variant does not exist, this method returns a Blank.
Endpoint: ```/api/v2/products/variants/{id}```

Method: ``` GET ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :

</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Request Parameters :</summary>
 

 - Query Paramters

```
	- {aggregateStock}
	- {queryStock}
```	

 - Path variables

```
	- {id}
```

<summary>Response - 200 (OK)</summary>
 
 ```json
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
  ],
      "createdDate": "2022-08-31T04:46:13.275Z",
      "lastModifiedDate": "2022-08-31T04:48:33.731Z"
}
 ```

HTTP Status Code:
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```
## Find Product Variant by Ref

Returns a Product variant by its Ref from a specific Store while passing the respective Ref as a path param in the endpoint. The Tenant authentication maps to a Store.
If the Product does not exist, this method returns a blank response.

Endpoint: ```/api/v2/products/variants/{variantRef}/byref```

Method: ``` GET ``` 

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)


 <summary>Request Headers :

</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Request Parameters :</summary>
 
 
- Query Paramters
  
```
	- {aggregateStock}	
	- {queryStock}
```

- Path variables
```
	- {variantRef}
```

<summary>Response - 200 (OK)</summary>
 
 ```json
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
  ],
  "createdDate": "2022-08-31T04:46:13.275Z",
  "lastModifiedDate": "2022-08-31T04:48:33.731Z"
}
 ```


HTTP Status Code:
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```
## Delete Product variant by Ref

Deleting a Product variant by ref marks the Product variant as deleted and produces the HTTP response confirming the action.
If the product variant does not exist, this method returns a empty response.

Endpoint: ```/api/v2/products/{baseProductRef}/variants/{variantRef}/byref```

Method: ``` DELETE ``` 

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :

</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |


 <summary>Path Variable :

</summary>

``` 
	- {baseProductRef}
	- {variantRef}
```

<summary>Response - 204 (Deleted)</summary> 

HTTP Status Code:
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```
## Find Product variants by productId
Returns a list of  Product variants  from a specific Store while passing the productId as a Path variable in the endpoint. The Tenant authentication maps to a Store.
If the Product variants does not exist, this method returns a empty list.

Endpoint: ```/api/v2/products/{productId}/variants```

Method: ``` GET ``` 

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Path Variable :

</summary>

```
 - {productId}
```

<summary>Response - 200 (OK)</summary>

HTTP Status Code:

``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```
## Find  Product variants by productId
Returns Product variant from a specific Store while passing the productId as a Path variable in the endpoint. The Tenant authentication maps to a Store.
If the Product variant does not exist, this method returns a empty list.

Endpoint: ```/api/v2/products/{productId}/variants```

Method: ``` GET ``` 

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :

</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

 <summary>Path Variable :

</summary>

```
 - {productId}
```

<summary>Response - 200 (OK)</summary>
 
 ```json
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
    ],
    "createdDate": "2022-08-31T04:46:13.275Z",
    "lastModifiedDate": "2022-08-31T04:48:33.731Z"
  }
]
 ```

HTTP Status Code:
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## Delete Product variants by product Id/variantId

Deleting a Product variants marks the Product variants as deleted and produces the HTTP response confirming the action.
If the Product variants does not exist, this method returns a empty response.

Endpoint: ```/api/v2/products/{productId}/variants/{variantId}```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :

</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |
 

Path Variable :
 
 ```
	- {productId}
	- {variantId}
```

<summary>Response - 204 (Deleted)</summary> 	

HTTP Status Code:
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Upload Product Variants
Creates an array of new Product variants in the TWC system.

Endpoint: ```/api/v2/uploadVariants```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)


 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | {Bearer token}   |
| X-TWC-Tenant  | {Tenant Name}    |

 <summary>Sample Request :</summary>
 
 ```json
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
  ```

<summary>Response - 201 (Created)</summary>

HTTP Status Code:
``` 
- 200 OK
- 201 Created
- 204 Deleted
- 400 Bad request unable to create customer
- 401 Unauthorized,
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```
***

[Back to Top](#product-api)

[Back to Home](index.md#welcome-to-the-wishlist)