# **Welcome to The Wishlist**


## **Wishlist HTTP Rest API Documentation**

**The wishlist** contains an wide array of api'sto meet all customer demands for the fluid evperieance that they are looking for. It employs automation to attain great results with minimum intervention or assistance.
For more detailed informaation, check out the collection and follow the service documentations.


### Api Collection Index

- [Customer Service API](customersvcApi.md)
  
  The Customer Service API stores information about a shop's customers, it also holds information on the status of a customer's account. You can create, retrieve, update, and delete customers using the Customer Service api.
  
    - [**Representations**](customersvcApi.md#representations)
    - [**REST Endpoints**](customersvcApi.md#rest-endpoints)
      - [Create a Customer](customersvcApi.md#create-a-customer)
      - [Upload Customers](customersvcApi.md#upload-customers)
      - [Validate Customer Input](customersvcApi.md#validate-customer-input)
      - [Update a Customer](customersvcApi.md#update-a-customer)
      - [Add address to Existing Customer](customersvcApi.md#add-address-to-existing-customer)
      - [Find Customer by Id](customersvcApi.md#find-customer-by-id)
      - [Find Customer by Ref](customersvcApi.md#find-customer-by-ref)
      - [Look up Customers by email/mobile/phone/firstName/lastName](customersvcApi.md#look-up-customers-by-emailmobilephonefirstnamelastname)
      - [Delete Customer by ID](customersvcApi.md#delete-customer-by-id)
      - [Delete Customer by Ref](customersvcApi.md#delete-customer-by-ref)



- [Inventory Service API](inventorySvcAPI.md)
  
  An inventory item represents a physical good. It holds essential information about the physical good. You can create, retrieve, update, and delete inventory details such as its location and levels using the Customer Service api.


  - [**Inventory API**](#inventory-api)
    - [**Representations**](#representations)
    - [**REST Endpoints**](#rest-endpoints)
      - [Create an inventory Location](#create-an-inventory-location)
      - [Create multiple inventory Locations](#create-multiple-inventory-locations)
      - [Validate an inventory Location](#validate-an-inventory-location)
      - [Find Inventory Location by id and locationRef](#find-inventory-location-by-id-and-locationref)
      - [Delete Inventory Location](#delete-inventory-location)
      - [Create an inventory level](#create-an-inventory-level)
      - [Create Multiple inventory level](#create-multiple-inventory-level)
      - [Validate inventory level](#validate-inventory-level)
      - [Update an inventory level](#update-an-inventory-level)
      - [Find Inventory level by id and stockRef](#find-inventory-level-by-id-and-stockref)
      - [Find Inventory level for product and location](#find-inventory-level-for-product-and-location)
      - [Find Aggregated inventory level for a product variant](#find-aggregated-inventory-level-for-a-product-variant)


- [Merchant Service API](merchantsSvcAPI.md)
  
  The Merchants resource stores information about a merchant and their stores. You can create, retrieve, update, and delete merchants using the Merchant Service api.

  - [**Merchants API**](#merchants-api)
    <!-- - [Index](#index) -->
  - [**Representations**](#representations)
    - [Register Merchant](#register-merchant)
    - [Update Merchant](#update-merchant)
    - [Deactivate Merchant](#deactivate-merchant)
    - [Find Merchant](#find-merchant)
    - [Create a Plan](#create-a-plan)
    - [Update a Plan](#update-a-plan)
    - [Delete a Plan](#delete-a-plan)
    - [Find Plan](#find-plan)
    - [Find All Plans](#find-all-plans)
    - [Create a Store](#create-a-store)
    - [Update a Store](#update-a-store)
    - [Find a Store](#find-a-store)
    - [Find a Store](#find-a-store-1)
    - [Deactivate Store](#deactivate-store)
    - [Create Subscription plan](#create-subscription-plan)
    - [Update Subscription plan](#update-subscription-plan)
    - [Cancel Subscription plan](#cancel-subscription-plan)
    - [Get Additional Config](#get-additional-config)
    - [Get All Config](#get-all-config)
    - [Get Entity Config](#get-entity-config)
    - [Get Store Tenant Config](#get-store-tenant-config)
    - [Create Additional Config](#create-additional-config)
    - [Update Additional Config](#update-additional-config)
    - [Create App Config Entity Config](#create-app-config-entity-config)
    - [Update App Config Entity Config](#update-app-config-entity-config)
    - [Create Customer Entity Config](#create-customer-entity-config)
    - [Update Customer Entity Config](#update-customer-entity-config)
    - [Create Email Template Entity Config](#create-email-template-entity-config)
    - [Update Email Template Entity Config](#update-email-template-entity-config)
    - [Create Inventory Entity Config](#create-inventory-entity-config)
    - [Update Inventory Entity Config](#update-inventory-entity-config)
    - [Create Location Entity Config](#create-location-entity-config)
    - [Update Location Entity Config](#update-location-entity-config)
    - [Create Order Entity Config](#create-order-entity-config)
    - [Update Order Entity Config](#update-order-entity-config)
    - [Create Price Entity Config](#create-price-entity-config)
    - [Update Price Entity Config](#update-price-entity-config)
    - [Create Product Entity Config](#create-product-entity-config)
    - [Update Product Entity Config](#update-product-entity-config)
    - [Create Store Entity Config](#create-store-entity-config)
    - [Update Store Entity Config](#update-store-entity-config)
    - [Create Wishlist Entity Config](#create-wishlist-entity-config)
    - [Update Wishlist Entity Config](#update-wishlist-entity-config)
    - [Get Notification Config](#get-notification-config)
    - [Create Notification Config](#create-notification-config)
    - [Create BackInStock Notification Settings](#create-backinstock-notification-settings)
    - [Update BackInStock Notification Settings](#update-backinstock-notification-settings)
    - [Delete BackInStock Notification Settings](#delete-backinstock-notification-settings)
    - [Create LowInStock Notification Settings](#create-lowinstock-notification-settings)
    - [Update LowInStock Notification Settings](#update-lowinstock-notification-settings)
    - [Delete LowInStock Notification Settings](#delete-lowinstock-notification-settings)
    - [Create PriceDrop Notification Settings](#create-pricedrop-notification-settings)
    - [Update PriceDrop Notification Settings](#update-pricedrop-notification-settings)
    - [Delete PriceDrop Notification Settings](#delete-pricedrop-notification-settings)
    - [Create ReminderEmail Notification Settings](#create-reminderemail-notification-settings)
    - [Update ReminderEmail Notification Settings](#update-reminderemail-notification-settings)
    - [Delete ReminderEmail Notification Settings](#delete-reminderemail-notification-settings)

  
- [Price Service API](priceSvcAPI.md)
  
  The Price resource stores information about price details of particular product variant. You can create, retrieve, update, and delete prices using the Price Service api.

  - [**Price API**](#price-api)
      <!-- - [Index](#index) -->
    - [**Representations**](#representations)
      - [Create A Price](#create-a-price)
      - [Update A Price](#update-a-price)
      - [Delete A Price](#delete-a-price)
      - [Find Price by id and priceRef](#find-price-by-id-and-priceref)
      - [Validate an price](#validate-an-price)
      - [Find All Prices](#find-all-prices)


- [Product Service API](productsvcAPI.md)

    The Product resource stores information about a product, its variants. You can create, retrieve, update, and delete orders using the Product Service api.


  - [**Product API**](#product-api)
      <!-- - [Index](#index) -->
    - [**Representations**](#representations)
      - [Product](#product)
      - [Product Variant](#product-variant)
    - [**REST Endpoints**](#rest-endpoints)
      - [Create a Product](#create-a-product)
      - [Update a Product](#update-a-product)
      - [Look up Product by gtin/productRef](#look-up-product-by-gtinproductref)
      - [Validate Request](#validate-request)
      - [Validate Product](#validate-product)
      - [Validate Product by Ref](#validate-product-by-ref)
      - [Find Product by ID](#find-product-by-id)
      - [Delete Product by ID](#delete-product-by-id)
      - [Find Product by Ref](#find-product-by-ref)
      - [Delete Product by Ref](#delete-product-by-ref)
      - [Upload Products](#upload-products)
      - [Create a Product Variants](#create-a-product-variants)
      - [Update a Product Variant](#update-a-product-variant)
      - [Validate Product Variant](#validate-product-variant)
      - [Find Product Variant by ID](#find-product-variant-by-id)
      - [Find Product Variant by Ref](#find-product-variant-by-ref)
      - [Delete Product variant by Ref](#delete-product-variant-by-ref)
      - [Find Product variants by productId](#find-product-variants-by-productid)
      - [Find  Product variants by productId](#find--product-variants-by-productid)
      - [Delete Product variants by product Id/variantId](#delete-product-variants-by-product-idvariantid)
      - [Upload Product Variants](#upload-product-variants)

- [Order Service API](ordersSvcApi.md)

    An order is a customer's request to purchase one or more products from a shop. You can create, retrieve, update, and delete Product using the Order Service api.

    - [**Order Svc API**](#order-svc-api)
    <!-- - [Index](#index) -->
    - [**Representations**](#representations)
    - [**REST Endpoints**](#rest-endpoints)
      - [Validate Order Entry](#validate-order-entry)
      - [Create an order](#create-an-order)
      - [Updates an order](#updates-an-order)
      - [FInd an orders](#find-an-orders)
      - [Search orders](#search-orders)
      - [Validate Order](#validate-order)
      - [Search entries for an order](#search-entries-for-an-order)
      - [Create an order entry](#create-an-order-entry)
      - [Update an order entry](#update-an-order-entry)
      - [Search an order entry](#search-an-order-entry)
      - [Delete entry](#delete-entry)


- [Wishlist Service API](wishlistSvcAPI.md)
  
  The Wishlist resource stores information about a customer's wishlist, which includes the list products which the customer wish to buy. You can create, retrieve, update, and delete wishlists using the Wishlist Service api.

  - [**Wishlist API**](#wishlist-api)
    <!-- - [Index](#index) -->
  - [**Representations**](#representations)
    - [Wishlist](#wishlist)
      - [Create a Wishlist](#create-a-wishlist)
      - [Update a Wishlist](#update-a-wishlist)
      - [Delete Wishlist by ID/Ref](#delete-wishlist-by-idref)
      - [Find Wishlist by id/wishlistRef](#find-wishlist-by-idwishlistref)
      - [Find Wishlist by CustomerId](#find-wishlist-by-customerid)
      - [Find Wishlist by CustomerRef](#find-wishlist-by-customerref)
      - [Create a Wishlist Item](#create-a-wishlist-item)
      - [Update a Wishlist Item](#update-a-wishlist-item)
      - [Delete Wishlist Item by wishlist Id and item Id](#delete-wishlist-item-by-wishlist-id-and-item-id)
      - [Find Wishlist Item by WishlistId and Item Id](#find-wishlist-item-by-wishlistid-and-item-id)


- [Impex Service API](impexAPI.md)

    The ImpEx API allows you to interact with all the core api's in the TWC system at a unified REST interface for the seemless interegration of bulk data in to the system. 

  - [**Representations**](impexAPI.md#representations)
  - [**REST Endpoints**](impexAPI.md#rest-endpoints)
    - [Create Batch](impexAPI.md#create-batch)
    - [Change State](impexAPI.md#change-state)
    - [Get Batch](impexAPI.md#get-batch)
    - [Query Batch](impexAPI.md#query-batch)
    - [Create Resources](impexAPI.md#create-resources)
    - [Update State](impexAPI.md#update-state)
    - [Get Resource By Id](impexAPI.md#get-resource-by-id)
    - [Query Resources](impexAPI.md#query-resources)

- [Shopify Connector](ShopifyConnector.md)
  
  Shopify Connector is used data integration from the Shopify system into the TWC system seamlessly.

- [Event Collector](eventcollectorAPI.md)

    The event collector api is employed for enabling various events and campains that pertains to a customer.
    


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


