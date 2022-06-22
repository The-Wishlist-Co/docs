
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

<details>
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

</details>

<details>
 <summary>Payload</summary>
 
```json
 {
  "admin_graphql_api_id": "string",
  "cost": 0,
  "country_code_of_origin": "string",
  "country_harmonized_system_codes": [
    {
      "country_code": "string",
      "harmonized_system_code": "string"
    }
  ],
  "created_at": "2022-06-22T12:27:57.620Z",
  "deleted": true,
  "harmonized_system_code": "string",
  "id": "string",
  "province_code_of_origin": "string",
  "requires_shipping": true,
  "sku": "string",
  "tracked": true,
  "updated_at": "2022-06-22T12:27:57.620Z"
}     
 ```
 
</details>

<details>
 <summary>Response - 200 (OK)</summary>

```json
 {
  "admin_graphql_api_id": "string",
  "cost": 0,
  "country_code_of_origin": "string",
  "country_harmonized_system_codes": [
    {
      "country_code": "string",
      "harmonized_system_code": "string"
    }
  ],
  "created_at": "2022-06-22T12:27:57.639Z",
  "deleted": true,
  "harmonized_system_code": "string",
  "id": "string",
  "province_code_of_origin": "string",
  "requires_shipping": true,
  "sku": "string",
  "tracked": true,
  "updated_at": "2022-06-22T12:27:57.639Z"
}     
 ```
 
</details> 

<details>
 <summary>Response - 201 (OK inventory item created)</summary>
 
 ```json
 {
  "admin_graphql_api_id": "string",
  "cost": 0,
  "country_code_of_origin": "string",
  "country_harmonized_system_codes": [
    {
      "country_code": "string",
      "harmonized_system_code": "string"
    }
  ],
  "created_at": "2022-06-22T12:27:57.640Z",
  "deleted": true,
  "harmonized_system_code": "string",
  "id": "string",
  "province_code_of_origin": "string",
  "requires_shipping": true,
  "sku": "string",
  "tracked": true,
  "updated_at": "2022-06-22T12:27:57.640Z"
}
 ```
 </details> 

<details>
 <summary>Response - 400 (NOK bad request)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 401 (NOK unauthorized)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 405 (Invalid input)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>
 
HTTP Status Code: 
- 200 OK
- 201 OK inventory item created
- 400 NOK bad request
- 401 NOK Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 NOK Invalid input

## Updated an inventory level

Method: ``` PUT ``` 

Endpoint: ```/api​/inventoryitem​```

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

</details>

<details>
 <summary>Payload</summary>
 
```json
 {
  "admin_graphql_api_id": "string",
  "cost": 0,
  "country_code_of_origin": "string",
  "country_harmonized_system_codes": [
    {
      "country_code": "string",
      "harmonized_system_code": "string"
    }
  ],
  "created_at": "2022-06-22T12:34:54.073Z",
  "deleted": true,
  "harmonized_system_code": "string",
  "id": "string",
  "province_code_of_origin": "string",
  "requires_shipping": true,
  "sku": "string",
  "tracked": true,
  "updated_at": "2022-06-22T12:34:54.073Z"
}     
 ```
 
</details>

<details>
 <summary>Response - 200 (OK inventory item created)</summary>

```json
 {
  "admin_graphql_api_id": "string",
  "cost": 0,
  "country_code_of_origin": "string",
  "country_harmonized_system_codes": [
    {
      "country_code": "string",
      "harmonized_system_code": "string"
    }
  ],
  "created_at": "2022-06-22T12:34:54.092Z",
  "deleted": true,
  "harmonized_system_code": "string",
  "id": "string",
  "province_code_of_origin": "string",
  "requires_shipping": true,
  "sku": "string",
  "tracked": true,
  "updated_at": "2022-06-22T12:34:54.092Z"
}     
 ```
 
</details> 


<details>
 <summary>Response - 400 (NOK bad request)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 401 (NOK unauthorized)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 


<details>
 <summary>Response - 405 (NOK Invalid input)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>
 
HTTP Status Code: 
- 200 OK inventory item created
- 201 created
- 400 NOK bad request
- 401 NOK unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 NOK Invalid input

## Find Inventory Item by Ref

Method: ``` GET ``` 

Endpoint: ```/api​/inventoryitem​/{inventoryRef}```

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

</details>

<details>
 <summary>Path Variable</summary>
 
 - {inventoryRef}
 
</details>

<details>
 <summary>Response - 200 (OK Found InventoryItem)</summary>

