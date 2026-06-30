# Transaction Details

```php
$transactionDetailsApi = $client->getTransactionDetailsApi();
```

## Class Name

`TransactionDetailsApi`


# Get Transaction

Include the Request ID in the GET request to retrieve the transaction details.

```php
function getTransaction(string $id): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | Request ID. |

## Response Type

**200**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`TssV2TransactionsGet200Response`](../../doc/models/tss-v2-transactions-get-200-response.md).

## Example Usage

```php
$id = 'id0';

$transactionDetailsApi = $client->getTransactionDetailsApi();
$apiResponse = $transactionDetailsApi->getTransaction($id);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'TssV2TransactionsGet200Response:';
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

