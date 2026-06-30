# Transient Token Data

```php
$transientTokenDataApi = $client->getTransientTokenDataApi();
```

## Class Name

`TransientTokenDataApi`

## Methods

* [Get Transaction for Transient Token](../../doc/controllers/transient-token-data.md#get-transaction-for-transient-token)
* [Get Payment Credentials for Transient Token](../../doc/controllers/transient-token-data.md#get-payment-credentials-for-transient-token)


# Get Transaction for Transient Token

Retrieve the data captured by Unified Checkout. This API is used to retrieve the detailed data represented by the Transient Token. This API will not return PCI payment data (PAN). Include the Request ID in the GET request to retrieve the transaction details.

```php
function getTransactionForTransientToken(string $transientToken): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transientToken` | `string` | Template, Required | Transient Token returned by the Unified Checkout application. |

## Response Type

**200**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```php
$transientToken = 'transientToken6';

$transientTokenDataApi = $client->getTransientTokenDataApi();
$apiResponse = $transientTokenDataApi->getTransactionForTransientToken($transientToken);

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
| 404 | The specified resource not found in the system. | `ApiException` |
| 500 | Unexpected server error | `ApiException` |


# Get Payment Credentials for Transient Token

Retrieve the Payment data captured by Unified Checkout. This API is used to retrieve the detailed data represented by the Transient Token. This API will return PCI payment data captured by the Unified Checkout platform.

```php
function getPaymentCredentialsForTransientToken(string $paymentCredentialsReference): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentCredentialsReference` | `string` | Template, Required | The paymentCredentialsReference field contained within the Transient token returned from a successful Unified Checkout transaction |

## Response Type

**200**: Retrieved payment credentials reference

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type `mixed`.

## Example Usage

```php
$paymentCredentialsReference = 'paymentCredentialsReference6';

$transientTokenDataApi = $client->getTransientTokenDataApi();
$apiResponse = $transientTokenDataApi->getPaymentCredentialsForTransientToken($paymentCredentialsReference);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'mixed:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | The specified resource not found in the system. | `ApiException` |
| 500 | Unexpected server error | `ApiException` |

