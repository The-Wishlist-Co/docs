
# **Inventory**
An inventory item represents a physical good. It holds essential information about the physical good, including its SKU and whether its inventory is tracked.

There is a 1:1 relationship between a product variant and an inventory item. Each product variant includes the ID of its related inventory item. You can use the inventory item ID to query the InventoryLevel resource to retrieve the location and quantity for an inventory item.

Use the **InventoryItem** resource together with the InventoryLevel and Location resources to manage a store's inventory across multiple locations.
An inventory level represents the quantities of an inventory item for a location.

Each **inventory level** belongs to one inventory item and has one location. For every location where an inventory item can be stocked, there's an inventory level that represents the inventory item's quantities relating to that location.

An **inventory location** represents a geographical location where your stores, pop-up stores, headquarters, and warehouses exist. You can use the Location resource to track sales, manage inventory, and configure the tax rates to apply at checkout. 

## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.

<details>
 <summary><font size="4">Inventory Item</font></summary>

```admin_graphql_api_id``` - string

```cost``` - number - The unit cost of the inventory item. The shop's default currency is used.


```country_code_of_origin``` - string - 
The country code (ISO 3166-1 alpha-2) of where the item came from.

```country_harmonized_system_codes``` - string -
An array of country-specific Harmonized System (HS) codes for the item. Used to determine duties when shipping the inventory item to certain countries.

```created_at``` - DateTime

```deleted``` - boolean - To mark item as deleted from inventory.

```harmonized_system_code``` - string - The general Harmonized System (HS) code for the inventory item. Used if a country-specific HS code (countryHarmonizedSystemCode) is not available.

```id``` - string - The ID of the inventory item.


```province_code_of_origin``` - string- The province code (ISO 3166-2 alpha-2) of where the item came from. The province code is only used if the shipping provider for the inventory item is Canada Post.

```requires_shipping``` - boolean - To enable shipping requirement status.

```sku``` - string - The unique SKU (stock keeping unit) of the inventory item.

```tracked``` - boolean - Whether inventory levels are tracked for the item. If true, then the inventory quantity changes are tracked.

```updated_at``` - The date and time when the inventory item was last modified.

</details>


<details>
 <summary><font size="4">Location </font></summary>
`active` - boolean - Whether the location is active. If true, then the location can be used to sell products, stock inventory, and fulfill orders. Deactivated locations don't contribute to the shop's location limit.

```address1``` - string - The location's street address.

```address2``` - string - The optional second line of the location's street address.

```admin_graphql_api_id``` - string

```city``` - string - The city the location is in.

```country``` - string - The country the location is in.

```country_code``` - string - The two-letter code (ISO 3166-1 alpha-2 format) corresponding to country the location is in.

```country_name``` - string

```created_at``` - The date and time (ISO 8601 format) when the location was created.


```id``` - string -The ID of the location.

```legacy``` - boolean - Whether this is a fulfillment service location. If true, then the location is a fulfillment service location. If false, then the location was created by the merchant and isn't tied to a fulfillment service.


```localized_country_name``` - string - The localized name of the location's country.


```localized_province_name``` -string - The localized name of the location's region. Typically a province, state, or district.


```name``` - string - The name of the location.

```phone``` - string - The phone number of the location. This value can contain special characters, such as - or +.


```province``` - string - The province, state, or district of the location.

```province_code``` - string -The province, state, or district code (ISO 3166-2 alpha-2 format) of the location.


```updated_at``` - The date and time (ISO 8601 format) when the location was last updated.


```zip``` - string - The zip or postal code.

</details>

<details>
 <summary><font size="4">Inventory Level </font></summary>
```admin_graphql_api_id``` - string

```available``` - integer - The available quantity of an inventory item at the inventory level's associated location. Returns null if the inventory item is not tracked.

```created_at``` - The date and time (ISO 8601 format) when the location was created.

```inventory_item_id``` - string - The ID of the inventory item associated with the inventory level. To find the ID of an inventory item, use the Inventory Item resource.

```location_id``` - string -The ID of the location that the inventory level belongs to. To find the ID of the location, use the Location resource.

```updated_at``` - The date and time (ISO 8601 format) when the inventory level was last modified.

</details>

## **REST Endpoints**

## Create an inventory item

Method: ``` POST ``` 

Endpoint: ```​/api​/inventoryitem```

OAuth 2.0 Scopes: `Tenant authentication`

## Updated an inventory level

Method: ``` PUT ``` 

Endpoint: ```/api​/inventoryitem​```

OAuth 2.0 Scopes: `Tenant authentication`

## Find Inventory Item by Ref

Method: ``` GET ``` 

Endpoint: ```/api​/inventoryitem​/{inventoryRef}```

OAuth 2.0 Scopes: `Tenant authentication`

## Upload many inventory levels

Method: ``` POST ``` 

Endpoint: ```/api​/inventoryitem​s```

OAuth 2.0 Scopes: `Tenant authentication`

## Create an inventory level

Method: ``` POST ``` 

Endpoint: ```/api​/inventorylevel```

OAuth 2.0 Scopes: `Tenant authentication`



## Updated an inventory level

Method: ``` PUT ``` 

Endpoint: ```/api​/inventorylevel```

OAuth 2.0 Scopes: `Tenant authentication`

## Find InventoryLevel By Id

Method: ``` GET ``` 

Endpoint: ```​/api​/inventorylevel​/inventoryitem​/{inventoryItemRef}​/location​/{locationRef}```

OAuth 2.0 Scopes: `Tenant authentication`

## Create an inventory level

Method: ``` POST ``` 

Endpoint: ```/api​/inventorylevels```

OAuth 2.0 Scopes: `Tenant authentication`

## Create an inventory Location

Method: ``` POST ``` 

Endpoint: ```/api​/inventorylocation```

OAuth 2.0 Scopes: `Tenant authentication`

## Updated an inventory level

Method: ``` PUT ``` 

Endpoint: ```​/api​/inventorylocation```

OAuth 2.0 Scopes: `Tenant authentication`

## Find Customer by ID

Method: ``` GET ``` 

Endpoint: ```​/api​/inventorylocation​/{id}```

OAuth 2.0 Scopes: `Tenant authentication`

## Create multiple inventory Locations

Method: ``` POST ``` 

Endpoint: ```/api​/inventorylocations```

OAuth 2.0 Scopes: `Tenant authentication`


***
[Back to Shopify connector](../ShopifyConnector.md)

[Back to Index](index.md)