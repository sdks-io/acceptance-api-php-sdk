
# Payment Information 28

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation28`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentType` | [`?PaymentType19`](../../doc/models/payment-type-19.md) | Optional | - | getPaymentType(): ?PaymentType19 | setPaymentType(?PaymentType19 paymentType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation28Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType19Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method19Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentInformation28 = PaymentInformation28Builder::init()
    ->paymentType(
        PaymentType19Builder::init()
            ->name('name6')
            ->method(
                Method19Builder::init()
                    ->name('name6')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