```json
{
  "admin_graphql_api_id": "string",
  "cost": 0,
  "country_code_of_origin": "string",
  "country_harmonized_system_codes": [
    {
      "country_code": "string",
      "harmonized_system_code": "string"
    }
  ],
  "created_at": "2022-06-22T12:55:48.436Z",
  "deleted": true,
  "harmonized_system_code": "string",
  "id": "string",
  "province_code_of_origin": "string",
  "requires_shipping": true,
  "sku": "string",
  "tracked": true,
  "updated_at": "2022-06-22T12:55:48.436Z"
}      
 ```
 
</details> 

<details>
 <summary>Response - 400 (Bad request unable to create InventoryItem)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 401 (Unauthorized)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 


<details>
 <summary>Response - 404 (InventoryItem with provided id not found)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>

<details>
 <summary>Response - 405 (Invalid input)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>
 
HTTP Status Code: 
- 200 OK Found InventoryItem
- 400 Bad request unable to create InventoryItem
- 401 Unauthorized
- 403 Forbidden 
- 404 InventoryItem with provided id not found
- 405 Invalid input

## Upload many inventory levels

Method: ``` POST ``` 

Endpoint: ```/api​/inventoryitem​s```

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

</details>

<details>
 <summary>Payload</summary>
 
```json
  [
  {
    "admin_graphql_api_id": "string",
    "cost": 0,
    "country_code_of_origin": "string",
    "country_harmonized_system_codes": [
      {
        "country_code": "string",
        "harmonized_system_code": "string"
      }
    ],
    "created_at": "2022-06-22T13:15:14.029Z",
    "deleted": true,
    "harmonized_system_code": "string",
    "id": "string",
    "province_code_of_origin": "string",
    "requires_shipping": true,
    "sku": "string",
    "tracked": true,
    "updated_at": "2022-06-22T13:15:14.029Z"
  }
]    
 ```
 
</details>

<details>
 <summary>Response - 200 (OK)</summary>

```json
 {
  "admin_graphql_api_id": "string",
  "cost": 0,
  "country_code_of_origin": "string",
  "country_harmonized_system_codes": [
    {
      "country_code": "string",
      "harmonized_system_code": "string"
    }
  ],
  "created_at": "2022-06-22T13:15:14.041Z",
  "deleted": true,
  "harmonized_system_code": "string",
  "id": "string",
  "province_code_of_origin": "string",
  "requires_shipping": true,
  "sku": "string",
  "tracked": true,
  "updated_at": "2022-06-22T13:15:14.041Z"
}     
 ```
 
</details> 

<details>
 <summary>Response - 201 (OK inventory item created)</summary>
 
 ```json
 {
  "admin_graphql_api_id": "string",
  "cost": 0,
  "country_code_of_origin": "string",
  "country_harmonized_system_codes": [
    {
      "country_code": "string",
      "harmonized_system_code": "string"
    }
  ],
  "created_at": "2022-06-22T13:15:14.041Z",
  "deleted": true,
  "harmonized_system_code": "string",
  "id": "string",
  "province_code_of_origin": "string",
  "requires_shipping": true,
  "sku": "string",
  "tracked": true,
  "updated_at": "2022-06-22T13:15:14.041Z"
}
 ```
 </details> 

<details>
 <summary>Response - 400 (NOK bad request)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 401 (NOK unauthorized)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 


<details>
 <summary>Response - 404 (not found)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>

<details>
 <summary>Response - 405 (NOK Invalid input)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>
 
HTTP Status Code: 
- 200 OK
- 201 created
- 400 NOK bad request
- 401 NOK unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 NOK Invalid input

## Create an inventory level

Method: ``` POST ``` 

Endpoint: ```/api​/inventorylevel```

OAuth 2.0 Scopes: `Tenant authentication`


<details>
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

</details>

<details>
 <summary>Payload</summary>
 
```json
{
  "admin_graphql_api_id": "string",
  "available": 0,
  "created_at": "2022-06-22T13:18:43.469Z",
  "inventory_item_id": "string",
  "location_id": "string",
  "updated_at": "2022-06-22T13:18:43.469Z"
}      
``` 
</details>

<details>
 <summary>Response - 200 (OK)</summary>

```json
{
  "admin_graphql_api_id": "string",
  "available": 0,
  "created_at": "2022-06-22T13:18:43.519Z",
  "inventory_item_id": "string",
  "location_id": "string",
  "updated_at": "2022-06-22T13:18:43.519Z"
}      
 ```
 
