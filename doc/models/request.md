
# Request

*This model accepts additional fields of type array.*

## Structure

`Request`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `processingInformation` | [`?ProcessingInformation27`](../../doc/models/processing-information-27.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation27 | setProcessingInformation(?ProcessingInformation27 processingInformation): void |
| `paymentInformation` | [`?PaymentInformation29`](../../doc/models/payment-information-29.md) | Optional | - | getPaymentInformation(): ?PaymentInformation29 | setPaymentInformation(?PaymentInformation29 paymentInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RequestBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation27Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation29Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedPaymentMethodBuilder;

$request = RequestBuilder::init()
    ->processingInformation(
        ProcessingInformation27Builder::init()
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
        PaymentInformation29Builder::init()
            ->paymentType(
                PaymentType11Builder::init()
                    ->name('name6')
                    ->method(
                        Method2Builder::init()
                            ->name('name6')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->tokenizedPaymentMethod(
                TokenizedPaymentMethodBuilder::init()
                    ->id('id0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

