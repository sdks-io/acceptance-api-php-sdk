
# Payment Information 3

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentType` | [`?PaymentType1`](../../doc/models/payment-type-1.md) | Optional | - | getPaymentType(): ?PaymentType1 | setPaymentType(?PaymentType1 paymentType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentInformation3 = PaymentInformation3Builder::init()
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
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

