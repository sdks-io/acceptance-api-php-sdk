# Transaction Batches

Get a list of batch files or details of Individual file processed through the Offline Transaction Submission Services.

```php
$transactionBatchesApi = $client->getTransactionBatchesApi();
```

## Class Name

`TransactionBatchesApi`

## Methods

* [Get Transaction Batches](../../doc/controllers/transaction-batches.md#get-transaction-batches)
* [Get Transaction Batch Id](../../doc/controllers/transaction-batches.md#get-transaction-batch-id)
* [Get Transaction Batch Details](../../doc/controllers/transaction-batches.md#get-transaction-batch-details)


# Get Transaction Batches

Provide the date and time search range to get a list of Batch Files ready for settlement

```php
function getTransactionBatches(\DateTime $startTime, \DateTime $endTime): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `startTime` | `DateTime` | Query, Required | Valid report Start Time in **ISO 8601 format**<br>Please refer the following link to know more about ISO 8601 format.[Rfc Date Format](<br><br>**Example date format:**<br><br>- yyyy-MM-dd'T'HH:mm:ss.SSSZZ |
| `endTime` | `DateTime` | Query, Required | Valid report End Time in **ISO 8601 format**<br>Please refer the following link to know more about ISO 8601 format.[Rfc Date Format](<br><br>**Example date format:**<br><br>- yyyy-MM-dd'T'HH:mm:ss.SSSZZ |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV1TransactionBatchesGet200Response`](../../doc/models/pts-v1-transaction-batches-get-200-response.md).

## Example Usage

```php
$startTime = DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z');

$endTime = DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z');

$transactionBatchesApi = $client->getTransactionBatchesApi();
$apiResponse = $transactionBatchesApi->getTransactionBatches(
    $startTime,
    $endTime
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV1TransactionBatchesGet200Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`PtsV1TransactionBatchesGet400Response1Exception`](../../doc/models/pts-v1-transaction-batches-get-400-response-1-exception.md) |
| 401 | Not Authorized | [`PtsV1TransactionBatchesGet401Response1Exception`](../../doc/models/pts-v1-transaction-batches-get-401-response-1-exception.md) |
| 403 | No Authenticated | [`PtsV1TransactionBatchesGet403Response1Exception`](../../doc/models/pts-v1-transaction-batches-get-403-response-1-exception.md) |
| 404 | No Reports Found | [`PtsV1TransactionBatchesGet404Response1Exception`](../../doc/models/pts-v1-transaction-batches-get-404-response-1-exception.md) |
| 500 | Bad Gateway | [`PtsV1TransactionBatchesGet500Response1Exception`](../../doc/models/pts-v1-transaction-batches-get-500-response-1-exception.md) |


# Get Transaction Batch Id

This API provides details like upload date, completion date, transaction count and accepted and rejected transaction count of the individual batch file using the batch id

```php
function getTransactionBatchId(string $id): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The batch id assigned for the template. |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV1TransactionBatchesIdGet200Response`](../../doc/models/pts-v1-transaction-batches-id-get-200-response.md).

## Example Usage

```php
$id = 'id0';

$transactionBatchesApi = $client->getTransactionBatchesApi();
$apiResponse = $transactionBatchesApi->getTransactionBatchId($id);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV1TransactionBatchesIdGet200Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`PtsV1TransactionBatchesGet400Response1Exception`](../../doc/models/pts-v1-transaction-batches-get-400-response-1-exception.md) |
| 401 | Not Authorized | [`PtsV1TransactionBatchesGet401Response1Exception`](../../doc/models/pts-v1-transaction-batches-get-401-response-1-exception.md) |
| 403 | No Authenticated | [`PtsV1TransactionBatchesGet403Response1Exception`](../../doc/models/pts-v1-transaction-batches-get-403-response-1-exception.md) |
| 404 | No Reports Found | [`PtsV1TransactionBatchesGet404Response1Exception`](../../doc/models/pts-v1-transaction-batches-get-404-response-1-exception.md) |
| 502 | Bad Gateway | [`PtsV1TransactionBatchesGet502Response1Exception`](../../doc/models/pts-v1-transaction-batches-get-502-response-1-exception.md) |


# Get Transaction Batch Details

Provides real-time detailed status information about the transactions that you previously uploaded in the Business Center or processed with the Offline Transaction File Submission service.

```php
function getTransactionBatchDetails(
    string $id,
    ?\DateTime $uploadDate = null,
    ?string $status = null
): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The batch id assigned for the template. |
| `uploadDate` | `?DateTime` | Query, Optional | Date in which the original batch file was uploaded. Date must be in ISO-8601 format.<br>Please refer the following link to know more about ISO 8601 format.[Rfc Date Format](<br>**Example date format:**<br><br>- yyyy-MM-dd |
| `status` | `?string` | Query, Optional | Allows you to filter by rejected response.<br><br>Valid values:<br><br>- Rejected |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```php
$id = 'id0';

$transactionBatchesApi = $client->getTransactionBatchesApi();
$apiResponse = $transactionBatchesApi->getTransactionBatchDetails($id);

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
| 400 | Bad Request | `ApiException` |
| 401 | Not Authorized | `ApiException` |
| 403 | No Authenticated | `ApiException` |
| 404 | No Reports Found | `ApiException` |
| 502 | Bad Gateway | `ApiException` |

