
# Payment Information 9

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation9`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentType` | [`?PaymentType3`](../../doc/models/payment-type-3.md) | Optional | - | getPaymentType(): ?PaymentType3 | setPaymentType(?PaymentType3 paymentType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentInformation9 = PaymentInformation9Builder::init()
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
    ->build();
```

