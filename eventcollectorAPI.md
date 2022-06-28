# **Event Collector API**

The event collector api is employed for enabling various events and campains that pertains to a customer. Various event suscriptions such as notification services, loyality services etc can be enabled by the customer and the information related to these events are also stored here.

### Index

***

- [**Event Collector API**](#event-collector-api)
    <!-- - [Index](#index) -->
  - [**Representations**](#representations)
    - [Order](#order)
  - [**REST Endpoints**](#rest-endpoints)
    - [Create Event](#create-event)
    - [Find Events](#find-events)
    - [Create  Event Subscriptions](#create--event-subscriptions)
    - [Update  Event Subscriptions](#update--event-subscriptions)
    - [Get All Event Subscriptions](#get-all-event-subscriptions)
    - [Get  Event Subscriptions](#get--event-subscriptions)
    - [Deactivate Event Subscriptions](#deactivate-event-subscriptions)
  



## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.

### Order
<!-- <details> -->
<!-- <summary>Expand for details</summary> -->

`active` - boolean - true for active event Subscription.

`destination` - The SQS or SNS event Subscribed.

`sqs` - AWS simple que service.

`accessKey` - sqs account accessKey.

`accessSecret` - sqs account accessSecret.

`queueUrl` - sqs queue Url of the event. 

`region` - AWS region in which sqs event exists.

`type` - Event type .i.e SQS, SNS etc.

`entityType` - [ CUSTOMER, INVENTORY_LEVEL, INVENTORY_LOCATION, ORDER, PRICE, PRODUCT, VARIANT_PRODUCT, WISHLIST ]

`id` - unique id of the event.

`subscribeCreate` - boolean - For creation.

`subscribeChange` - boolean - For changes in active Subscription.

`subscribeDelete` - boolean - To mark current Subscription as deleted.


<!-- </details> -->


## **REST Endpoints**

- ## **Events  Resource**

## Create Event
For the creation of a new Event resource with unique id.

Method: ``` POST ``` 

Endpoint: ```​​/api​/api/v1/events```

OAuth 2.0 Scopes: `Tenant authentication`

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request : 
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

Response : 
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
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```

## Find Events
To find event by id. Id is passed as a path param.

Method: ``` GET ``` 

Endpoint: ```​/api/v1/events/{eventId}```

OAuth 2.0 Scopes: `Tenant authentication`

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request Parameters: `eventId  : id`

Response : 
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
- 401 Unauthorized
- 403 Forbidden 
- 404 Not Found
```



- ## **Event Subscription Resource**

## Create  Event Subscriptions
For the creation of a new EventSubscriptions resource with unique id, and active status.

Method: ``` POST ``` 

Endpoint: ```​​​/api/v1/event-subscription```

OAuth 2.0 Scopes: `Tenant authentication`

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request : 
```json
{
  "active": true,
  "destination": {
    "sqs": {
      "accessKey": "string",
      "accessSecret": "string",
      "queueUrl": "string",
      "region": "string"
    },
    "type": "SNS"
  },
  "entityType": "CUSTOMER",
  "id": "string",
  "subscribeChange": true,
  "subscribeCreate": true,
  "subscribeDelete": true
}
```

Response : 
```json
{
  "active": true,
  "destination": {
    "sqs": {
      "accessKey": "string",
      "accessSecret": "string",
      "queueUrl": "string",
      "region": "string"
    },
    "type": "SNS"
  },
  "entityType": "CUSTOMER",
  "id": "string",
  "subscribeChange": true,
  "subscribeCreate": true,
  "subscribeDelete": true
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
```

## Update  Event Subscriptions
For the updation of an existing EventSubscriptions resource with unique id.

Method: ``` PUT ``` 

Endpoint: ```​​​/api/v1/event-subscription```

OAuth 2.0 Scopes: `Tenant authentication`

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request : 
```json
{
  "active": true,
  "destination": {
    "sqs": {
      "accessKey": "string",
      "accessSecret": "string",
      "queueUrl": "string",
      "region": "string"
    },
    "type": "SNS"
  },
  "entityType": "CUSTOMER",
  "id": "string",
  "subscribeChange": true,
  "subscribeCreate": true,
  "subscribeDelete": true
}
```
Response : 

```json
{
  "active": true,
  "destination": {
    "sqs": {
      "accessKey": "string",
      "accessSecret": "string",
      "queueUrl": "string",
      "region": "string"
    },
    "type": "SNS"
  },
  "entityType": "CUSTOMER",
  "id": "string",
  "subscribeChange": true,
  "subscribeCreate": true,
  "subscribeDelete": true
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
```

## Get All Event Subscriptions
TO find all active event Subscription events.

Method: ``` GET ``` 

Endpoint: ```​​​/api/v1/event-subscription```

OAuth 2.0 Scopes: `Tenant authentication`

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request Parameters : no parameters

Response : 

```json
[
  {
    "active": true,
    "destination": {
      "sqs": {
        "accessKey": "string",
        "accessSecret": "string",
        "queueUrl": "string",
        "region": "string"
      },
      "type": "SNS"
    },
    "entityType": "CUSTOMER",
    "id": "string",
    "subscribeChange": true,
    "subscribeCreate": true,
    "subscribeDelete": true
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
```

## Get  Event Subscriptions
TO find an active event Subscription event with id.

Method: ``` GET ``` 

Endpoint: ```​​​/api/v1/event-subscription/{Id}```

OAuth 2.0 Scopes: `Tenant authentication`

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request Parameters: `id  :event id`

Response : 

```json
{
  "active": true,
  "destination": {
    "sqs": {
      "accessKey": "string",
      "accessSecret": "string",
      "queueUrl": "string",
      "region": "string"
    },
    "type": "SNS"
  },
  "entityType": "CUSTOMER",
  "id": "string",
  "subscribeChange": true,
  "subscribeCreate": true,
  "subscribeDelete": true
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
```

## Deactivate Event Subscriptions
TO find an active event Subscription event with id.

Method: ``` PUT ``` 

Endpoint: ```​​​​/api​/v1​/event-subscription​/{Id}​/deactivate```

OAuth 2.0 Scopes: `Tenant authentication`

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request Parameters: `id  :event id`

Response : 
```json
{
  "body": {},
  "statusCode": "ACCEPTED",
  "statusCodeValue": 0
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
```

***
[Back to Index](index.md)