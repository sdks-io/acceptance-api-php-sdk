
# Mit Reversal Request

*This model accepts additional fields of type array.*

## Structure

`MitReversalRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientReferenceInformation` | [`?ClientReferenceInformation`](../../doc/models/client-reference-information.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation | setClientReferenceInformation(?ClientReferenceInformation clientReferenceInformation): void |
| `reversalInformation` | [`?ReversalInformation`](../../doc/models/reversal-information.md) | Optional | - | getReversalInformation(): ?ReversalInformation | setReversalInformation(?ReversalInformation reversalInformation): void |
| `processingInformation` | [`?ProcessingInformation3`](../../doc/models/processing-information-3.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation3 | setProcessingInformation(?ProcessingInformation3 processingInformation): void |
| `orderInformation` | [`?OrderInformation4`](../../doc/models/order-information-4.md) | Optional | - | getOrderInformation(): ?OrderInformation4 | setOrderInformation(?OrderInformation4 orderInformation): void |
| `pointOfSaleInformation` | [`?PointOfSaleInformation2`](../../doc/models/point-of-sale-information-2.md) | Optional | - | getPointOfSaleInformation(): ?PointOfSaleInformation2 | setPointOfSaleInformation(?PointOfSaleInformation2 pointOfSaleInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MitReversalRequestBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ReversalInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails6Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItem1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PointOfSaleInformation2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Emv2Builder;

$mitReversalRequest = MitReversalRequestBuilder::init()
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
    ->reversalInformation(
        ReversalInformationBuilder::init()
            ->amountDetails(
                AmountDetails5Builder::init()
                    ->totalAmount('102.21')
                    ->currency('currency0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->reason('testing')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->processingInformation(
        ProcessingInformation3Builder::init()
            ->paymentSolution('paymentSolution6')
            ->reconciliationId('reconciliationId4')
            ->linkId('linkId8')
            ->reportGroup('reportGroup4')
            ->visaCheckoutId('visaCheckoutId6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->orderInformation(
        OrderInformation4Builder::init()
            ->amountDetails(
                AmountDetails6Builder::init()
                    ->serviceFeeAmount('serviceFeeAmount2')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->lineItems(
                [
                    LineItem1Builder::init()
                        ->quantity(132)
                        ->unitPrice('unitPrice8')
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build()
                ]
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->pointOfSaleInformation(
        PointOfSaleInformation2Builder::init()
            ->emv(
                Emv2Builder::init()
                    ->tags('tags4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

