# Instrument Identifier

```php
$instrumentIdentifierApi = $client->getInstrumentIdentifierApi();
```

## Class Name

`InstrumentIdentifierApi`

## Methods

* [Post Instrument Identifier](../../doc/controllers/instrument-identifier.md#post-instrument-identifier)
* [Get Instrument Identifier](../../doc/controllers/instrument-identifier.md#get-instrument-identifier)
* [Patch Instrument Identifier](../../doc/controllers/instrument-identifier.md#patch-instrument-identifier)
* [Delete Instrument Identifier](../../doc/controllers/instrument-identifier.md#delete-instrument-identifier)
* [Get Instrument Identifier Payment Instruments List](../../doc/controllers/instrument-identifier.md#get-instrument-identifier-payment-instruments-list)
* [Post Instrument Identifier Enrollment](../../doc/controllers/instrument-identifier.md#post-instrument-identifier-enrollment)


# Post Instrument Identifier

|  |  |  |
| --- | --- | --- |
|**Instrument Identifiers**<br>An Instrument Identifier represents either a card number, or in the case of an ACH bank account, the routing and account number.<br>The same token Id is returned for a specific card number or bank account & routing number allowing the Instrument Identifier Id to be used for cross-channel payment tracking.<br>An Instrument Identifier can exist independently but also be associated with a [Customer Payment Instrument](#token-management_customer-payment-instrument_create-a-customer-payment-instrument) or [Standalone Payment Instrument](#token-management_payment-instrument_create-a-payment-instrument).<br><br>**Creating an Instrument Identifier**<br>It is recommended you [create an Instrument Identifier via a Payment Authorization](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-with-token-create_authorization-with-instrument-identifier-token-creation_liveconsole-tab-request-body), this can be for a zero amount.<br>An Instrument Identifier will also be created if you [create a Customer via a Payment Authorization](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-with-token-create_authorization-with-customer-token-creation_liveconsole-tab-request-body)<br>In Europe: You should perform Payer Authentication alongside the Authorization.|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Payment Network Tokens**<br>Network tokens perform better than regular card numbers and they are not necessarily invalidated when a cardholder loses their card, or it expires.<br>A Payment Network Token will be automatically created and used in future payments if you are enabled for the service.<br>A Payment Network Token can also be [provisioned for an existing Instrument Identifier](#token-management_instrument-identifier_enroll-an-instrument-identifier-for-payment-network-token).<br>For more information about Payment Network Tokens see the Developer Guide.<br><br>**Payments with Instrument Identifiers**<br>To perform a payment with an Instrument Identifier simply specify the [Instrument Identifier Id in the payments request along with the expiration date, card type, & billing address](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-using-tokens_authorization-with-instrument-identifier-token-id_liveconsole-tab-request-body).<br>When an Instrument Identifier is used in a payment the **_previousTransactionId_** and **_originalAuthorizedAmount_** values are automatically recorded.<br>These values will be added for you to future Merchant Initiated Transaction payments.

```php
function postInstrumentIdentifier(
    PostInstrumentIdentifierRequest $body,
    ?string $profileId = null,
    ?bool $retrieveBinDetails = null
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PostInstrumentIdentifierRequest`](../../doc/models/post-instrument-identifier-request.md) | Body, Required | Specify either a Card, Bank Account or Enrollable Card |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |
| `retrieveBinDetails` | `?bool` | Query, Optional | Retrieve the Bin Details of PAN or network token |

## Response Type

**200**: Returns an existing Instrument Identifier associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PostInstrumentIdentifierResponse`](../../doc/models/post-instrument-identifier-response.md).

## Example Usage

```php
$body = PostInstrumentIdentifierRequestBuilder::init()->build();

$instrumentIdentifierApi = $client->getInstrumentIdentifierApi();
$apiResponse = $instrumentIdentifierApi->postInstrumentIdentifier($body);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PostInstrumentIdentifierResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`PostInstrumentIdentifierException1Exception`](../../doc/models/post-instrument-identifier-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`PostInstrumentIdentifierException21Exception`](../../doc/models/post-instrument-identifier-exception-21-exception.md) |
| 409 | Conflict. The token is linked to a Payment Instrument. | [`PostInstrumentIdentifierException31Exception`](../../doc/models/post-instrument-identifier-exception-31-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`PostInstrumentIdentifierException41Exception`](../../doc/models/post-instrument-identifier-exception-41-exception.md) |
| 500 | Unexpected error. | [`PostInstrumentIdentifierException51Exception`](../../doc/models/post-instrument-identifier-exception-51-exception.md) |


# Get Instrument Identifier

|  |  |  |
| --- | --- | --- |
|**Instrument Identifiers**<br>An Instrument Identifier represents either a card number, or in the case of an ACH bank account, the routing and account number.<br>The same token Id is returned for a specific card number or bank account & routing number allowing the Instrument Identifier Id to be used for cross-channel payment tracking.<br>An Instrument Identifier can exist independently but also be associated with a [Customer Payment Instrument](#token-management_customer-payment-instrument_create-a-customer-payment-instrument) or [Standalone Payment Instrument](#token-management_payment-instrument_create-a-payment-instrument).<br><br>**Retrieving an Instrument Identifier**<br>Your system can use this API to retrieve an Instrument Identifier.<br>**Note: the actual card data will be masked.**<br>The Instrument Identifier will also be returned when retrieving a [Customer](#token-management_customer_retrieve-a-customer), [Customer Payment Instrument](#token-management_customer-payment-instrument_retrieve-a-customer-payment-instrument) or [Standalone Payment Instrument](#token-management_payment-instrument_retrieve-a-payment-instrument).|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Payment Network Tokens**<br>Network tokens perform better than regular card numbers and they are not necessarily invalidated when a cardholder loses their card, or it expires.<br>A Payment Network Token will be automatically created and used in future payments if you are enabled for the service.<br>A Payment Network Token can also be [provisioned for an existing Instrument Identifier](#token-management_instrument-identifier_enroll-an-instrument-identifier-for-payment-network-token).<br>For more information about Payment Network Tokens see the Developer Guide.<br><br>**Payments with Instrument Identifiers**<br>To perform a payment with an Instrument Identifier simply specify the [Instrument Identifier Id in the payments request along with the expiration date, card type, & billing address](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-using-tokens_authorization-with-instrument-identifier-token-id_liveconsole-tab-request-body).<br>When an Instrument Identifier is used in a payment the **_previousTransactionId_** and **_originalAuthorizedAmount_** values are automatically recorded.<br>These values will be added for you to future Merchant Initiated Transaction payments.

```php
function getInstrumentIdentifier(
    string $instrumentIdentifierId,
    ?string $profileId = null,
    ?bool $retrieveBinDetails = null
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `instrumentIdentifierId` | `string` | Template, Required | The Id of an Instrument Identifier.<br><br>**Constraints**: *Minimum Length*: `12`, *Maximum Length*: `32` |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |
| `retrieveBinDetails` | `?bool` | Query, Optional | Retrieve the Bin Details of PAN or network token |

## Response Type

**200**: Returns an existing Instrument Identifier associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`GetInstrumentIdentifierResponse`](../../doc/models/get-instrument-identifier-response.md).

## Example Usage

```php
$instrumentIdentifierId = 'instrumentIdentifierId0';

$instrumentIdentifierApi = $client->getInstrumentIdentifierApi();
$apiResponse = $instrumentIdentifierApi->getInstrumentIdentifier($instrumentIdentifierId);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'GetInstrumentIdentifierResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`GetInstrumentIdentifierException1Exception`](../../doc/models/get-instrument-identifier-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`GetInstrumentIdentifierException21Exception`](../../doc/models/get-instrument-identifier-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`GetInstrumentIdentifierException31Exception`](../../doc/models/get-instrument-identifier-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`GetInstrumentIdentifierException41Exception`](../../doc/models/get-instrument-identifier-exception-41-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`GetInstrumentIdentifierException31Exception`](../../doc/models/get-instrument-identifier-exception-31-exception.md) |
| 500 | Unexpected error. | [`GetInstrumentIdentifierException61Exception`](../../doc/models/get-instrument-identifier-exception-61-exception.md) |


# Patch Instrument Identifier

|  |  |  |
| --- | --- | --- |
|**Instrument Identifiers**<br>An Instrument Identifier represents either a card number, or in the case of an ACH bank account, the routing and account number.<br>The same token Id is returned for a specific card number or bank account & routing number allowing the Instrument Identifier Id to be used for cross-channel payment tracking.<br>An Instrument Identifier can exist independently but also be associated with a [Customer Payment Instrument](#token-management_customer-payment-instrument_create-a-customer-payment-instrument) or [Standalone Payment Instrument](#token-management_payment-instrument_create-a-payment-instrument).|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Updating an Instrument Identifier**<br>When an Instrument Identifier is used in a payment the **_previousTransactionId_** and **_originalAuthorizedAmount_** values are automatically recorded.<br>These values will be added for you to future Merchant Initiated Transaction payments.<br>Your system can use this API to update these values.

```php
function patchInstrumentIdentifier(
    string $instrumentIdentifierId,
    PatchInstrumentIdentifierRequest $body,
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
| `instrumentIdentifierId` | `string` | Template, Required | The Id of an Instrument Identifier.<br><br>**Constraints**: *Minimum Length*: `12`, *Maximum Length*: `32` |
| `body` | [`PatchInstrumentIdentifierRequest`](../../doc/models/patch-instrument-identifier-request.md) | Body, Required | Specify the previous transaction Id to update. |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |
| `retrieveBinDetails` | `?bool` | Query, Optional | Retrieve the Bin Details of PAN or network token |
| `ifMatch` | `?string` | Header, Optional | Contains an ETag value from a GET request to make the request conditional.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` |

## Response Type

**200**: Returns an existing Instrument Identifier associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PatchInstrumentIdentifierResponse`](../../doc/models/patch-instrument-identifier-response.md).

## Example Usage

```php
$instrumentIdentifierId = 'instrumentIdentifierId0';

$body = PatchInstrumentIdentifierRequestBuilder::init()->build();

$instrumentIdentifierApi = $client->getInstrumentIdentifierApi();
$apiResponse = $instrumentIdentifierApi->patchInstrumentIdentifier(
    $instrumentIdentifierId,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PatchInstrumentIdentifierResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request: e.g. A required header value could be missing. | [`PatchInstrumentIdentifierException1Exception`](../../doc/models/patch-instrument-identifier-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`PatchInstrumentIdentifierException21Exception`](../../doc/models/patch-instrument-identifier-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`PatchInstrumentIdentifierException31Exception`](../../doc/models/patch-instrument-identifier-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`PatchInstrumentIdentifierException41Exception`](../../doc/models/patch-instrument-identifier-exception-41-exception.md) |
| 412 | Precondition Failed: The If-Match request header value does not match the current resources ETag | [`PatchInstrumentIdentifierException51Exception`](../../doc/models/patch-instrument-identifier-exception-51-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`PatchInstrumentIdentifierException31Exception`](../../doc/models/patch-instrument-identifier-exception-31-exception.md) |
| 500 | Unexpected error. | [`PatchInstrumentIdentifierException71Exception`](../../doc/models/patch-instrument-identifier-exception-71-exception.md) |


# Delete Instrument Identifier

|  |  |  |
| --- | --- | --- |
|**Instrument Identifiers**<br>An Instrument Identifier represents either a card number, or in the case of an ACH bank account, the routing <br>and account numbers.<br>The same token Id is returned for a specific card number or bank account & routing number allowing the <br>Instrument Identifier Id to be used for cross-channel payment tracking.<br>An Instrument Identifier can exist independently but also be associated with a [Customer Payment Instrument](#token-management_customer-payment-instrument_create-a-customer-payment-instrument) <br>or [Standalone Payment Instrument](#token-management_payment-instrument_create-a-payment-instrument).|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Deleting an Instrument Identifier**<br>Your system can use this API to delete an existing Instrument Identifier.<br>An Instrument Identifier cannot be deleted if it is linked to any Payment Instruments.<br>You can [retrieve all Payment Instruments associated with an Instrument Identifier](#token-management_instrument-identifier_list-payment-instruments-for-an-instrument-identifier).

```php
function deleteInstrumentIdentifier(string $instrumentIdentifierId, ?string $profileId = null): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `instrumentIdentifierId` | `string` | Template, Required | The Id of an Instrument Identifier.<br><br>**Constraints**: *Minimum Length*: `12`, *Maximum Length*: `32` |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**204**: The request is fulfilled but does not need to return a body

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```php
$instrumentIdentifierId = 'instrumentIdentifierId0';

$instrumentIdentifierApi = $client->getInstrumentIdentifierApi();
$apiResponse = $instrumentIdentifierApi->deleteInstrumentIdentifier($instrumentIdentifierId);

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
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`DeleteInstrumentIdentifierException1Exception`](../../doc/models/delete-instrument-identifier-exception-1-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`DeleteInstrumentIdentifierException21Exception`](../../doc/models/delete-instrument-identifier-exception-21-exception.md) |
| 409 | Conflict. The token is linked to a Payment Instrument. | [`DeleteInstrumentIdentifierException31Exception`](../../doc/models/delete-instrument-identifier-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`DeleteInstrumentIdentifierException41Exception`](../../doc/models/delete-instrument-identifier-exception-41-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`DeleteInstrumentIdentifierException21Exception`](../../doc/models/delete-instrument-identifier-exception-21-exception.md) |
| 500 | Unexpected error. | [`DeleteInstrumentIdentifierException61Exception`](../../doc/models/delete-instrument-identifier-exception-61-exception.md) |


# Get Instrument Identifier Payment Instruments List

|  |  |  |
| --- | --- | --- |
|**Instrument Identifiers**<br>An Instrument Identifier represents either a card number, or in the case of an ACH bank account, the routing <br>and account numbers.<br>The same token Id is returned for a specific card number or bank account & routing number allowing the <br>Instrument Identifier Id to be used for cross-channel payment tracking.<br>An Instrument Identifier can exist independently but also be associated with a [Customer Payment Instrument](#token-management_customer-payment-instrument_create-a-customer-payment-instrument) <br>or [Standalone Payment Instrument](#token-management_payment-instrument_create-a-payment-instrument).|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Retrieving all Payment Instruments associated with an Instrument Identifier**<br>Your system can use this API to retrieve all Payment Instruments linked to an Instrument Identifier.

```php
function getInstrumentIdentifierPaymentInstrumentsList(
    string $instrumentIdentifierId,
    ?string $profileId = null,
    ?bool $retrieveBinDetails = null,
    ?int $offset = 0,
    ?int $limit = 20
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `instrumentIdentifierId` | `string` | Template, Required | The Id of an Instrument Identifier.<br><br>**Constraints**: *Minimum Length*: `12`, *Maximum Length*: `32` |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |
| `retrieveBinDetails` | `?bool` | Query, Optional | Retrieve the Bin Details of PAN or network token |
| `offset` | `?int` | Query, Optional | Starting record in zero-based dataset that should be returned as the first object in the array. Default is 0.<br><br>**Default**: `0`<br><br>**Constraints**: `>= 0` |
| `limit` | `?int` | Query, Optional | The maximum number that can be returned in the array starting from the offset record in zero-based dataset. Default is 20, maximum is 100.<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 100` |

## Response Type

**200**: Returns all existing Payment Instruments associated with the supplied Id.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PaymentInstrumentList`](../../doc/models/payment-instrument-list.md).

## Example Usage

```php
$instrumentIdentifierId = 'instrumentIdentifierId0';

$offset = 0;

$limit = 20;

$instrumentIdentifierApi = $client->getInstrumentIdentifierApi();
$apiResponse = $instrumentIdentifierApi->getInstrumentIdentifierPaymentInstrumentsList(
    $instrumentIdentifierId,
    null,
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
| 400 | Bad Request: e.g. A required header value could be missing. | [`GetInstrumentIdentifierPaymentInstrumentsListException1Exception`](../../doc/models/get-instrument-identifier-payment-instruments-list-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`GetInstrumentIdentifierPaymentInstrumentsListException21Exception`](../../doc/models/get-instrument-identifier-payment-instruments-list-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`GetInstrumentIdentifierPaymentInstrumentsListException31Exception`](../../doc/models/get-instrument-identifier-payment-instruments-list-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`GetInstrumentIdentifierPaymentInstrumentsListException41Exception`](../../doc/models/get-instrument-identifier-payment-instruments-list-exception-41-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`GetInstrumentIdentifierPaymentInstrumentsListException31Exception`](../../doc/models/get-instrument-identifier-payment-instruments-list-exception-31-exception.md) |
| 500 | Unexpected error. | [`GetInstrumentIdentifierPaymentInstrumentsListException61Exception`](../../doc/models/get-instrument-identifier-payment-instruments-list-exception-61-exception.md) |


# Post Instrument Identifier Enrollment

|  |  |  |
| --- | --- | --- |
|**Instrument Identifiers**<br>An Instrument Identifier represents either a card number, or in the case of an ACH bank account, the routing and account number.<br>The same token Id is returned for a specific card number or bank account & routing number allowing the Instrument Identifier Id to be used for cross-channel payment tracking.<br>An Instrument Identifier can exist independently but also be associated with a [Customer Payment Instrument](#token-management_customer-payment-instrument_create-a-customer-payment-instrument) or [Standalone Payment Instrument](#token-management_payment-instrument_create-a-payment-instrument).|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Enroll an Instrument Identifier for a Payment Network Token**<br>Your system can use this API to provision a Network token for an existing Instrument Identifier.<br>Network tokens perform better than regular card numbers and they are not necessarily invalidated when a cardholder loses their card, or it expires.<br>A Network token can be [provisioned when creating an Instrument Identifier](#token-management_instrument-identifier_create-an-instrument-identifier_samplerequests-dropdown_create-instrument-identifier-card-enroll-for-network-token_liveconsole-tab-request-body).This will occur automatically when creating a [Customer](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-with-token-create_authorization-with-customer-token-creation_liveconsole-tab-request-body), [Payment Instrument](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-with-token-create_authorization-create-default-payment-instrument-shipping-address-for-existing-customer_liveconsole-tab-request-body) or [Instrument Identifier](#payments_payments_process-a-payment_samplerequests-dropdown_authorization-with-token-create_authorization-with-instrument-identifier-token-creation_liveconsole-tab-request-body) via the Payments API.<br>For more information about Payment Network Tokens see the Developer Guide.

```php
function postInstrumentIdentifierEnrollment(
    string $instrumentIdentifierId,
    PostInstrumentIdentifierEnrollmentRequest $body,
    ?string $profileId = null
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `instrumentIdentifierId` | `string` | Template, Required | The Id of an Instrument Identifier.<br><br>**Constraints**: *Minimum Length*: `12`, *Maximum Length*: `32` |
| `body` | [`PostInstrumentIdentifierEnrollmentRequest`](../../doc/models/post-instrument-identifier-enrollment-request.md) | Body, Required | Specify Enrollable Card details |
| `profileId` | `?string` | Header, Optional | The Id of a profile containing user specific TMS configuration.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` |

## Response Type

**202**: The request has been accepted for processing, but the processing has not been completed.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```php
$instrumentIdentifierId = 'instrumentIdentifierId0';

$body = PostInstrumentIdentifierEnrollmentRequestBuilder::init()->build();

$instrumentIdentifierApi = $client->getInstrumentIdentifierApi();
$apiResponse = $instrumentIdentifierApi->postInstrumentIdentifierEnrollment(
    $instrumentIdentifierId,
    $body
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
| 400 | Bad Request: e.g. A required header value could be missing. | [`PostInstrumentIdentifierEnrollmentException1Exception`](../../doc/models/post-instrument-identifier-enrollment-exception-1-exception.md) |
| 403 | Forbidden: e.g. The profile might not have permission to perform the operation. | [`PostInstrumentIdentifierEnrollmentException21Exception`](../../doc/models/post-instrument-identifier-enrollment-exception-21-exception.md) |
| 404 | Token Not Found. The Id may not exist or was entered incorrectly. | [`PostInstrumentIdentifierEnrollmentException31Exception`](../../doc/models/post-instrument-identifier-enrollment-exception-31-exception.md) |
| 410 | Token Not Available. The token has been deleted. | [`PostInstrumentIdentifierEnrollmentException41Exception`](../../doc/models/post-instrument-identifier-enrollment-exception-41-exception.md) |
| 424 | Failed Dependency: e.g. The profile represented by the profile-id may not exist or the profile-id was entered incorrectly. | [`PostInstrumentIdentifierEnrollmentException31Exception`](../../doc/models/post-instrument-identifier-enrollment-exception-31-exception.md) |
| 500 | Unexpected error. | [`PostInstrumentIdentifierEnrollmentException61Exception`](../../doc/models/post-instrument-identifier-enrollment-exception-61-exception.md) |