</details> 

<details>
 <summary>Response - 201 (OK inventory level item created)</summary>
 
 ```json
 {
  "admin_graphql_api_id": "string",
  "available": 0,
  "created_at": "2022-06-22T13:18:43.519Z",
  "inventory_item_id": "string",
  "location_id": "string",
  "updated_at": "2022-06-22T13:18:43.519Z"
}
 ```
 </details> 

<details>
 <summary>Response - 400 (NOK bad request)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 401 (NOK unauthorized)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 405 (NOK Invalid input)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>
 
HTTP Status Code: 
- 200 OK
- 201 NOK inventory level item created
- 400 NOK Invalid status value
- 401 NOK Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 NOK Invalid input


## Updated an inventory level

Method: ``` PUT ``` 

Endpoint: ```/api​/inventorylevel```

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

</details>

<details>
 <summary>Payload</summary>
 
```json
{
  "admin_graphql_api_id": "string",
  "available": 0,
  "created_at": "2022-06-22T13:22:49.148Z",
  "inventory_item_id": "string",
  "location_id": "string",
  "updated_at": "2022-06-22T13:22:49.148Z"
}      
 ```
 
</details>

<details>
 <summary>Response - 200 (OK inventory item created)</summary>

```json
{
  "admin_graphql_api_id": "string",
  "available": 0,
  "created_at": "2022-06-22T13:22:49.203Z",
  "inventory_item_id": "string",
  "location_id": "string",
  "updated_at": "2022-06-22T13:22:49.203Z"
}      
 ```
 
</details> 

<details>
 <summary>Response - 400 (NOK bad request)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 401 (NOK Unauthorized)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 


<details>
 <summary>Response - 405 (NOK Invalid input)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>
 
HTTP Status Code: 
- 200 OK inventory item created
- 201 created
- 400 NOK Invalid status value
- 401 NOK Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 NOK Invalid input

## Find InventoryLevel By Id

Method: ``` GET ``` 

Endpoint: ```​/api​/inventorylevel​/inventoryitem​/{inventoryItemRef}​/location​/{locationRef}```

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

</details>

<details>
 <summary>Path Variables</summary>
  - {inventoryItemRef}
  - {locationRef}
 
</details>

<details>
 <summary>Response - 200 (OK Found InventoryLevel)</summary>

```json
 {
  "admin_graphql_api_id": "string",
  "cost": 0,
  "country_code_of_origin": "string",
  "country_harmonized_system_codes": [
    {
      "country_code": "string",
      "harmonized_system_code": "string"
    }
  ],
  "created_at": "2022-06-22T13:26:19.864Z",
  "deleted": true,
  "harmonized_system_code": "string",
  "id": "string",
  "province_code_of_origin": "string",
  "requires_shipping": true,
  "sku": "string",
  "tracked": true,
  "updated_at": "2022-06-22T13:26:19.864Z"
}     
 ```
 
</details> 

<details> 
 <summary>Response - 400 (Bad request unable to create InventoryLevel)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 401 (Unauthorized)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 


<details>
 <summary>Response - 404 (InventoryLevel with provided id not found)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>

<details>
 <summary>Response - 405 (Invalid input)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>
 
HTTP Status Code: 
- 200 OK Found InventoryLevel
- 400 Bad request unable to create InventoryLevel
- 401 Unauthorized
- 403 Forbidden 
- 404 InventoryLevel with provided id not found
- 405 Invalid input

## Create an inventory level

Method: ``` POST ``` 

Endpoint: ```/api​/inventorylevels```

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

</details>

<details>
 <summary>Payload</summary>
 
```json
[
  {
    "admin_graphql_api_id": "string",
    "available": 0,
    "created_at": "2022-06-22T13:31:10.253Z",
    "inventory_item_id": "string",
    "location_id": "string",
    "updated_at": "2022-06-22T13:31:10.253Z"
  }
]      
```
 
</details>

<details>
 <summary>Response - 200 (OK)</summary>

```json
[
  {
    "admin_graphql_api_id": "string",
    "available": 0,
    "created_at": "2022-06-22T13:31:10.253Z",
    "inventory_item_id": "string",
    "location_id": "string",
    "updated_at": "2022-06-22T13:31:10.253Z"
  }
]      
 ```
 
</details> 

