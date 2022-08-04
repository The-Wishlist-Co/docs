[Back to Emarsys Integration](/emarsysIntegration.md)

## Emarsys Payload Schema  

- **`key_id`** - ` string or integer` - Identifies the contact by their id, uid, or the name/integer id of a custom field, such as email. When id or uid is used as identifier, provide value in this parameter and specify the the actual id or uid in the external_id parameter. - `required`

- **`events`** - `array[`object`]` - The update event(s) in the batch.

  - **`external_id`** - string or integer - The external identifier of the field specified in the key_id parameter. Tip: The customer email is set as external Id. - `required`

  - **`trigger_id`** - `string` - The unique identifier of the wishlist update event. This field is used for deduplication, so if an event is sent multiple times with the same trigger_id, only the first one will be processed. If these IDs differ or are missing, the triggers are considered different, and all of them will be processed. - `optional`

  - **`event_time`** - `string` - The time when the update event happened in UTC using the ISO 8601 format. In Interactions programs the expiration of the event is calculated based on this value. - `required`

- **`wishlist_content`** - `array[`object`]` - List of the items present in the wishlist after the wishlist update happened. It can be empty. - `required`


  - **`item_id`** - `string` - The unique identifier of the wishlist item. Two items under wishlist_content cannot have the same item_id. The value entered here is case-sensitive. - `required`


  - **`quantity`** - `integer` - The quantity of the item. It must be a positive integer. If it is missing, "1" will be used. - `optional`

- **`event_attributes`** - `object` - Additional custom attributes to the event. Any field with any type of value can be provided. - `optional`

    - **`branch_name`**  - `optional`
    - **`branch_id`** - `optional`
    - **`staff_name`** - `optional`
    - **`staff_id`** - `optional`
  

[Sample (application/json)](emarsysSampleRequest.md#example-applicationjson)

[Back to Emarsys Integration](/emarsysIntegration.md)

    

