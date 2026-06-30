# Refund

A refund is a follow-on transaction that uses the ID returned from either a payment or capture request.

```php
$refundApi = $client->getRefundApi();
```

## Class Name

`RefundApi`

## Methods

* [Refund Payment](../../doc/controllers/refund.md#refund-payment)
* [Refund Capture](../../doc/controllers/refund.md#refund-capture)


# Refund Payment

Refund a Payment API is only used, if you have requested Authorization and Capture together in [/pts/v2/payments]( API call. Include the payment ID in the POST request to refund the payment amount.

```php
function refundPayment(string $id, RefundPaymentRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The payment ID. This ID is returned from a previous payment request. |
| `body` | [`RefundPaymentRequest`](../../doc/models/refund-payment-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2PaymentsRefundPost201Response`](../../doc/models/pts-v2-payments-refund-post-201-response.md).

## Example Usage

```php
$id = 'id0';

$body = RefundPaymentRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformation10Builder::init()
            ->code('Testing-VDP-Payments-Refund')
            ->build()
    )
    ->orderInformation(
        OrderInformation8Builder::init()
            ->amountDetails(
                AmountDetails9Builder::init()
                    ->totalAmount('102.21')
                    ->currency('USD')
                    ->build()
            )
            ->build()
    )
    ->build();

$refundApi = $client->getRefundApi();
$apiResponse = $refundApi->refundPayment(
    $id,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2PaymentsRefundPost201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2PaymentsRefundPost400Response1Exception`](../../doc/models/pts-v2-payments-refund-post-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2PaymentsRefundPost502Response1Exception`](../../doc/models/pts-v2-payments-refund-post-502-response-1-exception.md) |


# Refund Capture

Refund a capture API is only used, if you have requested Capture independenlty using [/pts/v2/payments/{id}/captures]( API call. Include the capture ID in the POST request to refund the captured amount.

```php
function refundCapture(string $id, RefundPaymentRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The capture ID. This ID is returned from a previous capture request. |
| `body` | [`RefundPaymentRequest`](../../doc/models/refund-payment-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2CapturesRefundsPost201Response`](../../doc/models/pts-v2-captures-refunds-post-201-response.md).

## Example Usage

```php
$id = 'id0';

$body = RefundPaymentRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformation10Builder::init()
            ->code('Testing-VDP-Payments-Refund')
            ->build()
    )
    ->orderInformation(
        OrderInformation8Builder::init()
            ->amountDetails(
                AmountDetails9Builder::init()
                    ->totalAmount('102.21')
                    ->currency('USD')
                    ->build()
            )
            ->build()
    )
    ->build();

$refundApi = $client->getRefundApi();
$apiResponse = $refundApi->refundCapture(
    $id,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2CapturesRefundsPost201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2CapturesRefundsPost400Response1Exception`](../../doc/models/pts-v2-captures-refunds-post-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2CapturesRefundsPost502Response1Exception`](../../doc/models/pts-v2-captures-refunds-post-502-response-1-exception.md) |

