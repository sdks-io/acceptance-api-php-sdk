
# Links 21

*This model accepts additional fields of type array.*

## Structure

`Links21`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?Self20`](../../doc/models/self-20.md) | Optional, Read-only | - | getSelf(): ?Self20 | setSelf(?Self20 self): void |
| `paymentInstruments` | [`?PaymentInstruments1`](../../doc/models/payment-instruments-1.md) | Optional, Read-only | - | getPaymentInstruments(): ?PaymentInstruments1 | setPaymentInstruments(?PaymentInstruments1 paymentInstruments): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links21Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self20Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInstruments1Builder;

$links21 = Links21Builder::init()
    ->self(
        Self20Builder::init()
            ->href('href0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInstruments(
        PaymentInstruments1Builder::init()
            ->href('href0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

