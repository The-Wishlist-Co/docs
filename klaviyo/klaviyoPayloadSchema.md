[Back to Klaviyo Integration](/klaviyoIntegration.md)

## Klaviyo Payload Schema  

- **`type`** - ` string ` - Identifies the event external parameter. - `required`

- **`attributes`** - `object` - its contain the attributes and attributes contians profile ,metrics and properties. - `required`

  - **`metric`** - `object` - its contains metrics information like  name , and service - `required`

          - **`name`** - `string` - name of the metrics like VariantPriceDrop ,VariantBackStock ,VariantLowStock and Remainder - `required`

          - **`service`** - `string` - by defult its would be API. - `required`

- **`profile`** - `object` - profile of the customer. - `required`


       - **`first_name`** - `string` - First Name of the customer - `required`


       - **`last_name`** - `string` - Last Name of the customer. - `required`

       - **`email`** - `string` - Email of the customer. - `required`

       - **`phone_number`** - `string` -Phane number of the customer. - `required`

       - **`location`** - `Object` - Address of the customer. - `optimal`


- **`properties`** - `object` - Additional custom attributes to the event. Any field with any type of value can be provided. - `required`

- **`Items`** - `[object]` - Array of wist list items. - `required`

    - **`ProductId`**  - `required`
    - **`wishlist_name`** - `optional`
    - **`addedFromCart`** - `optional`
    - **`purchased`** - `optional`
    - **`wishlistItem_productId`** - `optional`
  

[Sample (application/json)](klaviyoSampleRequest.md#example-applicationjson)

[Back to Klaviyo Integration](/klaviyoIntegration.md)

    

