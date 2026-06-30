# Customer Payment Instrument

```php
$customerPaymentInstrumentApi = $client->getCustomerPaymentInstrumentApi();
```

## Class Name

`CustomerPaymentInstrumentApi`

## Methods

* [Post Customer Payment Instrument](../../doc/controllers/customer-payment-instrument.md#post-customer-payment-instrument)
* [Get Customer Payment Instruments List](../../doc/controllers/customer-payment-instrument.md#get-customer-payment-instruments-list)
* [Get Customer Payment Instrument](../../doc/controllers/customer-payment-instrument.md#get-customer-payment-instrument)
* [Patch Customers Payment Instrument](../../doc/controllers/customer-payment-instrument.md#patch-customers-payment-instrument)
* [Delete Customer Payment Instrument](../../doc/controllers/customer-payment-instrument.md#delete-customer-payment-instrument)


# Post Customer Payment Instrument

|  |  |  |
| --- | --- | --- |
|**Customer Payment Instrument**<br>A Customer Payment Instrument represents tokenized customer payment information such as expiration date, billing address & card type.<br>A [Customer](#token-management_customer_create-a-customer) can have [one or more Payment Instruments](#token-management_customer-payment-instrument_retrieve-a-customer-payment-instrument), with one allocated as the Customers default for use in payments.<br>A Payment Instrument token does not store the card number. A Payment Instrument is associated with an [Instrument Identifier](#token-management_instrument-identifier_create-an-instrument-identifier) that represents either a payment card number, or in the case of an ACH bank account, the routing and account number.<br><br>**Creating a Customer Payment Instrument**<br>It is recommended you [create a Customer Payment Instrument via a Payment Authorization](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-with-token-create_authorization-create-default-payment-instrument-shipping-address-for-existing-customer_liveconsole-tab-request-body), this can be for a zero amount.<br>In Europe: You should perform Payer Authentication alongside the Authorization.|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Payment Network Tokens**<br>Network tokens perform better than regular card numbers and they are not necessarily invalidated when a cardholder loses their card, or it expires.<br>A Payment Network Token will be automatically created and used in future payments if you are enabled for the service.<br>A Payment Network Token can also be [provisioned for an existing Instrument Identifier](#token-management_instrument-identifier_enroll-an-instrument-identifier-for-payment-network-token).<br>For more information about Payment Network Tokens see the Developer Guide.<br><br>**Payments with Customers Payment Instrument**<br>To perform a payment with a particular Payment Instrument or Shipping Address specify the [Payment Instrument in the payment request](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-using-tokens_authorization-with-customer-payment-instrument-and-shipping-address-token-id_liveconsole-tab-request-body).

```php
function postCustomerPaymentInstrument(
    string $customerId,
    PostCustomerPaymentInstrumentRequest $body,
    ?string $profileId = null
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The Id of a Customer.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `body` | [`PostCustomerPaymentInstrumentRequest`](../../doc/models/post-customer-payment-instrument-request.md) | Body, Required | - |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**201**: A new Payment Instrument has been created.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PostCustomerPaymentInstrumentResponse`](../../doc/models/post-customer-payment-instrument-response.md).

## Example Usage

```php
$customerId = 'customerId6';

$body = PostCustomerPaymentInstrumentRequestBuilder::init()->build();

$customerPaymentInstrumentApi = $client->getCustomerPaymentInstrumentApi();
$apiResponse = $customerPaymentInstrumentApi->postCustomerPaymentInstrument(
    $customerId,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PostCustomerPaymentInstrumentResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`PostCustomerPaymentInstrumentException1Exception`](../../doc/models/post-customer-payment-instrument-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`PostCustomerPaymentInstrumentException21Exception`](../../doc/models/post-customer-payment-instrument-exception-21-exception.md) |
| 409 | Conflict. The token is linked to a Payment Instrument. | [`PostCustomerPaymentInstrumentException31Exception`](../../doc/models/post-customer-payment-instrument-exception-31-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`PostCustomerPaymentInstrumentException41Exception`](../../doc/models/post-customer-payment-instrument-exception-41-exception.md) |
| 500 | Unexpected error. | [`PostCustomerPaymentInstrumentException51Exception`](../../doc/models/post-customer-payment-instrument-exception-51-exception.md) |


# Get Customer Payment Instruments List

|  |  |  |
| --- | --- | --- |
|**Customer Payment Instrument**<br>A Customer Payment Instrument represents tokenized customer payment information such as expiration date, billing address & card type.<br>A [Customer](#token-management_customer_create-a-customer) can have [one or more Payment Instruments](#token-management_customer-payment-instrument_retrieve-a-customer-payment-instrument), with one allocated as the Customers default for use in payments.<br>A Payment Instrument token does not store the card number. A Payment Instrument is associated with an [Instrument Identifier](#token-management_instrument-identifier_create-an-instrument-identifier) that represents either a payment card number, or in the case of an ACH bank account, the routing and account number.<br>|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Retrieving all Customer Payment Instruments**<br>Your system can use this API to retrieve all existing Payment Instruments for a Customer.

```php
function getCustomerPaymentInstrumentsList(
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

**200**: Returns all existing Payment Instruments associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PaymentInstrumentList`](../../doc/models/payment-instrument-list.md).

## Example Usage

```php
$customerId = 'customerId6';

$offset = 0;

$limit = 20;

$customerPaymentInstrumentApi = $client->getCustomerPaymentInstrumentApi();
$apiResponse = $customerPaymentInstrumentApi->getCustomerPaymentInstrumentsList(
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
    echo 'PaymentInstrumentList:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`GetCustomerPaymentInstrumentsListException1Exception`](../../doc/models/get-customer-payment-instruments-list-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`GetCustomerPaymentInstrumentsListException21Exception`](../../doc/models/get-customer-payment-instruments-list-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`GetCustomerPaymentInstrumentsListException31Exception`](../../doc/models/get-customer-payment-instruments-list-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`GetCustomerPaymentInstrumentsListException41Exception`](../../doc/models/get-customer-payment-instruments-list-exception-41-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`GetCustomerPaymentInstrumentsListException31Exception`](../../doc/models/get-customer-payment-instruments-list-exception-31-exception.md) |
| 500 | Unexpected error. | [`GetCustomerPaymentInstrumentsListException61Exception`](../../doc/models/get-customer-payment-instruments-list-exception-61-exception.md) |


# Get Customer Payment Instrument

|  |  |  |
| --- | --- | --- |
|**Customer Payment Instrument**<br>A Customer Payment Instrument represents tokenized customer payment information such as expiration date, billing address & card type.<br>A [Customer](#token-management_customer_create-a-customer) can have [one or more Payment Instruments](#token-management_customer-payment-instrument_retrieve-a-customer-payment-instrument), with one allocated as the Customers default for use in payments.<br>A Payment Instrument token does not store the card number. A Payment Instrument is associated with an [Instrument Identifier](#token-management_instrument-identifier_create-an-instrument-identifier) that represents either a payment card number, or in the case of an ACH bank account, the routing and account number.<br>|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Retrieving a Customer Payment Instrument**<br>Your system can use this API to retrieve an existing Payment Instrument for a Customer.<br>To perform a payment with a particular Payment Instrument simply specify the [Payment Instrument Id in the payments request](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-using-tokens_authorization-with-customer-payment-instrument-and-shipping-address-token-id_liveconsole-tab-request-body).

```php
function getCustomerPaymentInstrument(
    string $customerId,
    string $paymentInstrumentId,
    ?string $profileId = null
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The Id of a Customer.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `paymentInstrumentId` | `string` | Template, Required | The Id of a payment instrument.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**200**: Returns an existing Payment Instrument associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`GetCustomerPaymentInstrumentResponse`](../../doc/models/get-customer-payment-instrument-response.md).

## Example Usage

```php
$customerId = 'customerId6';

$paymentInstrumentId = 'paymentInstrumentId2';

$customerPaymentInstrumentApi = $client->getCustomerPaymentInstrumentApi();
$apiResponse = $customerPaymentInstrumentApi->getCustomerPaymentInstrument(
    $customerId,
    $paymentInstrumentId
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'GetCustomerPaymentInstrumentResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`GetCustomerPaymentInstrumentException1Exception`](../../doc/models/get-customer-payment-instrument-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`GetCustomerPaymentInstrumentException21Exception`](../../doc/models/get-customer-payment-instrument-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`GetCustomerPaymentInstrumentException31Exception`](../../doc/models/get-customer-payment-instrument-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`GetCustomerPaymentInstrumentException41Exception`](../../doc/models/get-customer-payment-instrument-exception-41-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`GetCustomerPaymentInstrumentException31Exception`](../../doc/models/get-customer-payment-instrument-exception-31-exception.md) |
| 500 | Unexpected error. | [`GetCustomerPaymentInstrumentException61Exception`](../../doc/models/get-customer-payment-instrument-exception-61-exception.md) |


# Patch Customers Payment Instrument

|  |  |  |
| --- | --- | --- |
|**Customer Payment Instrument**<br>A Customer Payment Instrument represents tokenized customer payment information such as expiration date, billing address & card type.<br>A [Customer](#token-management_customer_create-a-customer) can have [one or more Payment Instruments](#token-management_customer-payment-instrument_retrieve-a-customer-payment-instrument), with one allocated as the Customers default for use in payments.<br>A Payment Instrument token does not store the card number. A Payment Instrument is associated with an [Instrument Identifier](#token-management_instrument-identifier_create-an-instrument-identifier) that represents either a payment card number, or in the case of an ACH bank account, the routing and account number.<br>|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Updating a Customers Payment Instrument**<br>Your system can use this API to update an existing Payment Instrument for a Customer, including selecting a [default Payment Instrument](#token-management_customer-payment-instrument_update-a-customer-payment-instrument_samplerequests-dropdown_make-customer-payment-instrument-the-default_liveconsole-tab-request-body) for use in payments.

```php
function patchCustomersPaymentInstrument(
    string $customerId,
    string $paymentInstrumentId,
    PatchCustomerPaymentInstrumentRequest $body,
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
| `paymentInstrumentId` | `string` | Template, Required | The Id of a payment instrument.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `body` | [`PatchCustomerPaymentInstrumentRequest`](../../doc/models/patch-customer-payment-instrument-request.md) | Body, Required | - |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |
| `ifMatch` | `?string` | Header, Optional | Contains an ETag value from a GET request to make the request conditional.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |

## Response Type

**200**: Returns an existing Payment Instrument associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PatchCustomersPaymentInstrumentResponse`](../../doc/models/patch-customers-payment-instrument-response.md).

## Example Usage

```php
$customerId = 'customerId6';

$paymentInstrumentId = 'paymentInstrumentId2';

$body = PatchCustomerPaymentInstrumentRequestBuilder::init()->build();

$customerPaymentInstrumentApi = $client->getCustomerPaymentInstrumentApi();
$apiResponse = $customerPaymentInstrumentApi->patchCustomersPaymentInstrument(
    $customerId,
    $paymentInstrumentId,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PatchCustomersPaymentInstrumentResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`PatchCustomersPaymentInstrumentException1Exception`](../../doc/models/patch-customers-payment-instrument-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`PatchCustomersPaymentInstrumentException21Exception`](../../doc/models/patch-customers-payment-instrument-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`PatchCustomersPaymentInstrumentException31Exception`](../../doc/models/patch-customers-payment-instrument-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`PatchCustomersPaymentInstrumentException41Exception`](../../doc/models/patch-customers-payment-instrument-exception-41-exception.md) |
| 412 | Precondition Failed: The If-Match request header value does not match the current resources ETag | [`PatchCustomersPaymentInstrumentException51Exception`](../../doc/models/patch-customers-payment-instrument-exception-51-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`PatchCustomersPaymentInstrumentException31Exception`](../../doc/models/patch-customers-payment-instrument-exception-31-exception.md) |
| 500 | Unexpected error. | [`PatchCustomersPaymentInstrumentException71Exception`](../../doc/models/patch-customers-payment-instrument-exception-71-exception.md) |


# Delete Customer Payment Instrument

|  |  |  |
| --- | --- | --- |
|**Customer Payment Instrument**<br>A Customer Payment Instrument represents tokenized customer payment information such as expiration date, billing address & card type.<br>A [Customer](#token-management_customer_create-a-customer) can have [one or more Payment Instruments](#token-management_customer-payment-instrument_retrieve-a-customer-payment-instrument), with one allocated as the Customers default for use in payments.<br>A Payment Instrument token does not store the card number. A Payment Instrument is associated with an [Instrument Identifier](#token-management_instrument-identifier_create-an-instrument-identifier) that represents either a payment card number, or in the case of an ACH bank account, the routing and account number.<br>|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Deleting a Customers Payment Instrument**<br>Your system can use this API to delete an existing Payment Instrument for a Customer.<br>Any Instrument Identifiers representing the card number will also be deleted if they are not associated with any other Payment Instruments.<br>If a customer has more than one Payment Instrument then the default Payment Instrument cannot be deleted without first selecting a [new default Payment Instrument](#token-management_customer-payment-instrument_update-a-customer-payment-instrument_samplerequests-dropdown_make-customer-payment-instrument-the-default_liveconsole-tab-request-body).

```php
function deleteCustomerPaymentInstrument(
    string $customerId,
    string $paymentInstrumentId,
    ?string $profileId = null
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Template, Required | The Id of a Customer.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `paymentInstrumentId` | `string` | Template, Required | The Id of a payment instrument.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**204**: The request is fulfilled but does not need to return a body

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```php
$customerId = 'customerId6';

$paymentInstrumentId = 'paymentInstrumentId2';

$customerPaymentInstrumentApi = $client->getCustomerPaymentInstrumentApi();
$apiResponse = $customerPaymentInstrumentApi->deleteCustomerPaymentInstrument(
    $customerId,
    $paymentInstrumentId
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
| 400 | Bad Request: e.g. A required header value could be missing. | [`DeleteCustomerPaymentInstrumentException1Exception`](../../doc/models/delete-customer-payment-instrument-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`DeleteCustomerPaymentInstrumentException21Exception`](../../doc/models/delete-customer-payment-instrument-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`DeleteCustomerPaymentInstrumentException31Exception`](../../doc/models/delete-customer-payment-instrument-exception-31-exception.md) |
| 409 | Conflict. The token is linked to a Payment Instrument. | [`DeleteCustomerPaymentInstrumentException41Exception`](../../doc/models/delete-customer-payment-instrument-exception-41-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`DeleteCustomerPaymentInstrumentException51Exception`](../../doc/models/delete-customer-payment-instrument-exception-51-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`DeleteCustomerPaymentInstrumentException31Exception`](../../doc/models/delete-customer-payment-instrument-exception-31-exception.md) |
| 500 | Unexpected error. | [`DeleteCustomerPaymentInstrumentException71Exception`](../../doc/models/delete-customer-payment-instrument-exception-71-exception.md) |

