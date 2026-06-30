# Payments

A payment authorizes the amount for the transaction. There are a number of supported payment
instruments, such as Credit Card, Debit Card, e-Wallet, and Alternative Payments. A payment
response includes the status of the request. It also includes processor-specific information
when the request is successful and errors if unsuccessful.

```php
$paymentsApi = $client->getPaymentsApi();
```

## Class Name

`PaymentsApi`

## Methods

* [Create Payment](../../doc/controllers/payments.md#create-payment)
* [Increment Auth](../../doc/controllers/payments.md#increment-auth)
* [Refresh Payment Status](../../doc/controllers/payments.md#refresh-payment-status)
* [Create Order Request](../../doc/controllers/payments.md#create-order-request)
* [Create Session Request](../../doc/controllers/payments.md#create-session-request)
* [Update Session Req](../../doc/controllers/payments.md#update-session-req)


# Create Payment

A payment authorizes the amount for the transaction. There are a number of supported payment features, such as E-commerce and Card Present - Credit Card/Debit Card, Echeck, e-Wallets, Level II/III Data, etc..

A payment response includes the status of the request. It also includes processor-specific information when the request is successful and errors if unsuccessful. See the [Payments Developer Guides Page](

Authorization can be requested with Capture, Decision Manager, Payer Authentication(3ds), and Token Creation.

```php
function createPayment(CreatePaymentRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreatePaymentRequest`](../../doc/models/create-payment-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type `array`.

## Example Usage

```php
$body = CreatePaymentRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformationBuilder::init()
            ->code('TC50171_3')
            ->build()
    )
    ->paymentInformation(
        PaymentInformationBuilder::init()
            ->card(
                CardBuilder::init()
                    ->number('4111111111111111')
                    ->expirationMonth('12')
                    ->expirationYear('2031')
                    ->build()
            )
            ->build()
    )
    ->orderInformation(
        OrderInformationBuilder::init()
            ->amountDetails(
                AmountDetailsBuilder::init()
                    ->totalAmount('102.21')
                    ->currency('USD')
                    ->build()
            )
            ->billTo(
                BillToBuilder::init()
                    ->firstName('John')
                    ->lastName('Doe')
                    ->address1('1 Market St')
                    ->locality('san francisco')
                    ->administrativeArea('CA')
                    ->postalCode('94105')
                    ->country('US')
                    ->email('test@cybs.com')
                    ->phoneNumber('4158880000')
                    ->build()
            )
            ->build()
    )
    ->build();

$paymentsApi = $client->getPaymentsApi();
$apiResponse = $paymentsApi->createPayment($body);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'array:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | `ApiException` |
| 502 | Unexpected system error or system timeout. | `ApiException` |


# Increment Auth

Use this service to authorize additional charges in a lodging or autorental transaction. Include the ID returned from the original authorization in the PATCH request to add additional charges to that authorization.

```php
function incrementAuth(string $id, IncrementAuthRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID returned from the original authorization request. |
| `body` | [`IncrementAuthRequest`](../../doc/models/increment-auth-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2IncrementalAuthorizationPatch201Response`](../../doc/models/pts-v2-incremental-authorization-patch-201-response.md).

## Example Usage

```php
$id = 'id0';

$body = IncrementAuthRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformation2Builder::init()
            ->code('TC50171_3')
            ->build()
    )
    ->processingInformation(
        ProcessingInformation2Builder::init()
            ->authorizationOptions(
                AuthorizationOptions3Builder::init()
                    ->initiator(
                        Initiator1Builder::init()
                            ->storedCredentialUsed(true)
                            ->build()
                    )
                    ->build()
            )
            ->build()
    )
    ->orderInformation(
        OrderInformation2Builder::init()
            ->amountDetails(
                AmountDetails3Builder::init()
                    ->additionalAmount('22.49')
                    ->currency('USD')
                    ->build()
            )
            ->build()
    )
    ->merchantInformation(
        MerchantInformation2Builder::init()
            ->transactionLocalDateTime('20191002080000')
            ->build()
    )
    ->travelInformation(
        TravelInformation1Builder::init()
            ->duration('4')
            ->build()
    )
    ->build();

$paymentsApi = $client->getPaymentsApi();
$apiResponse = $paymentsApi->incrementAuth(
    $id,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2IncrementalAuthorizationPatch201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2IncrementalAuthorizationPatch400Response1Exception`](../../doc/models/pts-v2-incremental-authorization-patch-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2IncrementalAuthorizationPatch502Response1Exception`](../../doc/models/pts-v2-incremental-authorization-patch-502-response-1-exception.md) |


# Refresh Payment Status

Checks and updates the payment status

```php
function refreshPaymentStatus(string $id, RefreshPaymentStatusRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The payment id whose status needs to be checked and updated. |
| `body` | [`RefreshPaymentStatusRequest`](../../doc/models/refresh-payment-status-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2PaymentsPost201Response1`](../../doc/models/pts-v2-payments-post-201-response-1.md).

## Example Usage

```php
$id = 'id0';

$body = RefreshPaymentStatusRequestBuilder::init()->build();

$paymentsApi = $client->getPaymentsApi();
$apiResponse = $paymentsApi->refreshPaymentStatus(
    $id,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2PaymentsPost201Response1:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2PaymentsPost400Response11Exception`](../../doc/models/pts-v2-payments-post-400-response-11-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2PaymentsPost502Response11Exception`](../../doc/models/pts-v2-payments-post-502-response-11-exception.md) |


# Create Order Request

Create a Payment Order Request

```php
function createOrderRequest(string $id, OrderPaymentRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | Request identifier number for the order request. |
| `body` | [`OrderPaymentRequest`](../../doc/models/order-payment-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2PaymentsOrderPost201Response`](../../doc/models/pts-v2-payments-order-post-201-response.md).

## Example Usage

```php
$id = 'id0';

$body = OrderPaymentRequestBuilder::init()->build();

$paymentsApi = $client->getPaymentsApi();
$apiResponse = $paymentsApi->createOrderRequest(
    $id,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2PaymentsOrderPost201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2PaymentsPost400Response11Exception`](../../doc/models/pts-v2-payments-post-400-response-11-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2PaymentsPost502Response11Exception`](../../doc/models/pts-v2-payments-post-502-response-11-exception.md) |


# Create Session Request

Create Alternative Payments Sessions Request

```php
function createSessionRequest(CreateSessionReq $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateSessionReq`](../../doc/models/create-session-req.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2PaymentsPost201Response2`](../../doc/models/pts-v2-payments-post-201-response-2.md).

## Example Usage

```php
$body = CreateSessionReqBuilder::init()->build();

$paymentsApi = $client->getPaymentsApi();
$apiResponse = $paymentsApi->createSessionRequest($body);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2PaymentsPost201Response2:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2PaymentsPost400Response11Exception`](../../doc/models/pts-v2-payments-post-400-response-11-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2PaymentsPost502Response11Exception`](../../doc/models/pts-v2-payments-post-502-response-11-exception.md) |


# Update Session Req

Update Alternative Payments Sessions Request

```php
function updateSessionReq(string $id, CreateSessionRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The payment ID. This ID is returned from a previous payment request. |
| `body` | [`CreateSessionRequest`](../../doc/models/create-session-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2PaymentsPost201Response2`](../../doc/models/pts-v2-payments-post-201-response-2.md).

## Example Usage

```php
$id = 'id0';

$body = CreateSessionRequestBuilder::init()->build();

$paymentsApi = $client->getPaymentsApi();
$apiResponse = $paymentsApi->updateSessionReq(
    $id,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2PaymentsPost201Response2:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2PaymentsPost400Response11Exception`](../../doc/models/pts-v2-payments-post-400-response-11-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2PaymentsPost502Response11Exception`](../../doc/models/pts-v2-payments-post-502-response-11-exception.md) |