<details>
 <summary>Response - 201 (ok inventory level item created)</summary>
 
 ```json
 [
  {
    "admin_graphql_api_id": "string",
    "available": 0,
    "created_at": "2022-06-22T13:31:10.253Z",
    "inventory_item_id": "string",
    "location_id": "string",
    "updated_at": "2022-06-22T13:31:10.253Z"
  }
]
 ```
 </details> 

<details>
 <summary>Response - 400 (NOK bad request)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 401 (NOK unauthorized)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 405 (NOK Invalid input)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>
 
HTTP Status Code: 
- 200 OK
- 201 OK inventory level item created
- 400 NOK bad request
- 401 NOK unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 NOK Invalid input

## Create an inventory Location

Method: ``` POST ``` 

Endpoint: ```/api​/inventorylocation```

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

</details>

<details>
 <summary>Payload</summary>
 
```json
 {
  "active": true,
  "address1": "string",
  "address2": "string",
  "admin_graphql_api_id": "string",
  "city": "string",
  "country": "string",
  "country_code": "string",
  "country_name": "string",
  "created_at": "2022-06-22T13:35:40.215Z",
  "id": "string",
  "legacy": true,
  "localized_country_name": "string",
  "localized_province_name": "string",
  "name": "string",
  "phone": "string",
  "province": "string",
  "province_code": "string",
  "updated_at": "2022-06-22T13:35:40.215Z",
  "zip": "string"
}     
 ```
 
</details>

<details>
 <summary>Response - 200 (OK)</summary>

```json
 {
  "active": true,
  "address1": "string",
  "address2": "string",
  "admin_graphql_api_id": "string",
  "city": "string",
  "country": "string",
  "country_code": "string",
  "country_name": "string",
  "created_at": "2022-06-22T13:35:40.215Z",
  "id": "string",
  "legacy": true,
  "localized_country_name": "string",
  "localized_province_name": "string",
  "name": "string",
  "phone": "string",
  "province": "string",
  "province_code": "string",
  "updated_at": "2022-06-22T13:35:40.215Z",
  "zip": "string"
}     
 ```
 
</details> 

<details>
 <summary>Response - 201 (ok inventory location created)</summary>
 
 ```json
 {
  "active": true,
  "address1": "string",
  "address2": "string",
  "admin_graphql_api_id": "string",
  "city": "string",
  "country": "string",
  "country_code": "string",
  "country_name": "string",
  "created_at": "2022-06-22T13:35:40.215Z",
  "id": "string",
  "legacy": true,
  "localized_country_name": "string",
  "localized_province_name": "string",
  "name": "string",
  "phone": "string",
  "province": "string",
  "province_code": "string",
  "updated_at": "2022-06-22T13:35:40.215Z",
  "zip": "string"
}
 ```
 </details> 

<details>
 <summary>Response - 400 (NOK Invalid status value)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 401 (NOK Unauthorized)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 



<details>
 <summary>Response - 405 (NOK Invalid input)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>
 
HTTP Status Code: 
- 200 OK
- 201 OK inventory location created
- 400 NOK bad request
- 401 NOK Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 NOK Invalid input

## Updated an inventory level

Method: ``` PUT ``` 

Endpoint: ```​/api​/inventorylocation```

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

</details>

<details>
 <summary>Payload</summary>
 
```json
{
  "active": true,
  "address1": "string",
  "address2": "string",
  "admin_graphql_api_id": "string",
  "city": "string",
  "country": "string",
  "country_code": "string",
  "country_name": "string",
  "created_at": "2022-06-22T13:39:39.407Z",
  "id": "string",
  "legacy": true,
  "localized_country_name": "string",
  "localized_province_name": "string",
  "name": "string",
  "phone": "string",
  "province": "string",
  "province_code": "string",
  "updated_at": "2022-06-22T13:39:39.407Z",
  "zip": "string"
}      
 ```
 
</details>

<details>
 <summary>Response - 200 (OK Location item created)</summary>

```json
 {
  "active": true,
  "address1": "string",
  "address2": "string",
  "admin_graphql_api_id": "string",
  "city": "string",
  "country": "string",
  "country_code": "string",
  "country_name": "string",
  "created_at": "2022-06-22T13:39:39.382Z",
  "id": "string",
  "legacy": true,
  "localized_country_name": "string",
  "localized_province_name": "string",
  "name": "string",
  "phone": "string",
  "province": "string",
  "province_code": "string",
  "updated_at": "2022-06-22T13:39:39.382Z",
  "zip": "string"
}     
 ```
 
</details> 


<details>
 <summary>Response - 400 (NOK bad request)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 401 (NOK unauthorized)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 405 (Invalid input)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>
 
