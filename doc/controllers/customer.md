# Customer

A Customer can be linked to multiple Payment Instruments and Shipping Addresses.
With one Payment Instrument and Shipping Address designated as the default.
It stores merchant reference information for the Customer such as email and merchant defined data.

```php
$customerApi = $client->getCustomerApi();
```

## Class Name

`CustomerApi`

## Methods

* [Post Customer](../../doc/controllers/customer.md#post-customer)
* [Get Customer](../../doc/controllers/customer.md#get-customer)
* [Patch Customer](../../doc/controllers/customer.md#patch-customer)
* [Delete Customer](../../doc/controllers/customer.md#delete-customer)


# Post Customer

|  |  |  |
| --- | --- | --- |
|**Customers**<br>A Customer represents your tokenized customer information.<br>You should associate the Customer Id with the customer account on your systems.<br>A Customer can have one or more [Payment Instruments](#token-management_customer-payment-instrument_create-a-customer-payment-instrumentl) or [Shipping Addresses](#token-management_customer-shipping-address_create-a-customer-shipping-address) with one allocated as the Customers default.<br><br>**Creating a Customer**<br>It is recommended you [create a Customer via a Payment Authorization](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-with-token-create_authorization-with-customer-token-creation_liveconsole-tab-request-body), this can be for a zero amount.<br>The Customer will be created with a Payment Instrument and Shipping Address.<br>You can also [add additional Payment Instruments to a Customer via a Payment Authorization](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-with-token-create_authorization-create-default-payment-instrument-shipping-address-for-existing-customer_liveconsole-tab-request-body).<br>In Europe: You should perform Payer Authentication alongside the Authorization.|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Payment Network Tokens**<br>Network tokens perform better than regular card numbers and they are not necessarily invalidated when a cardholder loses their card, or it expires.<br>A Payment Network Token will be automatically created and used in future payments if you are enabled for the service.<br>A Payment Network Token can also be [provisioned for an existing Instrument Identifier](#token-management_instrument-identifier_enroll-an-instrument-identifier-for-payment-network-token).<br>For more information about Payment Network Tokens see the Developer Guide.<br><br>**Payments with Customers**<br>To perform a payment with the Customers default details specify the [Customer Id in the payments request](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-using-tokens_authorization-with-customer-token-id_liveconsole-tab-request-body).<br>To perform a payment with a particular Payment Instrument or Shipping Address <br>specify the [Payment Instrument or Shipping Address Ids in the payments request](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-using-tokens_authorization-with-customer-payment-instrument-and-shipping-address-token-id_liveconsole-tab-request-body).
The availability of API features for a merchant may depend on the portfolio configuration and may need to be enabled at the portfolio level before they can be added to merchant accounts.

```php
function postCustomer(PostCustomerRequest $body, ?string $profileId = null): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PostCustomerRequest`](../../doc/models/post-customer-request.md) | Body, Required | - |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**201**: A new Customer has been created.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`TmsV2CustomersResponse`](../../doc/models/tms-v2-customers-response.md).

## Example Usage

```php
$body = PostCustomerRequestBuilder::init()->build();

$customerApi = $client->getCustomerApi();
$apiResponse = $customerApi->postCustomer($body);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'TmsV2CustomersResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`PostCustomerException1Exception`](../../doc/models/post-customer-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`PostCustomerException21Exception`](../../doc/models/post-customer-exception-21-exception.md) |
| 409 | Conflict. The token is linked to a Payment Instrument. | [`PostCustomerException31Exception`](../../doc/models/post-customer-exception-31-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`PostCustomerException41Exception`](../../doc/models/post-customer-exception-41-exception.md) |
| 500 | Unexpected error. | [`PostCustomerException51Exception`](../../doc/models/post-customer-exception-51-exception.md) |


# Get Customer

|  |  |  |
| --- | --- | --- |
|**Customers**<br>A Customer represents your tokenized customer information.<br>You should associate the Customer Id with the customer account on your systems.<br>A Customer can have one or more [Payment Instruments](#token-management_customer-payment-instrument_create-a-customer-payment-instrumentl) or [Shipping Addresses](#token-management_customer-shipping-address_create-a-customer-shipping-address) with one allocated as the Customers default.<br><br>**Retrieving a Customer**<br>When your customer signs into their account, your system can use this API to retrieve the Customers default Payment Instrument and Shipping Address.<br>**Note: the actual card data will be masked.**<br>If your customer wants to see other available Payment Instruments, your system can [retrieve all Payment Instruments](#token-management_customer-payment-instrument_list-payment-instruments-for-a-customer) associated with the Customer.<br>The same applies to [Shipping Addresses](#token-management_customer-shipping-address_list-shipping-addresses-for-a-customer).|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Payment Network Tokens**<br>Network tokens perform better than regular card numbers and they are not necessarily invalidated when a cardholder loses their card, or it expires.<br>A Payment Network Token will be automatically created and used in future payments if you are enabled for the service.<br>A Payment Network Token can also be [provisioned for an existing Instrument Identifier](#token-management_instrument-identifier_enroll-an-instrument-identifier-for-payment-network-token).<br>For more information about Payment Network Tokens see the Developer Guide.<br><br>**Payments with Customers**<br>To perform a payment with the Customers default details specify the [Customer Id in the payments request](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-using-tokens_authorization-with-customer-token-id_liveconsole-tab-request-body).<br>To perform a payment with a particular Payment Instrument or Shipping Address <br>specify the [Payment Instrument or Shipping Address Ids in the payments request](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-using-tokens_authorization-with-customer-payment-instrument-and-shipping-address-token-id_liveconsole-tab-request-body).

```php
function getCustomer(string $customerId, ?string $profileId = null): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The Id of a Customer.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**200**: Returns an existing Customer associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`GetCustomerResponse`](../../doc/models/get-customer-response.md).

## Example Usage

```php
$customerId = 'customerId6';

$customerApi = $client->getCustomerApi();
$apiResponse = $customerApi->getCustomer($customerId);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'GetCustomerResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`GetCustomerException1Exception`](../../doc/models/get-customer-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`GetCustomerException21Exception`](../../doc/models/get-customer-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`GetCustomerException31Exception`](../../doc/models/get-customer-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`GetCustomerException41Exception`](../../doc/models/get-customer-exception-41-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`GetCustomerException31Exception`](../../doc/models/get-customer-exception-31-exception.md) |
| 500 | Unexpected error. | [`GetCustomerException61Exception`](../../doc/models/get-customer-exception-61-exception.md) |


# Patch Customer

|  |  |  |
| --- | --- | --- |
|**Customers**<br>A Customer represents your tokenized customer information.<br>You should associate the Customer Id with the customer account on your systems.<br>A Customer can have one or more [Payment Instruments](#token-management_customer-payment-instrument_create-a-customer-payment-instrumentl) or [Shipping Addresses](#token-management_customer-shipping-address_create-a-customer-shipping-address) with one allocated as the Customers default.|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Updating a Customer**<br>Your system can use this API to update a Customers details including selecting a  [default Payment Instrument](#token-management_customer_update-a-customer_samplerequests-dropdown_update-customers-default-payment-instrument_liveconsole-tab-request-body) or [default Shipping Address](#token-management_customer_update-a-customer_samplerequests-dropdown_update-customers-default-shipping-address_liveconsole-tab-request-body) for use in payments.<br>Note: Updating a Customers [Payment Instrument](#token-management_customer-payment-instrument_update-a-customer-payment-instrument) or [Shipping Address](#token-management_customer-shipping-address_update-a-customer-shipping-address) details is performed using their own dedicated API resources.

```php
function patchCustomer(
    string $customerId,
    PatchCustomerRequest $body,
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
| `body` | [`PatchCustomerRequest`](../../doc/models/patch-customer-request.md) | Body, Required | - |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |
| `ifMatch` | `?string` | Header, Optional | Contains an ETag value from a GET request to make the request conditional.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |

## Response Type

**200**: Returns an existing Customer associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PatchCustomerResponse`](../../doc/models/patch-customer-response.md).

## Example Usage

```php
$customerId = 'customerId6';

$body = PatchCustomerRequestBuilder::init()->build();

$customerApi = $client->getCustomerApi();
$apiResponse = $customerApi->patchCustomer(
    $customerId,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PatchCustomerResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`PatchCustomerException1Exception`](../../doc/models/patch-customer-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`PatchCustomerException21Exception`](../../doc/models/patch-customer-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`PatchCustomerException31Exception`](../../doc/models/patch-customer-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`PatchCustomerException41Exception`](../../doc/models/patch-customer-exception-41-exception.md) |
| 412 | Precondition Failed: The If-Match request header value does not match the current resources ETag | [`PatchCustomerException51Exception`](../../doc/models/patch-customer-exception-51-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`PatchCustomerException31Exception`](../../doc/models/patch-customer-exception-31-exception.md) |
| 500 | Unexpected error. | [`PatchCustomerException71Exception`](../../doc/models/patch-customer-exception-71-exception.md) |


# Delete Customer

|  |  |  |
| --- | --- | --- |
|**Customers**<br>A Customer represents your tokenized customer information.<br>You should associate the Customer Id with the customer account on your systems.<br>A Customer can have one or more [Payment Instruments](#token-management_customer-payment-instrument_create-a-customer-payment-instrumentl) or [Shipping Addresses](#token-management_customer-shipping-address_create-a-customer-shipping-address) with one allocated as the Customers default.|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Deleting a Customer**<br>Your system can use this API to delete a complete Customer.<br>When a Customer is deleted all associated Payment Instruments & Shipping Addresses are deleted.<br>Any Instrument Identifiers representing the card number will also be deleted if they are not associated with any other Payment Instruments.<br>Note: Individual [Payment Instruments](#token-management_customer-payment-instrument_delete-a-customer-payment-instrument) or [Shipping Addresses](#token-management_customer-shipping-address_delete-a-customer-shipping-address) can be deleted via their own dedicated API resources.

```php
function deleteCustomer(string $customerId, ?string $profileId = null): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The Id of a Customer.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**204**: The request is fulfilled but does not need to return a body

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```php
$customerId = 'customerId6';

$customerApi = $client->getCustomerApi();
$apiResponse = $customerApi->deleteCustomer($customerId);

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
| 400 | Bad Request: e.g. A required header value could be missing. | [`DeleteCustomerException1Exception`](../../doc/models/delete-customer-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`DeleteCustomerException21Exception`](../../doc/models/delete-customer-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`DeleteCustomerException31Exception`](../../doc/models/delete-customer-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`DeleteCustomerException41Exception`](../../doc/models/delete-customer-exception-41-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`DeleteCustomerException31Exception`](../../doc/models/delete-customer-exception-31-exception.md) |
| 500 | Unexpected error. | [`DeleteCustomerException61Exception`](../../doc/models/delete-customer-exception-61-exception.md) |

