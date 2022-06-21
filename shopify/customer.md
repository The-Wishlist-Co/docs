# **Customer**
The Customer resource stores information about a shop's customers, such as their contact details, their order history, and whether they've agreed to receive email marketing.

The Customer resource also holds information on the status of a customer's account. Customers with accounts save time at checkout when they're logged in because they don't need to enter their contact information. You can use the Customer API to check whether a customer has an active account, and then invite them to create one if they don't.

For security reasons, the Customer resource doesn't store credit card information. Customers always need to enter this information at checkout.

## **Representations**

All representations are JSON objects submitted or received as payload to API requests or responses.

### customer
Represents a customer. If a store field is defined in a store, then the customer account is specific to the store.

<details>
 <summary>Expand for details</summary>

```accepts_marketing``` - boolean - Optional -
To enable marketing for a customer.

```accepts_marketing_updated_at``` - DateTime - The date and time (ISO 8601 format) when the customer consented or objected to receiving marketing material by email. Set this value whenever the customer consents or objects to marketing materials.

```addresses``` - [Address](../Common_Fields/address.md) - The address is saved as an array. The Address of the customer will be set to the ID of that address.

```admin_graphql_api_id``` - string

```created_at``` - The date and time (ISO 8601 format) when the customer was created.

```currency``` - string - The three-letter code (ISO 4217 format) for the currency that the customer used when they paid for their last order. Defaults to the shop currency. Returns the shop currency for test orders.

```default_address``` - [Address](Common_Fields/address.md) - The default address for the customer. The address is saved as an array. The defaultShippingAddress of the customer will be set to the ID of that address.

```email``` - string -
The customer's email address and the main identifier of uniqueness for a customer account. Attempting to assign the same email address to multiple customers returns an error.


```first_name``` - string -The customer's first name.

```id``` - string -A unique identifier for the customer.

```last_name``` - string - The customer's last name.

```last_order_id``` - string - The ID of the customer's last order.

```last_order_name``` - string -The name of the customer's last order. This is directly related to the **name** field on the Order resource.

```marketing_opt_in_level``` - string  - Optional - The marketing subscription opt-in level, as described in the Sender Best Common Practices, that the customer gave when they consented to receive marketing material by email. If the customer does not accept email marketing, then this property will be set to null. Valid values:
- single_opt_in
- confirmed_opt_in
- unknown

```multipass_identifier``` - string -A unique identifier for the customer that's used with ' 'Multipass login.

```note```	string - Optional -A note about the customer.


```orders_count``` - integer -The number of orders associated with this customer. Test and archived orders aren't counted.


```phone``` - string -The unique phone number (E.164 format) for this customer. Attempting to assign the same phone number to multiple customers returns an error. The property can be set using different formats, but each format must represent a number that can be dialed from anywhere in the world.

```state``` - string -The state of the customer's account with a shop. Default value: disabled. Valid values:
- disabled: The customer doesn't have an active account. Customer accounts can be disabled from the Shopify admin at any time.
- invited: The customer has received an email invite to create an account.
- enabled: The customer has created an account.
- declined: The customer declined the email invite to create an account.

```tags``` - string - Tags that the shop owner has attached to the customer, formatted as a string of comma-separated values. A customer can have up to 250 tags. Each tag can have up to 255 characters.


```tax_exempt``` - boolean -Whether the customer is exempt from paying taxes on their order. If true, then taxes won't be applied to an order at checkout. If false, then taxes will be applied at checkout.


```tax_exemptions``` string - Whether the customer is exempt from paying specific taxes on their order. Canadian taxes only.

```total_spent``` - number -The total amount of money that the customer has spent across their order history.

```twc_customer_id``` - string
The unique ID of the customer.


```updated_at``` - The date and time (ISO 8601 format) when the customer information was last updated.


```verified_email``` - boolean -Whether the customer has verified their email address.

</details>

## **REST Endpoints**
 
## Create a Customer
Creates a new Customer data set in the TWC system, then the wishlist is assigned to the created customer. All wishlists and orders will be assigned to the created customer.

Endpoint: ```/api/customers```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication`

## Upload Customers
Creates an array of new Customers in the TWC system.

Endpoint: ```/api/upload-customers```

Method: ``` POST ```

OAuth 2.0 Scopes: `Tenant authentication`

## Update a Customer
Updates Customer data set in the TWC system.

Endpoint: ```/api/customers```

Method: ``` PUT ```

OAuth 2.0 Scopes: `Tenant authentication`

## Find Customer by Ref
Returns a customer by its Ref from a specific Store while passing the respective Ref as a path param in the endpoint. The Tenant authentication maps to a Store.
If the customer does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/customers/{customerRef}```

Method: ``` GET ``` 

OAuth 2.0 Scopes: `Tenant authentication`

## Delete Customer by ID
Deleting a Customer marks the customer as deleted and produces the HTTP response confirming the action.
If the customer does not exist, this method returns a ResourceNotFound error.

Endpoint: ```/api/customers/{id}```

Method: ``` DELETE ```

OAuth 2.0 Scopes: `Tenant authentication`



