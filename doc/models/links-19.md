
# Links 19

*This model accepts additional fields of type array.*

## Structure

`Links19`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?Self18`](../../doc/models/self-18.md) | Optional, Read-only | - | getSelf(): ?Self18 | setSelf(?Self18 self): void |
| `paymentInstruments` | [`?PaymentInstruments`](../../doc/models/payment-instruments.md) | Optional, Read-only | - | getPaymentInstruments(): ?PaymentInstruments | setPaymentInstruments(?PaymentInstruments paymentInstruments): void |
| `shippingAddress` | [`?ShippingAddress11`](../../doc/models/shipping-address-11.md) | Optional, Read-only | - | getShippingAddress(): ?ShippingAddress11 | setShippingAddress(?ShippingAddress11 shippingAddress): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links19Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self18Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInstrumentsBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShippingAddress11Builder;

$links19 = Links19Builder::init()
    ->self(
        Self18Builder::init()
            ->href('href0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInstruments(
        PaymentInstrumentsBuilder::init()
            ->href('href0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shippingAddress(
        ShippingAddress11Builder::init()
            ->href('href0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

