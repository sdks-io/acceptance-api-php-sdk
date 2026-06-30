# Credit

A credit is a stand-alone transaction that is not linked to any previous transactions. It takes money from
your merchant bank account and returns it to the customer.

```php
$creditApi = $client->getCreditApi();
```

## Class Name

`CreditApi`


# Create Credit

POST to the credit resource to credit funds to a specified credit card.

```php
function createCredit(CreateCreditRequest $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateCreditRequest`](../../doc/models/create-credit-request.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2CreditsPost201Response`](../../doc/models/pts-v2-credits-post-201-response.md).

## Example Usage

```php
$body = CreateCreditRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformationBuilder::init()
            ->code('12345678')
            ->build()
    )
    ->paymentInformation(
        PaymentInformation5Builder::init()
            ->card(
                Card4Builder::init()
                    ->number('4111111111111111')
                    ->expirationMonth('03')
                    ->expirationYear('2031')
                    ->type('001')
                    ->build()
            )
            ->build()
    )
    ->orderInformation(
        OrderInformation8Builder::init()
            ->amountDetails(
                AmountDetails9Builder::init()
                    ->totalAmount('200')
                    ->currency('usd')
                    ->build()
            )
            ->billTo(
                BillTo2Builder::init()
                    ->firstName('Test')
                    ->lastName('test')
                    ->address1('test')
                    ->locality('Ann Arbor')
                    ->administrativeArea('MI')
                    ->postalCode('48104-2201')
                    ->country('US')
                    ->email('test@cybs.com')
                    ->phoneNumber('9999999999')
                    ->build()
            )
            ->build()
    )
    ->build();

$creditApi = $client->getCreditApi();
$apiResponse = $creditApi->createCredit($body);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2CreditsPost201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2CreditsPost400Response1Exception`](../../doc/models/pts-v2-credits-post-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2CreditsPost502Response1Exception`](../../doc/models/pts-v2-credits-post-502-response-1-exception.md) |

