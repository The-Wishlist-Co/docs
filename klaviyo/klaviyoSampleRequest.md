[Back to Klaviyo Integration](/klaviyoIntegration.md)

## Example (application/json)
```json
{
    "data": {
        "type": "event",
        "attributes": {
            "metric": {
                "name": "VariantPriceDrop",
                "service": "api"
            },
            "properties": {
                "Items": [
                    {
                        "wishlist_name": "Test wishlist for Klaviyo Templates",
                        "addedFromCart": false,
                        "purchased": false,
                        "wishlistItem_productId": "2e8ecc35-8919-4345-828d-8a2b0bd30b24",
                        "ProductID": "ccb5c56c-4cfe-4980-a33d-f75175e565a2"
                    }
                ]
            },
            "profile": {
                "first_name": "Ronald ",
                "last_name": "Royid",
                "email": "ronaldroyid1998@gmail.com",
                "phone_number": "623362386238",
                "organization": "TWC",
                "location": {}
            }
        }
    }
}


```
[Schema](klaviyoPayloadSchema.md#klaviyo-payload-schema)

[Back to Klaviyo Integration](/klaviyoIntegration.md)

