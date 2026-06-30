# Orders

An order is a service that is used for initiating a transaction with itemized details, shipping, billing and buyer information.

```php
$ordersApi = $client->getOrdersApi();
```

## Class Name

`OrdersApi`

## Methods

* [Create Order](../../doc/controllers/orders.md#create-order)
* [Update Order](../../doc/controllers/orders.md#update-order)


# Create Order

A create order request enables you to send the itemized details along with the order. This API can be used by merchants initiating their transactions with the create order API.

```php
function createOrder(CreateOrderRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateOrderRequest`](../../doc/models/create-order-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2CreateOrderPost201Response`](../../doc/models/pts-v2-create-order-post-201-response.md).

## Example Usage

```php
$body = CreateOrderRequestBuilder::init()->build();

$ordersApi = $client->getOrdersApi();
$apiResponse = $ordersApi->createOrder($body);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2CreateOrderPost201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2CreateOrderPost400Response1Exception`](../../doc/models/pts-v2-create-order-post-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2CreateOrderPost502Response1Exception`](../../doc/models/pts-v2-create-order-post-502-response-1-exception.md) |


# Update Order

This API can be used in two flavours - for updating the order as well as saving the order.

```php
function updateOrder(string $id, UpdateOrderRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID returned from the original create order response. |
| `body` | [`UpdateOrderRequest`](../../doc/models/update-order-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2UpdateOrderPatch201Response`](../../doc/models/pts-v2-update-order-patch-201-response.md).

## Example Usage

```php
$id = 'id0';

$body = UpdateOrderRequestBuilder::init()
    ->orderInformation(
        OrderInformation31Builder::init()
            ->amountDetails(
                AmountDetails32Builder::init()
                    ->totalAmount('102.21')
                    ->currency('USD')
                    ->build()
            )
            ->shipTo(
                ShipTo11Builder::init()
                    ->firstName('RTS')
                    ->lastName('VDP')
                    ->address1('201 S. Division St.')
                    ->locality('Ann Arbor')
                    ->administrativeArea('MI')
                    ->postalCode('48104-2201')
                    ->country('US')
                    ->build()
            )
            ->additionalProperty('invoiceDescription', ApiHelper::deserialize('{"productDescription":"Description of the product invoice"}'))
            ->build()
    )
    ->merchantInformation(
        MerchantInformation17Builder::init()
            ->merchantDescriptor(
                MerchantDescriptor11Builder::init()
                    ->name('Merchant1')
                    ->email('merchant1@gmail.com')
                    ->build()
            )
            ->build()
    )
    ->paymentInformation(
        PaymentInformation28Builder::init()
            ->paymentType(
                PaymentType19Builder::init()
                    ->name('ewallet')
                    ->method(
                        Method19Builder::init()
                            ->name('payPal')
                            ->build()
                    )
                    ->build()
            )
            ->build()
    )
    ->build();

$ordersApi = $client->getOrdersApi();
$apiResponse = $ordersApi->updateOrder(
    $id,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2UpdateOrderPatch201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2UpdateOrderPatch400Response1Exception`](../../doc/models/pts-v2-update-order-patch-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2UpdateOrderPatch502Response1Exception`](../../doc/models/pts-v2-update-order-patch-502-response-1-exception.md) |

