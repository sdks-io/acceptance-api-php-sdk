
# Order Payment Request

*This model accepts additional fields of type array.*

## Structure

`OrderPaymentRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientReferenceInformation` | [`?ClientReferenceInformation3`](../../doc/models/client-reference-information-3.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation3 | setClientReferenceInformation(?ClientReferenceInformation3 clientReferenceInformation): void |
| `processingInformation` | [`?ProcessingInformation21`](../../doc/models/processing-information-21.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation21 | setProcessingInformation(?ProcessingInformation21 processingInformation): void |
| `paymentInformation` | [`?PaymentInformation20`](../../doc/models/payment-information-20.md) | Optional | - | getPaymentInformation(): ?PaymentInformation20 | setPaymentInformation(?PaymentInformation20 paymentInformation): void |
| `orderInformation` | [`?OrderInformation24`](../../doc/models/order-information-24.md) | Optional | - | getOrderInformation(): ?OrderInformation24 | setOrderInformation(?OrderInformation24 orderInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderPaymentRequestBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation21Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation20Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet7Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation24Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails26Builder;

$orderPaymentRequest = OrderPaymentRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformation3Builder::init()
            ->code('code4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->processingInformation(
        ProcessingInformation21Builder::init()
            ->actionList(
                [
                    'actionList3',
                    'actionList4'
                ]
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInformation(
        PaymentInformation20Builder::init()
            ->paymentType(
                PaymentType1Builder::init()
                    ->method(
                        Method1Builder::init()
                            ->name('name6')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->eWallet(
                EWallet7Builder::init()
                    ->accountId('accountId4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->orderInformation(
        OrderInformation24Builder::init()
            ->amountDetails(
                AmountDetails26Builder::init()
                    ->totalAmount('totalAmount4')
                    ->currency('currency0')
                    ->subTotalAmount('subTotalAmount0')
                    ->handlingAmount('handlingAmount2')
                    ->shippingAmount('shippingAmount6')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

