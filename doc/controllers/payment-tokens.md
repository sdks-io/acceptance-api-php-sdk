# Payment-Tokens

A payment-tokens is a service that is used for retrieving vault details or deleting vault id/payment method.

```php
$paymentTokensApi = $client->getPaymentTokensApi();
```

## Class Name

`PaymentTokensApi`


# Retrieve or Delete Payment Token

This API can be used in two flavours - for retrieval or deletion of vault id.

```php
function retrieveOrDeletePaymentToken(Request $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`Request`](../../doc/models/request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`RetrieveOrDeletePaymentTokenResponse`](../../doc/models/retrieve-or-delete-payment-token-response.md).

## Example Usage

```php
$body = RequestBuilder::init()->build();

$paymentTokensApi = $client->getPaymentTokensApi();
$apiResponse = $paymentTokensApi->retrieveOrDeletePaymentToken($body);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'RetrieveOrDeletePaymentTokenResponse:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2RetrievePaymentTokenGet400Response1Exception`](../../doc/models/pts-v2-retrieve-payment-token-get-400-response-1-exception.md) |
| 502 | Internal server error. | [`PtsV2RetrievePaymentTokenGet502Response1Exception`](../../doc/models/pts-v2-retrieve-payment-token-get-502-response-1-exception.md) |

