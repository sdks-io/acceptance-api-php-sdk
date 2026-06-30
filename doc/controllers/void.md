# Void

A void cancels a payment or capture. A transaction can be voided only when Visa Acceptance has not already
submitted the capture to your processor. You cannot undo a void.

```php
$voidApi = $client->getVoidApi();
```

## Class Name

`VoidApi`

## Methods

* [Void Payment](../../doc/controllers/void.md#void-payment)
* [Void Capture](../../doc/controllers/void.md#void-capture)
* [Void Refund](../../doc/controllers/void.md#void-refund)
* [Void Credit](../../doc/controllers/void.md#void-credit)
* [Mit Void](../../doc/controllers/void.md#mit-void)


# Void Payment

Void a Payment API is only used, if you have requested Authorization and Capture together in [/pts/v2/payments]( API call. Include the payment ID in the POST request to cancel the payment.

```php
function voidPayment(string $id, VoidPaymentRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The payment ID returned from a previous payment request. |
| `body` | [`VoidPaymentRequest`](../../doc/models/void-payment-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2PaymentsVoidsPost201Response`](../../doc/models/pts-v2-payments-voids-post-201-response.md).

## Example Usage

```php
$id = 'id0';

$body = VoidPaymentRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformation4Builder::init()
            ->transactionId('')
            ->build()
    )
    ->build();

$voidApi = $client->getVoidApi();
$apiResponse = $voidApi->voidPayment(
    $id,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2PaymentsVoidsPost201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2PaymentsVoidsPost400Response1Exception`](../../doc/models/pts-v2-payments-voids-post-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2PaymentsVoidsPost502Response1Exception`](../../doc/models/pts-v2-payments-voids-post-502-response-1-exception.md) |


# Void Capture

Refund a capture API is only used, if you have requested Capture independenlty using [/pts/v2/payments/{id}/captures]( API call. Include the capture ID in the POST request to cancel the capture.

```php
function voidCapture(string $id, VoidPaymentRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The capture ID returned from a previous capture request. |
| `body` | [`VoidPaymentRequest`](../../doc/models/void-payment-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2CapturesVoidsPost201Response`](../../doc/models/pts-v2-captures-voids-post-201-response.md).

## Example Usage

```php
$id = 'id0';

$body = VoidPaymentRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformation4Builder::init()
            ->transactionId('')
            ->build()
    )
    ->build();

$voidApi = $client->getVoidApi();
$apiResponse = $voidApi->voidCapture(
    $id,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2CapturesVoidsPost201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2CapturesVoidsPost400Response1Exception`](../../doc/models/pts-v2-captures-voids-post-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2CapturesVoidsPost502Response1Exception`](../../doc/models/pts-v2-captures-voids-post-502-response-1-exception.md) |


# Void Refund

Include the refund ID in the POST request to cancel the refund.

```php
function voidRefund(string $id, VoidPaymentRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The refund ID returned from a previous refund request. |
| `body` | [`VoidPaymentRequest`](../../doc/models/void-payment-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2RefundsVoidsPost201Response`](../../doc/models/pts-v2-refunds-voids-post-201-response.md).

## Example Usage

```php
$id = 'id0';

$body = VoidPaymentRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformation4Builder::init()
            ->transactionId('')
            ->build()
    )
    ->build();

$voidApi = $client->getVoidApi();
$apiResponse = $voidApi->voidRefund(
    $id,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2RefundsVoidsPost201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2RefundsVoidsPost400Response1Exception`](../../doc/models/pts-v2-refunds-voids-post-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2RefundsVoidsPost502Response1Exception`](../../doc/models/pts-v2-refunds-voids-post-502-response-1-exception.md) |


# Void Credit

Include the credit ID in the POST request to cancel the credit.

```php
function voidCredit(string $id, VoidPaymentRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The credit ID returned from a previous credit request. |
| `body` | [`VoidPaymentRequest`](../../doc/models/void-payment-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2CreditsVoidsPost201Response`](../../doc/models/pts-v2-credits-voids-post-201-response.md).

## Example Usage

```php
$id = 'id0';

$body = VoidPaymentRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformation4Builder::init()
            ->transactionId('')
            ->build()
    )
    ->build();

$voidApi = $client->getVoidApi();
$apiResponse = $voidApi->voidCredit(
    $id,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2CreditsVoidsPost201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2CreditsVoidsPost400Response1Exception`](../../doc/models/pts-v2-credits-voids-post-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2CreditsVoidsPost502Response1Exception`](../../doc/models/pts-v2-credits-voids-post-502-response-1-exception.md) |


# Mit Void

This is to void a previous payment, capture, refund, or credit that merchant does not receive a reply(Mostly due to timeout). To use this feature/API, make sure to pass unique value to field - clientReferenceInformation -> transactionId in your payment, capture, refund, or credit API call and use same transactionId in this API request payload to reverse the payment.

```php
function mitVoid(MitVoidRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`MitVoidRequest`](../../doc/models/mit-void-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2VoidsPost200Response`](../../doc/models/pts-v2-voids-post-200-response.md).

## Example Usage

```php
$body = MitVoidRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformationBuilder::init()
            ->transactionId('')
            ->build()
    )
    ->build();

$voidApi = $client->getVoidApi();
$apiResponse = $voidApi->mitVoid($body);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2VoidsPost200Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2VoidsPost400Response1Exception`](../../doc/models/pts-v2-voids-post-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2VoidsPost502Response1Exception`](../../doc/models/pts-v2-voids-post-502-response-1-exception.md) |

