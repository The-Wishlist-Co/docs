[Back to Platform Generated Events](/platformgeneratedevents.md#price-drop)

## Price Drop Payload Schema  



- **`event`** - `array[`object`]` - The update event(s) in the batch.

- **`customer`** - 'object' - customer details

          - **`id`** - `string` - customer id. 

          - **`customer_ref`** - `string` - 

          - **`firstName`** - `string` - first name of the customer


          - **`lastName`** - `string` - lastname name of the cusyomer


           - **`customer_state`** - 'string' - customer active or not

           - **`accepts_marketing`**            - `boolen` 

           - **`verified_email`**               - `boolean`
           - **`active`**                       - `string`
           - **`deleted`**                      - `boolean`
           - **`tenant_id`**                    - `string`
           - **`dob`**                          - `date`
           - **`accepts_marketing_updated_at`** - 'date'

- **`product`**  - `Array`['object'] - product details
      
           - **'variant_options'**              - 'array'
- **`wishlist`**                                - 'Object'
           - **`wishlistid`**                   - 'string' - wishlist id
           - **`ref`**                          - 'string' - wishlist ref
           - **`itemId`**                       - 'string' - wishlist item id
           - **`itemRef`**                      - 'string' - wishlist item ref'
        - **`digital_product`**                  -  'number'- 
        - **`productRef`**                       - 'string' -
        - **`status`**                           - 'string` - 
        - **`condition`**                        - 'string` - product condition
        - **`baseProductRef`**                   - 'string` - base product ref
        - **`mobile_link`**                      - 'string` - mobile link
        - **`gtin`**                             - 'string` - bar code
        - **`availability`**                     - 'string` - availblity of product
        - **`additional_image_link`**              -'string' - image link
  - **`stock`**                                    -'Object'  
        - **`locationId`**                      -'string' - location       
        - **`locationRef`**                     -'string' - location ref
        - **`stockLevel`**                      -'string` - stock level 
  - **`variantValues`**                         -'Object'
            
        - **`color`**                          -'string' - product level
        - **`size`**                           -'string' - size
            
        - **`baseProduct`**                    -'Object'
            
            - **`tenant_id`**                  -'string'
            - **`color`**                      -'string'
            - **`inventory_tracking`**         -'string'
            - **`link`**                      -'string`                     
            - **`description`**:               -'string'
            - **`title`**                      -'string',
            - **`expiration_date`**            - 'date',
            - **`condition`**                  - 'string',
            - **`deleted`**                    - 'boolean',
            - **`variance`**                   - 'array',
            - **`productRef`**                 - 'string'
            - **`variants_available`**         - 'number',
            - **`disabled`**                   - 'boolean',
            - **`mobile_link`**                - 'string',
            - **`digital_product`**            - 'string',
            - **`id`**                         - 'string', 
            - **`status`**                     - 'string`,
            - **`deleted`**                    - 'boolean',
            - **`baseProductId`**              - 'string',
            - **`tenant_id`**                  - 'string',
            - **`disabled`**                   - 'boolean'
            - **`expiration_date`**            - 'date`,
            - **`link`**                       - 'string',
            - **`description`**                - 'string',
            - **`id`**                         - 'string',         
            - **`color`**:                     - 'string',
            - **`title`**:                     - 'string'
        }
[Sample (application/json)](priceDropEventNotificationMessage.md#example-applicationjson)

[Back to price drop ](/platformgeneratedevents.md)

    

