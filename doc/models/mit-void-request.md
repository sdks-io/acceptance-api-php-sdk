
# Mit Void Request

*This model accepts additional fields of type array.*

## Structure

`MitVoidRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientReferenceInformation` | [`?ClientReferenceInformation`](../../doc/models/client-reference-information.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation | setClientReferenceInformation(?ClientReferenceInformation clientReferenceInformation): void |
| `paymentInformation` | [`?PaymentInformation9`](../../doc/models/payment-information-9.md) | Optional | - | getPaymentInformation(): ?PaymentInformation9 | setPaymentInformation(?PaymentInformation9 paymentInformation): void |
| `orderInformation` | [`?OrderInformation14`](../../doc/models/order-information-14.md) | Optional | - | getOrderInformation(): ?OrderInformation14 | setOrderInformation(?OrderInformation14 orderInformation): void |
| `processingInformation` | [`?ProcessingInformation17`](../../doc/models/processing-information-17.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation17 | setProcessingInformation(?ProcessingInformation17 processingInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MitVoidRequestBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation14Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation17Builder;

$mitVoidRequest = MitVoidRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformationBuilder::init()
            ->code('code4')
            ->reconciliationId('reconciliationId2')
            ->pausedRequestId('pausedRequestId2')
            ->transactionId('')
            ->comments('comments2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInformation(
        PaymentInformation9Builder::init()
            ->paymentType(
                PaymentType3Builder::init()
                    ->name('name6')
                    ->subTypeName('subTypeName0')
                    ->method(
                        Method2Builder::init()
                            ->name('name6')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->orderInformation(
        OrderInformation14Builder::init()
            ->amountDetails(
                AmountDetails5Builder::init()
                    ->totalAmount('totalAmount4')
                    ->currency('currency0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->processingInformation(
        ProcessingInformation17Builder::init()
            ->paymentId('paymentId4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

