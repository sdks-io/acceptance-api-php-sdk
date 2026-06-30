# Customer Shipping Address

```php
$customerShippingAddressApi = $client->getCustomerShippingAddressApi();
```

## Class Name

`CustomerShippingAddressApi`

## Methods

* [Post Customer Shipping Address](../../doc/controllers/customer-shipping-address.md#post-customer-shipping-address)
* [Get Customer Shipping Addresses List](../../doc/controllers/customer-shipping-address.md#get-customer-shipping-addresses-list)
* [Get Customer Shipping Address](../../doc/controllers/customer-shipping-address.md#get-customer-shipping-address)
* [Patch Customers Shipping Address](../../doc/controllers/customer-shipping-address.md#patch-customers-shipping-address)
* [Delete Customer Shipping Address](../../doc/controllers/customer-shipping-address.md#delete-customer-shipping-address)


# Post Customer Shipping Address

|  |  |  |
| --- | --- | --- |
|**Customer Shipping Address**<br>A Customer Shipping Address represents tokenized customer shipping information.<br>A [Customer](#token-management_customer_create-a-customer) can have [one or more Shipping Addresses](#token-management_customer-shipping-address_list-shipping-addresses-for-a-customer), with one allocated as the Customers default for use in payments.|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Creating a Customer Shipping Address**<br>Your system can use this API to create an existing Customers default or non default Shipping Address.<br>You can also create additional Customer Shipping Addresses via the [Payments API](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-with-token-create_authorization-create-default-payment-instrument-shipping-address-for-existing-customer_liveconsole-tab-request-body).

```php
function postCustomerShippingAddress(
    string $customerId,
    PostCustomerShippingAddressRequest $body,
    ?string $profileId = null
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The Id of a Customer.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `body` | [`PostCustomerShippingAddressRequest`](../../doc/models/post-customer-shipping-address-request.md) | Body, Required | - |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**201**: A new Shipping Address has been created.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PostCustomerShippingAddressResponse`](../../doc/models/post-customer-shipping-address-response.md).

## Example Usage

```php
$customerId = 'customerId6';

$body = PostCustomerShippingAddressRequestBuilder::init()->build();

$customerShippingAddressApi = $client->getCustomerShippingAddressApi();
$apiResponse = $customerShippingAddressApi->postCustomerShippingAddress(
    $customerId,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PostCustomerShippingAddressResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`PostCustomerShippingAddressException1Exception`](../../doc/models/post-customer-shipping-address-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`PostCustomerShippingAddressException21Exception`](../../doc/models/post-customer-shipping-address-exception-21-exception.md) |
| 409 | Conflict. The token is linked to a Payment Instrument. | [`PostCustomerShippingAddressException31Exception`](../../doc/models/post-customer-shipping-address-exception-31-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`PostCustomerShippingAddressException41Exception`](../../doc/models/post-customer-shipping-address-exception-41-exception.md) |
| 500 | Unexpected error. | [`PostCustomerShippingAddressException51Exception`](../../doc/models/post-customer-shipping-address-exception-51-exception.md) |


# Get Customer Shipping Addresses List

|  |  |  |
| --- | --- | --- |
|**Customer Shipping Address**<br>A Customer Shipping Address represents tokenized customer shipping information.<br>A [Customer](#token-management_customer_create-a-customer) can have [one or more Shipping Addresses](#token-management_customer-shipping-address_list-shipping-addresses-for-a-customer), with one allocated as the Customers default for use in payments.|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Retrieving all Customer Shipping Addresses**<br>Your system can use this API to retrieve all existing Shipping Addresses for a Customer.

```php
function getCustomerShippingAddressesList(
    string $customerId,
    ?string $profileId = null,
    ?int $offset = 0,
    ?int $limit = 20
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The Id of a Customer.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |
| `offset` | `?int` | Query, Optional | Starting record in zero-based dataset that should be returned as the first object in the array. Default is 0.<br><br>**Default**: `0`<br><br>**Constraints**: `>= 0` |
| `limit` | `?int` | Query, Optional | The maximum number that can be returned in the array starting from the offset record in zero-based dataset. Default is 20, maximum is 100.<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 100` |

## Response Type

**200**: Returns all existing Shipping Addresses associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`ShippingAddressListForCustomer`](../../doc/models/shipping-address-list-for-customer.md).

## Example Usage

```php
$customerId = 'customerId6';

$offset = 0;

$limit = 20;

$customerShippingAddressApi = $client->getCustomerShippingAddressApi();
$apiResponse = $customerShippingAddressApi->getCustomerShippingAddressesList(
    $customerId,
    null,
    $offset,
    $limit
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'ShippingAddressListForCustomer:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`GetCustomerShippingAddressesListException1Exception`](../../doc/models/get-customer-shipping-addresses-list-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`GetCustomerShippingAddressesListException21Exception`](../../doc/models/get-customer-shipping-addresses-list-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`GetCustomerShippingAddressesListException31Exception`](../../doc/models/get-customer-shipping-addresses-list-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`GetCustomerShippingAddressesListException41Exception`](../../doc/models/get-customer-shipping-addresses-list-exception-41-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`GetCustomerShippingAddressesListException31Exception`](../../doc/models/get-customer-shipping-addresses-list-exception-31-exception.md) |
| 500 | Unexpected error. | [`GetCustomerShippingAddressesListException61Exception`](../../doc/models/get-customer-shipping-addresses-list-exception-61-exception.md) |


# Get Customer Shipping Address

|  |  |  |
| --- | --- | --- |
|**Customer Shipping Address**<br>A Customer Shipping Address represents tokenized customer shipping information.<br>A [Customer](#token-management_customer_create-a-customer) can have [one or more Shipping Addresses](#token-management_customer-shipping-address_list-shipping-addresses-for-a-customer), with one allocated as the Customers default for use in payments.|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Retrieving a Customer Shipping Address**<br>Your system can use this API to retrieve an existing Shipping Address for a Customer.<br>To perform a payment with a particular Shipping Address simply specify the [Shipping Address Id in the payments request](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-using-tokens_authorization-with-customer-payment-instrument-and-shipping-address-token-id_liveconsole-tab-request-body).

```php
function getCustomerShippingAddress(
    string $customerId,
    string $shippingAddressId,
    ?string $profileId = null
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The Id of a Customer.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `shippingAddressId` | `string` | Template, Required | The Id of a shipping address.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**200**: Returns an existing Shipping Address associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`GetCustomerShippingAddressResponse`](../../doc/models/get-customer-shipping-address-response.md).

## Example Usage

```php
$customerId = 'customerId6';

$shippingAddressId = 'shippingAddressId2';

$customerShippingAddressApi = $client->getCustomerShippingAddressApi();
$apiResponse = $customerShippingAddressApi->getCustomerShippingAddress(
    $customerId,
    $shippingAddressId
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'GetCustomerShippingAddressResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`GetCustomerShippingAddressException1Exception`](../../doc/models/get-customer-shipping-address-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`GetCustomerShippingAddressException21Exception`](../../doc/models/get-customer-shipping-address-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`GetCustomerShippingAddressException31Exception`](../../doc/models/get-customer-shipping-address-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`GetCustomerShippingAddressException41Exception`](../../doc/models/get-customer-shipping-address-exception-41-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`GetCustomerShippingAddressException31Exception`](../../doc/models/get-customer-shipping-address-exception-31-exception.md) |
| 500 | Unexpected error. | [`GetCustomerShippingAddressException61Exception`](../../doc/models/get-customer-shipping-address-exception-61-exception.md) |


# Patch Customers Shipping Address

|  |  |  |
| --- | --- | --- |
|**Customer Shipping Address**<br>A Customer Shipping Address represents tokenized customer shipping information.<br>A [Customer](#token-management_customer_create-a-customer) can have [one or more Shipping Addresses](#token-management_customer-shipping-address_list-shipping-addresses-for-a-customer), with one allocated as the Customers default for use in payments.|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Updating a Customers Shipping Address**<br>Your system can use this API to update an existing Shipping Addresses for a Customer, including selecting a [default Shipping Address](#token-management_customer-shipping-address_update-a-customer-shipping-address_samplerequests-dropdown_make-customer-shipping-address-the-default_liveconsole-tab-request-body) for use in payments.

```php
function patchCustomersShippingAddress(
    string $customerId,
    string $shippingAddressId,
    PatchCustomerShippingAddressRequest $body,
    ?string $profileId = null,
    ?string $ifMatch = null
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The Id of a Customer.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `shippingAddressId` | `string` | Template, Required | The Id of a shipping address.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `body` | [`PatchCustomerShippingAddressRequest`](../../doc/models/patch-customer-shipping-address-request.md) | Body, Required | - |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |
| `ifMatch` | `?string` | Header, Optional | Contains an ETag value from a GET request to make the request conditional.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |

## Response Type

**200**: Returns an existing Shipping Address associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PatchCustomersShippingAddressResponse`](../../doc/models/patch-customers-shipping-address-response.md).

## Example Usage

```php
$customerId = 'customerId6';

$shippingAddressId = 'shippingAddressId2';

$body = PatchCustomerShippingAddressRequestBuilder::init()->build();

$customerShippingAddressApi = $client->getCustomerShippingAddressApi();
$apiResponse = $customerShippingAddressApi->patchCustomersShippingAddress(
    $customerId,
    $shippingAddressId,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PatchCustomersShippingAddressResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`PatchCustomersShippingAddressException1Exception`](../../doc/models/patch-customers-shipping-address-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`PatchCustomersShippingAddressException21Exception`](../../doc/models/patch-customers-shipping-address-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`PatchCustomersShippingAddressException31Exception`](../../doc/models/patch-customers-shipping-address-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`PatchCustomersShippingAddressException41Exception`](../../doc/models/patch-customers-shipping-address-exception-41-exception.md) |
| 412 | Precondition Failed: The If-Match request header value does not match the current resources ETag | [`PatchCustomersShippingAddressException51Exception`](../../doc/models/patch-customers-shipping-address-exception-51-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`PatchCustomersShippingAddressException31Exception`](../../doc/models/patch-customers-shipping-address-exception-31-exception.md) |
| 500 | Unexpected error. | [`PatchCustomersShippingAddressException71Exception`](../../doc/models/patch-customers-shipping-address-exception-71-exception.md) |


# Delete Customer Shipping Address

|  |  |  |
| --- | --- | --- |
|**Customer Shipping Address**<br>A Customer Shipping Address represents tokenized customer shipping information.<br>A [Customer](#token-management_customer_create-a-customer) can have [one or more Shipping Addresses](#token-management_customer-shipping-address_list-shipping-addresses-for-a-customer), with one allocated as the Customers default for use in payments.|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Deleting a Customers Shipping Address**<br>Your system can use this API to delete an existing Shipping Address for a Customer.<br>If a customer has more than one Shipping Address then the default Shipping Address cannot be deleted without first selecting a [new default Shipping Address](#token-management_customer-shipping-address_update-a-customer-shipping-address_samplerequests-dropdown_make-customer-shipping-address-the-default_liveconsole-tab-request-body).

```php
function deleteCustomerShippingAddress(
    string $customerId,
    string $shippingAddressId,
    ?string $profileId = null
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The Id of a Customer.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `shippingAddressId` | `string` | Template, Required | The Id of a shipping address.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**204**: The request is fulfilled but does not need to return a body

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```php
$customerId = 'customerId6';

$shippingAddressId = 'shippingAddressId2';

$customerShippingAddressApi = $client->getCustomerShippingAddressApi();
$apiResponse = $customerShippingAddressApi->deleteCustomerShippingAddress(
    $customerId,
    $shippingAddressId
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'void:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`DeleteCustomerShippingAddressException1Exception`](../../doc/models/delete-customer-shipping-address-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`DeleteCustomerShippingAddressException21Exception`](../../doc/models/delete-customer-shipping-address-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`DeleteCustomerShippingAddressException31Exception`](../../doc/models/delete-customer-shipping-address-exception-31-exception.md) |
| 409 | Conflict. The token is linked to a Payment Instrument. | [`DeleteCustomerShippingAddressException41Exception`](../../doc/models/delete-customer-shipping-address-exception-41-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`DeleteCustomerShippingAddressException51Exception`](../../doc/models/delete-customer-shipping-address-exception-51-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`DeleteCustomerShippingAddressException31Exception`](../../doc/models/delete-customer-shipping-address-exception-31-exception.md) |
| 500 | Unexpected error. | [`DeleteCustomerShippingAddressException71Exception`](../../doc/models/delete-customer-shipping-address-exception-71-exception.md) |

