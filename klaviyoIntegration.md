[Back to Home](index.md#welcome-to-the-wishlist)

# **Klaviyo Integration**

Klaviyo Platform empowers marketers to execute simple, single-channel campaigns, or create sophisticated, cross-channel journeys at scale.

 The Klaviyo platform makes it easy to integrate data, set up messaging across channels, and deploy personalized campaigns at scale. From personalized campaigns to triggering events in real-time, easily deploy marketing automation across every channel.

 The **Klaviyo Integration Lambda** enables the seamless integration of the platforms Trigger a Wishlist Update event with the TWC System for the customers who are subscribed to the event from Klaviyo.

 ***

## Enabling Klaviyo

Enabling the service is done using the TWC [*Event Subscription Resource*](eventcollectorAPI.md#event-subscription-resource) API. Once enabled, all the wishlist interactions flow to Emarsys from the [Customer Interactions](platformgeneratedevents.md#customer-interaction)

## Configuring System Parameters

Various credentials, secrets and URLs related to the Klaviyo Integration are stored securely in the Parameter Store and accessed by the lambda as required.

- klaviyoPrivateKey - Klaviyo provided private key.  

 
  
- KlaviyoUrl: The base URL of klaviyo api's.  



## Configure Authentication for Klaviyo API

Klaviyo API uses private key provided by klaviyo.


## Lambda Implementation

The Wishlist action is received by the Klavio integration lambda from the Simple Queue Service (sqs) registered during the subscription. This event triggers the lambda.



The response body is then utilised to prepare the payload required by the klaviyo system and is set as the request body for klaviyo. The request is then passed through to Klaviyo accompanied by the private key. 

A successful request is represented by the HTTP status code 202.

[Sample Payload](klaviyo/klaviyoSampleRequest.md#example-application.json)

[Payload Schema](klaviyo/klaviyoPayloadSchema.md#klaviyoPayloadSchema.md)


****


[Back to Top](#klaviyo-integration)

[Back to Home](index.md#welcome-to-the-wishlist)



