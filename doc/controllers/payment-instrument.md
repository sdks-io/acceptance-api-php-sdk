# Payment Instrument

```php
$paymentInstrumentApi = $client->getPaymentInstrumentApi();
```

## Class Name

`PaymentInstrumentApi`

## Methods

* [Post Payment Instrument](../../doc/controllers/payment-instrument.md#post-payment-instrument)
* [Get Payment Instrument](../../doc/controllers/payment-instrument.md#get-payment-instrument)
* [Patch Payment Instrument](../../doc/controllers/payment-instrument.md#patch-payment-instrument)
* [Delete Payment Instrument](../../doc/controllers/payment-instrument.md#delete-payment-instrument)


# Post Payment Instrument

|  |  |  |
| --- | --- | --- |
|**Standalone Payment Instruments**<br>A Payment Instrument represents tokenized payment information such as expiration date, billing address & card type.<br>A Payment Instrument token does not store the card number. A Payment Instrument is associated with an [Instrument Identifier](#token-management_instrument-identifier_create-an-instrument-identifier) that represents either a payment card number, or in the case of an ACH bank account, the routing and account number.<br>**Standalone Payment Instruments do not belong to a [Customer](#token-management_customer_create-a-customer).**<br><br>**Creating a Payment Instrument**<br>It is recommended you [create a Payment Instrument via a Payment Authorization](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-with-token-create_authorization-with-customer-token-creation_liveconsole-tab-request-body), this can be for a zero amount.<br>In Europe: You should perform Payer Authentication alongside the Authorization.|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Payment Network Tokens**<br>Network tokens perform better than regular card numbers and they are not necessarily invalidated when a cardholder loses their card, or it expires.<br>A Payment Network Token will be automatically created and used in future payments if you are enabled for the service.<br>A Payment Network Token can also be [provisioned for an existing Instrument Identifier](#token-management_instrument-identifier_enroll-an-instrument-identifier-for-payment-network-token).<br>For more information about Payment Network Tokens see the Developer Guide.<br><br>**Payments with Payment Instruments**<br>To perform a payment with a particular Payment Instrument specify the [Payment Instrument in the payment request](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-using-tokens_authorization-with-customer-payment-instrument-and-shipping-address-token-id_liveconsole-tab-request-body).

```php
function postPaymentInstrument(
    PostPaymentInstrumentRequest $body,
    ?string $profileId = null,
    ?bool $retrieveBinDetails = null
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PostPaymentInstrumentRequest`](../../doc/models/post-payment-instrument-request.md) | Body, Required | - |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |
| `retrieveBinDetails` | `?bool` | Query, Optional | Retrieve the Bin Details of PAN or network token |

## Response Type

**201**: Returns an existing Payment Instrument associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PostPaymentInstrumentResponse`](../../doc/models/post-payment-instrument-response.md).

## Example Usage

```php
$body = PostPaymentInstrumentRequestBuilder::init()->build();

$paymentInstrumentApi = $client->getPaymentInstrumentApi();
$apiResponse = $paymentInstrumentApi->postPaymentInstrument($body);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PostPaymentInstrumentResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`PostPaymentInstrumentException1Exception`](../../doc/models/post-payment-instrument-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`PostPaymentInstrumentException21Exception`](../../doc/models/post-payment-instrument-exception-21-exception.md) |
| 409 | Conflict. The token is linked to a Payment Instrument. | [`PostPaymentInstrumentException31Exception`](../../doc/models/post-payment-instrument-exception-31-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`PostPaymentInstrumentException41Exception`](../../doc/models/post-payment-instrument-exception-41-exception.md) |
| 500 | Unexpected error. | [`PostPaymentInstrumentException51Exception`](../../doc/models/post-payment-instrument-exception-51-exception.md) |


# Get Payment Instrument

|  |  |  |
| --- | --- | --- |
|**Standalone Payment Instruments**<br>A Payment Instrument represents tokenized payment information such as expiration date, billing address & card type.<br>A Payment Instrument token does not store the card number. A Payment Instrument is associated with an [Instrument Identifier](#token-management_instrument-identifier_create-an-instrument-identifier) that represents either a payment card number, or in the case of an ACH bank account, the routing and account number.<br>**Standalone Payment Instruments do not belong to a [Customer](#token-management_customer_create-a-customer).**|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Retrieving a Payment Instrument**<br>Your system can use this API to retrieve an existing Payment Instrument.<br>To perform a payment with a particular Payment Instrument simply specify the [Payment Instrument Id in the payments request](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-using-tokens_authorization-with-customer-payment-instrument-and-shipping-address-token-id_liveconsole-tab-request-body).

```php
function getPaymentInstrument(
    string $paymentInstrumentId,
    ?string $profileId = null,
    ?bool $retrieveBinDetails = null
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentInstrumentId` | `string` | Template, Required | The Id of a payment instrument.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |
| `retrieveBinDetails` | `?bool` | Query, Optional | Retrieve the Bin Details of PAN or network token |

## Response Type

**200**: Returns an existing Payment Instrument associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`GetPaymentInstrumentResponse`](../../doc/models/get-payment-instrument-response.md).

## Example Usage

```php
$paymentInstrumentId = 'paymentInstrumentId2';

$paymentInstrumentApi = $client->getPaymentInstrumentApi();
$apiResponse = $paymentInstrumentApi->getPaymentInstrument($paymentInstrumentId);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'GetPaymentInstrumentResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`GetPaymentInstrumentException1Exception`](../../doc/models/get-payment-instrument-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`GetPaymentInstrumentException21Exception`](../../doc/models/get-payment-instrument-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`GetPaymentInstrumentException31Exception`](../../doc/models/get-payment-instrument-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`GetPaymentInstrumentException41Exception`](../../doc/models/get-payment-instrument-exception-41-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`GetPaymentInstrumentException31Exception`](../../doc/models/get-payment-instrument-exception-31-exception.md) |
| 500 | Unexpected error. | [`GetPaymentInstrumentException61Exception`](../../doc/models/get-payment-instrument-exception-61-exception.md) |


# Patch Payment Instrument

|  |  |  |
| --- | --- | --- |
|**Standalone Payment Instruments**<br>A Payment Instrument represents tokenized payment information such as expiration date, billing address & card type.<br>A Payment Instrument token does not store the card number. A Payment Instrument is associated with an [Instrument Identifier](#token-management_instrument-identifier_create-an-instrument-identifier) that represents either a payment card number, or in the case of an ACH bank account, the routing and account number.<br>**Standalone Payment Instruments do not belong to a [Customer](#token-management_customer_create-a-customer).**|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Updating a Payment Instrument**<br>Your system can use this API to update an existing Payment Instrument.

```php
function patchPaymentInstrument(
    string $paymentInstrumentId,
    PatchPaymentInstrumentRequest $body,
    ?string $profileId = null,
    ?bool $retrieveBinDetails = null,
    ?string $ifMatch = null
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentInstrumentId` | `string` | Template, Required | The Id of a payment instrument.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `body` | [`PatchPaymentInstrumentRequest`](../../doc/models/patch-payment-instrument-request.md) | Body, Required | - |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |
| `retrieveBinDetails` | `?bool` | Query, Optional | Retrieve the Bin Details of PAN or network token |
| `ifMatch` | `?string` | Header, Optional | Contains an ETag value from a GET request to make the request conditional.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |

## Response Type

**200**: Returns an existing Payment Instrument associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PatchPaymentInstrumentResponse`](../../doc/models/patch-payment-instrument-response.md).

## Example Usage

```php
$paymentInstrumentId = 'paymentInstrumentId2';

$body = PatchPaymentInstrumentRequestBuilder::init()->build();

$paymentInstrumentApi = $client->getPaymentInstrumentApi();
$apiResponse = $paymentInstrumentApi->patchPaymentInstrument(
    $paymentInstrumentId,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PatchPaymentInstrumentResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`PatchPaymentInstrumentException1Exception`](../../doc/models/patch-payment-instrument-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`PatchPaymentInstrumentException21Exception`](../../doc/models/patch-payment-instrument-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`PatchPaymentInstrumentException31Exception`](../../doc/models/patch-payment-instrument-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`PatchPaymentInstrumentException41Exception`](../../doc/models/patch-payment-instrument-exception-41-exception.md) |
| 412 | Precondition Failed: The If-Match request header value does not match the current resources ETag | [`PatchPaymentInstrumentException51Exception`](../../doc/models/patch-payment-instrument-exception-51-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`PatchPaymentInstrumentException31Exception`](../../doc/models/patch-payment-instrument-exception-31-exception.md) |
| 500 | Unexpected error. | [`PatchPaymentInstrumentException71Exception`](../../doc/models/patch-payment-instrument-exception-71-exception.md) |


# Delete Payment Instrument

|  |  |  |
| --- | --- | --- |
|**Standalone Payment Instruments**<br>A Payment Instrument represents tokenized payment information such as expiration date, billing address & card type.<br>A Payment Instrument token does not store the card number. A Payment Instrument is associated with an [Instrument Identifier](#token-management_instrument-identifier_create-an-instrument-identifier) that represents either a payment card number, or in the case of an ACH bank account, the routing and account number.<br>**Standalone Payment Instruments do not belong to a [Customer](#token-management_customer_create-a-customer).**|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Deleting a Payment Instrument**<br>Your system can use this API to delete an existing Payment Instrument.<br>Any Instrument Identifiers representing the card number will also be deleted if they are not associated with any other Payment Instruments.

```php
function deletePaymentInstrument(string $paymentInstrumentId, ?string $profileId = null): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentInstrumentId` | `string` | Template, Required | The Id of a payment instrument.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**204**: The request is fulfilled but does not need to return a body

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```php
$paymentInstrumentId = 'paymentInstrumentId2';

$paymentInstrumentApi = $client->getPaymentInstrumentApi();
$apiResponse = $paymentInstrumentApi->deletePaymentInstrument($paymentInstrumentId);

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
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`DeletePaymentInstrumentException1Exception`](../../doc/models/delete-payment-instrument-exception-1-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`DeletePaymentInstrumentException21Exception`](../../doc/models/delete-payment-instrument-exception-21-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`DeletePaymentInstrumentException31Exception`](../../doc/models/delete-payment-instrument-exception-31-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`DeletePaymentInstrumentException21Exception`](../../doc/models/delete-payment-instrument-exception-21-exception.md) |
| 500 | Unexpected error. | [`DeletePaymentInstrumentException51Exception`](../../doc/models/delete-payment-instrument-exception-51-exception.md) |

