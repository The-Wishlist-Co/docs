
[Back to Home](index.md#welcome-to-the-wishlist)

# **Event Collector API**

When an API fails with HTTP 503, 502, customer must retry. If the API fails after reasonable number of times, a fault should be reported into event collector.

### Index

***

- [**Event Collector API**](#event-collector-api)
    <!-- - [Index](#index) -->
  - [**Representations**](#representations)
    - [Order](#order)
  - [**REST Endpoints**](#rest-endpoints)
    - [**Events  Resource**](#events--resource)
      - [Create Event](#create-event)
      - [Find Events](#find-events)
  



## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.

### Order
<!-- <details> -->
<!-- <summary>Expand for details</summary> -->

`entity_id` - string - the id of the entity.

`entity_name` - string- the name of the entity.

`base64_encoded_fault_json` - string.

`base64_encoded_payload_json` - string- base64 encoded payload json.

`additionalProp1` - string- key attribute values like correlationId

`additionalProp2` - string- key attribute values like reference id

`additionalProp3` - string-.key attribute value like time stamp- the time error occurred

`operation` - string- operation type like BULK_CREATE or BULK_UPDATE or CREATE or DELETE or READ or UPDATE.

`event_source` - [ CUSTOMER, INVENTORY_LEVEL, INVENTORY_LOCATION, ORDER, PRICE, PRODUCT, VARIANT_PRODUCT, WISHLIST ]

`id` - unique id of the event.

`event_type` - string - type of event like FAULT


<!-- </details> -->


## **REST Endpoints**

## **Events  Resource**

## Create Event
For the creation of a new Event resource with unique id.

Method: ``` POST ``` 

Endpoint: ```​​​/api/v1/events```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request : 
```json 
{
  "entity_id": "string",
  "event_payload": {
    "base64_encoded_payload_json": "ewoiaWQiOiIxMiIsCiJyZWZlcmVuY2UiOiIxMjEyMyIKfQ==",
    "key_attributes": {
      "correlationId": "123123123-123123-123123123",
      "referenceId": "referenceId",
      "timestamp": "time at error occured",
      "additionalKey1": "value1",
      "additionalKey2": "value2",
      "additionalKeyN": "valueN"
    },
    "operation": "BULK_CREATE or BULK_UPDATE or CREATE or DELETE or READ or UPDATE",
    "base64_encoded_fault_json": "eyJpZCI6IjEyXCJ9"
  },
  "event_source": "APPLICATION",
  "event_type": "FAULT"
}'
```

<summary>Response - 201 (Created)</summary>

``` json
{
  "entity_id": "string",
  "entity_name": "string",
  "event_payload": {
    "base64_encoded_fault_json": "string",
    "base64_encoded_payload_json": "string",
    "entity_id": "string",
    "key_attributes": {
      "additionalProp1": "string",
      "additionalProp2": "string",
      "additionalProp3": "string"
    },
    "operation": "BULK_CREATE"
  },
  "event_source": "APPLICATION",
  "event_type": "ENTITY_EVENT",
  "id": "string"
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

## Find Events
To find event by id. Id is passed as a path param.

Method: ``` GET ``` 

Endpoint: ```​/api/v1/events/{eventId}```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request Parameters: `eventId  : id`

 <summary>Response - 200 (OK)</summary>

```json
{
  "entity_id": "string",
  "entity_name": "string",
  "event_payload": {
    "base64_encoded_fault_json": "string",
    "base64_encoded_payload_json": "string",
    "entity_id": "string",
    "key_attributes": {
      "additionalProp1": "string",
      "additionalProp2": "string",
      "additionalProp3": "string"
    },
    "operation": "BULK_CREATE"
  },
  "event_source": "APPLICATION",
  "event_type": "ENTITY_EVENT",
  "id": "string"
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


***
[Back to Top](#event-collector-api)

[Back to Home](index.md#welcome-to-the-wishlist)