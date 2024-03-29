
[Back to Home](index.md#welcome-to-the-wishlist)

# **Event Collector API**

The event collector API is employed for enabling various events and campaigns that pertain to a customer. Various event suscriptions such as notification services, loyalty services etc can be enabled by the retailer and the information related to these events are also stored here.

### Index

***

- [**Event Collector API**](#event-collector-api)
    - [Index](#index)
  - [**Representations**](#representations)
    - [Event](#event)
    - [Event Subscriptions](#event-subscriptions)
    - [Jobs](#jobs)
  - [**REST Endpoints**](#rest-endpoints)
  - [**Events  Resource**](#events--resource)
  - [Create Event](#create-event)
  - [Find Events](#find-events)
  - [**Event Subscription Resource**](#event-subscription-resource)
  - [Create  Event Subscriptions](#create--event-subscriptions)
  - [Update  Event Subscriptions](#update--event-subscriptions)
  - [Get All Event Subscriptions](#get-all-event-subscriptions)
  - [Get  Event Subscriptions](#get--event-subscriptions)
  - [Deactivate Event Subscriptions](#deactivate-event-subscriptions)
  - [**Jobs API**](#jobs-api)
  - [Create Notification Job](#create-notification-job)
  - [Update Notification Job](#update-notification-job)
  - [Delete  Notification Job](#delete--notification-job)



## **Representations**

All requests and responses are JSON objects.

### Event 

`entity_id` - string - Id of the entity.

`entity_name` - string - Name of the entity.

`event_payload` - Object 

- `base64_encoded_fault_json` - string - encrypted fault json. 

- `base64_encoded_payload_json` - string - encrypted fault json. 

- `entity_id` - string -
-   `key_attributes` - Object
    -  `additionalProp1` - string - customer defined additional property.
  
    -  `additionalProp2` - string - customer defined additional property.
  
    -  `additionalProp3` - string - customer defined additional property.

    
  - `operation` - enum - to chose between various avaliable entity operations provided.
    - CREATE
    - BULK_UPDATE
    - BULK_CREATE
    - READ
    - DELETE
    - UPDATE


`event_source` - - enum - to chose between various avaliable event sources provided.
  - SYSTEM
  - CONNECTOR
  - APPLICATION
  - SERVERLESS

`event_type` - enum - to chose between various avaliable entity types provided.
 - ORDER
 - ORDER_ENTRY
 - CUSTOMER
 - ADDRESS
 - PRODUCT
 - VARIANT_PRODUCT
 - INVENTORY_LEVEL
 - INVENTORY_LOCATION
 - INVENTORY_ITEM
 - STORE
 - MERCHANT
 - WISHLIST
 - WISHLIST_ITEM
 - OTHER
 - EVENT

`id` - string - unique id of the event.

### Event Subscriptions
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

### Jobs

`deleted` - boolean - To mark current job as deleted.

`id` - unique id of the event.

`is_active` - boolean - To mark current job template as active or not.

`is_scheduled` - boolean - To mark if the current job is scheduled for notifications.

`job_parameters` - object - contains various job parameters.

  - `campaign_id` - string - Customer defined campain id of the job. Comes under job parameters.

  -`utm_medium` - customer defined utm medium. Comes under job parameters"

`notification` - enum - To select different type of avaliable notification types.
- REMINDER
- PRICE_DROP
- LOW_STOCK
- BACK_IN_STOCK;

`number_of_items_in_email` - integer - Number of items in email, set -1 to send the entire wishlist.

`schedule` - string - as per cron expression",
  any cron schedule with frequency.

`scheduleExpression` - string -- string - as per cron expression", any cron schedule with frequency expressed as a string. Optional.
  
`template_id` - string - Template ID from sendgrid


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


## **Event Subscription Resource**

## Create  Event Subscriptions
For the creation of a new EventSubscriptions resource with unique id, and active status.

Method: ``` POST ``` 

Endpoint: ```​​​/api/v1/event-subscription```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

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

 <summary>Response - 201 (Created)</summary>

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
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Update  Event Subscriptions
For updating an existing EventSubscriptions resource with unique id.

Method: ``` PUT ``` 

Endpoint: ```​​​/api/v1/event-subscription```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

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

<summary>Response - 201 (Created)</summary> 

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
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Get All Event Subscriptions
TO find all active event Subscription events.

Method: ``` GET ``` 

Endpoint: ```​​​/api/v1/event-subscription```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request Parameters : no parameters

 <summary>Response - 200 (OK)</summary> 

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
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Get  Event Subscriptions
TO find an active event Subscription event with id.

Method: ``` GET ``` 

Endpoint: ```​​​/api/v1/event-subscription/{Id}```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request Parameters: `id  :event id`

 <summary>Response - 200 (OK)</summary> 

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
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```


## Deactivate Event Subscriptions
TO find an active event Subscription event with id.

Method: ``` PUT ``` 

Endpoint: ```​​​​/api​/v1​/event-subscription​/{Id}​/deactivate```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request Parameters: `id  :event id`

 <summary>Response - 200 (OK)</summary> 
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
- 400 Bad request 
- 401 Unauthorised
- 403 Forbidden 
- 404 Not Found
- 405 Invalid input
```

## **Jobs API**

## Create Notification Job
For the creation of a new Job notification. A Job resource with unique id,active status, notification type, cron schedule etc.

Method: ``` POST ``` 

Endpoint: ```​​​/api/v1/jobs```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request : 
```json
{
  "deleted": true,
  "id": "string",
  "is_active": true,
  "is_scheduled": true,
  "job_parameters": {
    "campaign_id": "string",
    "utm_medium": "string"
  },
  "notification": "BACK_IN_STOCK",
  "number_of_items_in_email": 0,
  "schedule": "string",
  "scheduleExpression": "string",
  "template_id": "string"
}
```

<summary>Response - 201 (Created)</summary> 

```json
{
  "deleted": true,
  "id": "string",
  "is_active": true,
  "is_scheduled": true,
  "job_parameters": {
    "campaign_id": "string",
    "utm_medium": "string"
  },
  "notification": "BACK_IN_STOCK",
  "number_of_items_in_email": 0,
  "schedule": "string",
  "scheduleExpression": "string",
  "template_id": "string"
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


## Update Notification Job
For Updating an existing job by adding parameters or changing existing ones. Job id cannot be updated.

Method: ``` PUT ``` 

Endpoint: ```​​​/api/v1/jobs/{{jobId}}```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request : 

 `PATH parameter -   "JobId" : id`

```json
{
  "deleted": true,
  "is_active": true,
  "is_scheduled": true,
  "job_parameters": {
    "campaign_id": "string",
    "utm_medium": "string"
  },
  "notification": "BACK_IN_STOCK",
  "number_of_items_in_email": 0,
  "schedule": "string",
  "scheduleExpression": "string",
  "template_id": "string"
}
```
<summary>Response - 200 (Ok)</summary> 

```json
{
  "deleted": true,
  "id": "string",
  "is_active": true,
  "is_scheduled": true,
  "job_parameters": {
    "campaign_id": "string",
    "utm_medium": "string"
  },
  "notification": "BACK_IN_STOCK",
  "number_of_items_in_email": 0,
  "schedule": "string",
  "scheduleExpression": "string",
  "template_id": "string"
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


<!-- ## Activate Or Deactivate Job
For only ypdatind is_active status of the job easily with jobId.

Method: ``` PUT ``` 

Endpoint: ```​​​/api/v1/jobs/active/{{jobID}}```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request Parameters:

 `PATH parameter -   "JobId" : id`

 `Request Param - "is_active": true/false`

 <summary>Response - 200 (Ok)</summary> 


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

## Delete  Notification Job
For the deletion of a Job. Delete status will be marked as true.

Method: ``` POST ``` 

Endpoint: ```​​​/api/v1/jobs/{{jobId}}```

OAuth 2.0 Scopes: `Tenant authentication` - [authentication](authenticationsvcApi.md)

 <summary>Request Headers :</summary>

| Key           | Value            |
|---------------|------------------|
| Content-Type  | application/json |
| X-TWC-Tenant  | {Tenant Name}    |


Request Parameters:

 `PATH parameter -   "JobId" : id`

 <summary>Response - 204 (No Content)</summary> 


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