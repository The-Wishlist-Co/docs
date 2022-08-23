[Back to Price Drop Messages](/platformgeneratedevents.md#price-drop)

## Example (application/json)
```json
{
    "event":
    {
        "type": "VariantPriceDrop"
    },
    "customer":
    {
        "id": "ff4d7ebc-f51c-4406-8806-34d478addc11",
        "customer_ref": "CUST00071",
        "firstName": "Vamika3",
        "lastName": "J",
        "customer_state": "enabled",
        "accepts_marketing": true,
        "verified_email": true,
        "email": "manu1@customerportal.com",
        "active": true,
        "deleted": false,
        "tenant_id": "sunils_electronics",
        "dob": "1985-10-25T00:00:00.000Z",
        "accepts_marketing_updated_at": "date"
    },
    "products":
    [
        {
            "variant_options": "[]",
            "wishlist":
            {
                "id": "wishlistUID",
                "ref": "wishlistReference",
                "itemId": "wishlist item UID",
                "itemRef": "wishlist item Ref"
            },
            "digital_product": 0,
            "productRef": "PRD01011-037",
            "status": "APPROVED",
            "condition": "\"New\"",
            "baseProductRef": "PRD01011",
            "mobile_link": "https://www.bigw.com.au/product/brilliant-basics-boys-skeleton-pyjama-set-black/p/1193835-black/",
            "gtin": "VAR01",
            "availability": "available",
            "additional_image_link": "string",
            "stock":
            {
                "locationId": "locationUID",
                "locationRef": "Sydney",
                "stockLevel": "5"
            },
            "variantValues":
            {
                "color": "blue",
                "size": "xl"
            },
            "baseProduct":
            {
                "tenant_id": "sunils_electronics",
                "color": "black",
                "inventory_tracking": "none",
                "link": "https://www.bigw.com.au/product/brilliant-basics-boys-skeleton-pyjama-set-black/p/1193835-black/",
                "description": "Thisisaproducttestforsureshshopenvtestt",
                "title": "InfantSummercloth",
                "expiration_date": "2021-11-13T21:56:06.341Z",
                "condition": "\"New\"",
                "deleted": 0,
                "variance": "[\"color\",\"size\"]",
                "productRef": "PRD01011",
                "variants_available": 1,
                "disabled": 0,
                "mobile_link": "https://www.bigw.com.au/product/brilliant-basics-boys-skeleton-pyjama-set-black/p/1193835-black/",
                "digital_product": 0,
                "id": "a83034ca-2675-49f3-86cf-bb4f3dd26a58",
                "status": "APPROVED"
            },
            "deleted": 0,
            "baseProductId": "a83034ca-2675-49f3-86cf-bb4f3dd26a58",
            "tenant_id": "sunils_electronics",
            "disabled": 0,
            "expiration_date": "2021-11-13T21:56:06.341Z",
            "link": "https://www.bigw.com.au/product/brilliant-basics-boys-skeleton-pyjama-set-black/p/1193835-black/",
            "description": "thisisanawesomeproduct",
            "id": "3390f456-c215-49eb-8e73-170d45634061",
            "color": "red",
            "title": "BrilliantBasicsBoysSkeletonPyjamaSet-Black"
        },
    ]
}

```
[Schema](priceDropEventPayloadSchema.md#price-drop-payload-schema)

[Back to platform generated messages](/platformgeneratedevents.md#price-drop)


