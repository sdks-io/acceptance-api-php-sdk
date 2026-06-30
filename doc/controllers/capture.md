# Capture

When you are ready to fulfill a customer’s order and transfer funds from the customer’s
bank to your bank, capture the payment for that order.

```php
$captureApi = $client->getCaptureApi();
```

## Class Name

`CaptureApi`


# Capture Payment

Include the payment ID in the POST request to capture the payment amount.

```php
function capturePayment(string $id, CapturePaymentRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The payment ID returned from a previous payment request. This ID links the capture to the payment. |
| `body` | [`CapturePaymentRequest`](../../doc/models/capture-payment-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2PaymentsCapturesPost201Response`](../../doc/models/pts-v2-payments-captures-post-201-response.md).

## Example Usage

```php
$id = 'id0';

$body = CapturePaymentRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformationBuilder::init()
            ->code('TC50171_3')
            ->build()
    )
    ->orderInformation(
        OrderInformation6Builder::init()
            ->amountDetails(
                AmountDetails9Builder::init()
                    ->totalAmount('102.21')
                    ->currency('USD')
                    ->build()
            )
            ->build()
    )
    ->build();

$captureApi = $client->getCaptureApi();
$apiResponse = $captureApi->capturePayment(
    $id,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2PaymentsCapturesPost201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2PaymentsCapturesPost400Response1Exception`](../../doc/models/pts-v2-payments-captures-post-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2PaymentsCapturesPost502Response1Exception`](../../doc/models/pts-v2-payments-captures-post-502-response-1-exception.md) |

