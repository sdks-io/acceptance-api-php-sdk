
# Payment Information 29

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation29`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentType` | [`?PaymentType11`](../../doc/models/payment-type-11.md) | Optional | - | getPaymentType(): ?PaymentType11 | setPaymentType(?PaymentType11 paymentType): void |
| `tokenizedPaymentMethod` | [`?TokenizedPaymentMethod`](../../doc/models/tokenized-payment-method.md) | Optional | - | getTokenizedPaymentMethod(): ?TokenizedPaymentMethod | setTokenizedPaymentMethod(?TokenizedPaymentMethod tokenizedPaymentMethod): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation29Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedPaymentMethodBuilder;

$paymentInformation29 = PaymentInformation29Builder::init()
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
    ->build();
```