HTTP Status Code: 
- 200 OK Location item created
- 201 created
- 400 NOK Invalid status value
- 401 NOK Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 NOK Invalid input

## Find Customer by ID

Method: ``` GET ``` 

Endpoint: ```​/api​/inventorylocation​/{id}```

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

</details>

<details>
 <summary>Path Variable</summary>
 
	- {id}
 
</details>

<details>
 <summary>Response - 200 (OK)</summary>

```json
 {
  "active": true,
  "address1": "string",
  "address2": "string",
  "admin_graphql_api_id": "string",
  "city": "string",
  "country": "string",
  "country_code": "string",
  "country_name": "string",
  "created_at": "2022-06-22T13:44:35.975Z",
  "id": "string",
  "legacy": true,
  "localized_country_name": "string",
  "localized_province_name": "string",
  "name": "string",
  "phone": "string",
  "province": "string",
  "province_code": "string",
  "updated_at": "2022-06-22T13:44:35.975Z",
  "zip": "string"
}     
 ```
 
</details> 

<details>
 <summary>Response - 400 (Bad request unable to create Location)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 401 (Unauthorized)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 


<details>
 <summary>Response - 404 (Location with provided id not found)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>

<details>
 <summary>Response - 405 (Invalid input)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>
 
HTTP Status Code: 
- 200 OK Found location
- 400 Bad request unable to create Location
- 401 Unauthorized
- 403 Forbidden 
- 404 Location with provided id not found
- 405 Invalid input

## Create multiple inventory Locations

Method: ``` POST ``` 

Endpoint: ```/api​/inventorylocations```

OAuth 2.0 Scopes: `Tenant authentication`

<details>
 <summary>Request Headers</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |

</details>

<details>
 <summary>Payload</summary>
 
```json
 [
  {
    "active": true,
    "address1": "string",
    "address2": "string",
    "admin_graphql_api_id": "string",
    "city": "string",
    "country": "string",
    "country_code": "string",
    "country_name": "string",
    "created_at": "2022-06-22T13:47:30.858Z",
    "id": "string",
    "legacy": true,
    "localized_country_name": "string",
    "localized_province_name": "string",
    "name": "string",
    "phone": "string",
    "province": "string",
    "province_code": "string",
    "updated_at": "2022-06-22T13:47:30.858Z",
    "zip": "string"
  }
]     
 ```
 
</details>

<details>
 <summary>Response - 200 (OK)</summary>

```json
[
  {
    "active": true,
    "address1": "string",
    "address2": "string",
    "admin_graphql_api_id": "string",
    "city": "string",
    "country": "string",
    "country_code": "string",
    "country_name": "string",
    "created_at": "2022-06-22T13:47:30.858Z",
    "id": "string",
    "legacy": true,
    "localized_country_name": "string",
    "localized_province_name": "string",
    "name": "string",
    "phone": "string",
    "province": "string",
    "province_code": "string",
    "updated_at": "2022-06-22T13:47:30.858Z",
    "zip": "string"
  }
]      
 ```
 
</details> 

<details>
 <summary>Response - 201 (OK inventory location created)</summary>
 
 ```json
 [
  {
    "active": true,
    "address1": "string",
    "address2": "string",
    "admin_graphql_api_id": "string",
    "city": "string",
    "country": "string",
    "country_code": "string",
    "country_name": "string",
    "created_at": "2022-06-22T13:47:30.858Z",
    "id": "string",
    "legacy": true,
    "localized_country_name": "string",
    "localized_province_name": "string",
    "name": "string",
    "phone": "string",
    "province": "string",
    "province_code": "string",
    "updated_at": "2022-06-22T13:47:30.858Z",
    "zip": "string"
  }
]
 ```
 </details> 

<details>
 <summary>Response - 400 (NOK bad request)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 

<details>
 <summary>Response - 401 (NOK unauthorized)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details> 


<details>
 <summary>Response - 405 (NOK Invalid input)</summary>
 
 ```json
 {
  "error": "string",
  "message": "string",
  "path": "string",
  "status": 0,
  "timestamp": "2022-06-22T09:29:16.269Z"
}
 ```
 
</details>
 
HTTP Status Code: 
- 200 OK
- 201 OK inventory location created
- 400 NOK Invalid status value
- 401 NOK Unauthorized
- 403 Forbidden 
- 404 Not Found
- 405 NOK Invalid input


***
[Back to Shopify connector](../ShopifyConnector.md)

[Back to Index](index.md)