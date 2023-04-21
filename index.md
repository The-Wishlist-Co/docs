# **Welcome to The Wishlist**


## **The Wishlist HTTP Rest API Documentation**

**The Wishlist**  is a microservices-based, API enabled engine that empowers retailers to understand and manage lists of products that their customers would like to purchase, and automates notifications to those customers when those items are low in stock, back in stock, or available at a discount (to name a few).  The Wishlist acts as a data hub that integrates key retailer systems such as ecommerce, Point of Sale, marketing platform, CDP, etc.  

The Wishlist's API's provide a comprehensive range of integration options for our data entities including Wishlists, Customers, Products, Inventory, and Orders. 

For more detailed informaation, check out the collection and follow the service documentation.


### Api Collection Index


- [**Authentication API**](authenticationsvcApi.md#authentication-api)	

	The Authentication Service generates the bearer token, which is used in the request header to interact with the application.
	
	- [*Representations*](authenticationsvcApi.md#representations)

	- [*REST Endpoints*](authenticationsvcApi.md#rest-endpoints)

		- [Generate Token](authenticationsvcApi.md#generate-token)
  
		

- [**Customer Service API**](customersvcApi.md#customer-api)
  
  The Customer Service enables the management of information about a store's customers. You can create, retrieve, update, and delete customers using the Customer Service API.
  
    - [*Representations*](customersvcApi.md#representations)
  
    - [*REST Endpoints*](customersvcApi.md#rest-endpoints)
  


- [**Inventory Service API**](inventorySvcAPI.md#inventory-api)
  
  The Inventory Service enables the management of information about physical goods. You can create, retrieve, update, and delete inventory details such as location and stock levels using the Inventory Service API.


    - [*Representations*](inventorySvcAPI.md#representations)
    
    - [*REST Endpoints*](inventorySvcAPI.md#rest-endpoints)
    
      - [*Location Resource*](inventorySvcAPI.md#location-resource)

      - [*Stock Level Resource*](inventorySvcAPI.md#stock-level-resource)


<!-- - [**Merchant Service API**](merchantsSvcAPI.md#merchants-api)
  
  The Merchants Service enables the management of information about a merchant and their stores. You can create, retrieve, update, and delete merchants using the Merchant Service API.

  - [*Representations*](merchantsSvcAPI.md#representations)

  - [*REST Endpoints*](merchantsSvcAPI.md#rest-endpoints)
    
    - [*Merchant Resource*](merchantsSvcAPI.md#merchant-resource)
    
    - [*Plan Resource*](merchantsSvcAPI.md#plan-resource)
    
    - [*Store Resource*](merchantsSvcAPI.md#store-resource)
    
    - [*Store Config Resource*](merchantsSvcAPI.md#store-config-resource) -->

  
- [**Price Service API**](priceSvcAPI.md#price-api)
  
  The Price Service enables the management of the price details of particular product variant. You can create, retrieve, update, and delete prices using the Price Service API.

    - [*Representations*](priceSvcAPI.md#representations)

    - [*REST Endpoints*](priceSvcAPI.md#rest-endpoints)


- [**Product Service API**](productsvcAPI.md#product-api)

    The Product Service enables the management of information about a product and its variants. You can create, retrieve, update, and delete products using the Product Service API.
    
  - [*REST Endpoints*](productsvcAPI.md#rest-endpoints)

      - [*Product Service*](productsvcAPI.md#product-service)
         
      - [*Product Variant Service*](productsvcAPI.md#product-variant-service)
     
       - [*Product Service*](productsvcAPI.md#product-service)
     
       - [*Product Variant Service*](productsvcAPI.md#product-variant-service)
     

- [**Order Service API**](ordersSvcApi.md#order-svc-api)

    The Order Service enables the management of information about a customer order. You can create, retrieve, update, and delete Orders using the Order Service api.

    - [*Representations*](ordersSvcApi.md#representations)

    - [*REST Endpoints*](ordersSvcApi.md#rest-endpoints)

      - [*Order Item Resource*](ordersSvcApi.md#order-item-resource)

      - [*Order Resource*](ordersSvcApi.md#order-resource)

      - [*Order Item*](ordersSvcApi.md#order-item)

    - [**Quote API**](quotesvcApi.md#Quote-api)

- [**Wishlist Service API**](wishlistSvcAPI.md#wishlist-api)
  
  The Wishlist resource enables management of information about a customer's wishlist. You can create, retrieve, update, and delete wishlists using the Wishlist Service api.

   - [*Representations*](wishlistSvcAPI.md#representations)

  - [*REST Endpoints*](wishlistSvcAPI.md#rest-endpoints)

    - [*Wishlist Resource*](wishlistSvcAPI.md#wishlist-resource)

    - [*Wishlist Item Resource*](wishlistSvcAPI.md#wishlist-item-resource)
 


- [**Impex Service API**](impexAPI.md#impex-api)

    The ImpEx Service allows you to interact with all the core API's in the The Wishlist platform at a unified REST interface for the seemless interegration of bulk data in to the system. 

  - [*Representations*](impexAPI.md#representations)

  - [*REST Endpoints*](impexAPI.md#rest-endpoints)

    - [*Impex Batch*](impexAPI.md#impex-resource)

    - [*Impex Resource*](impexAPI.md#impex-resource)



- [**Shopify Connector**](ShopifyConnector.md#shopify-connect)
  
  Shopify Connector is used to integrate data from  Shopify system into the The Wishlist platform.

<!-- - [**Event Collector**](eventcollectorAPI.md#event-collector-api)

    The event collector API is employed for enabling various events and campains that pertain to a customer.
    
    - [*Representations*](eventcollectorAPI.md#representations)

    - [*REST Endpoints*](eventcollectorAPI.md#rest-endpoints)

      - [*Events  Resource*](eventcollectorAPI.md#events--resource)

      - [*Event Subscription Resource*](eventcollectorAPI.md#event-subscription-resource) -->

<!-- 
- [**Platform Generated Events**](platformgeneratedevents.md#platform-generated-messages)
 -->

- [**Emarsys Integration**](emarsysIntegration.md#emarsys-integration)

- [**Event Failure Reporting**](apiFails.md#event-collector-api)

     If an API fails after a reasonable number of times, a fault should be reported into event collector.


- [**Analytics Service**](reports.md#reports-api)

    Analytics service is used to generate the reports
