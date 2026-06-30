# Reversal

An authorization reversal releases the hold that the payment placed on the customer’s funds.

```php
$reversalApi = $client->getReversalApi();
```

## Class Name

`ReversalApi`

## Methods

* [Auth Reversal](../../doc/controllers/reversal.md#auth-reversal)
* [Mit Reversal](../../doc/controllers/reversal.md#mit-reversal)


# Auth Reversal

Include the payment ID in the POST request to reverse the payment amount.

```php
function authReversal(string $id, AuthReversalRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The payment ID returned from a previous payment request. |
| `body` | [`AuthReversalRequest`](../../doc/models/auth-reversal-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2PaymentsReversalsPost201Response`](../../doc/models/pts-v2-payments-reversals-post-201-response.md).

## Example Usage

```php
$id = 'id0';

$body = AuthReversalRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformation4Builder::init()
            ->code('TC50171_3')
            ->transactionId('code')
            ->build()
    )
    ->reversalInformation(
        ReversalInformationBuilder::init()
            ->amountDetails(
                AmountDetails5Builder::init()
                    ->totalAmount('102.21')
                    ->build()
            )
            ->reason('testing')
            ->build()
    )
    ->build();

$reversalApi = $client->getReversalApi();
$apiResponse = $reversalApi->authReversal(
    $id,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2PaymentsReversalsPost201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2PaymentsReversalsPost400Response1Exception`](../../doc/models/pts-v2-payments-reversals-post-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2PaymentsReversalsPost502Response1Exception`](../../doc/models/pts-v2-payments-reversals-post-502-response-1-exception.md) |


# Mit Reversal

This is to reverse a previous payment that merchant does not receive a reply(Mostly due to Timeout). To use this feature/API, make sure to pass unique value to field - clientReferenceInformation -> transactionId in [/pts/v2/payments]( API call and use same transactionId in this API request payload to reverse the payment.

```php
function mitReversal(MitReversalRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`MitReversalRequest`](../../doc/models/mit-reversal-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2ReversalsPost201Response`](../../doc/models/pts-v2-reversals-post-201-response.md).

## Example Usage

```php
$body = MitReversalRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformationBuilder::init()
            ->transactionId('')
            ->build()
    )
    ->reversalInformation(
        ReversalInformationBuilder::init()
            ->amountDetails(
                AmountDetails5Builder::init()
                    ->totalAmount('102.21')
                    ->build()
            )
            ->reason('testing')
            ->build()
    )
    ->build();

$reversalApi = $client->getReversalApi();
$apiResponse = $reversalApi->mitReversal($body);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2ReversalsPost201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2ReversalsPost400Response1Exception`](../../doc/models/pts-v2-reversals-post-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2ReversalsPost502Response1Exception`](../../doc/models/pts-v2-reversals-post-502-response-1-exception.md) |

