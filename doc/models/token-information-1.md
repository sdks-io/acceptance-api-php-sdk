
# Token Information 1

*This model accepts additional fields of type array.*

## Structure

`TokenInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `instrumentidentifierNew` | `?bool` | Optional | A value of true means the card number or bank account used to create an Instrument Identifier was new and did not already exist in the token vault.<br>A value of false means the card number or bank account used to create an Instrument Identifier already existed in the token vault. | getInstrumentidentifierNew(): ?bool | setInstrumentidentifierNew(?bool instrumentidentifierNew): void |
| `customer` | [`?Customer4`](../../doc/models/customer-4.md) | Optional | - | getCustomer(): ?Customer4 | setCustomer(?Customer4 customer): void |
| `paymentInstrument` | [`?PaymentInstrument4`](../../doc/models/payment-instrument-4.md) | Optional | - | getPaymentInstrument(): ?PaymentInstrument4 | setPaymentInstrument(?PaymentInstrument4 paymentInstrument): void |
| `shippingAddress` | [`?ShippingAddress4`](../../doc/models/shipping-address-4.md) | Optional | - | getShippingAddress(): ?ShippingAddress4 | setShippingAddress(?ShippingAddress4 shippingAddress): void |
| `instrumentIdentifier` | [`?InstrumentIdentifier3`](../../doc/models/instrument-identifier-3.md) | Optional | - | getInstrumentIdentifier(): ?InstrumentIdentifier3 | setInstrumentIdentifier(?InstrumentIdentifier3 instrumentIdentifier): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenInformation1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Customer4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInstrument4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShippingAddress4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\InstrumentIdentifier3Builder;

$tokenInformation1 = TokenInformation1Builder::init()
    ->instrumentidentifierNew(false)
    ->customer(
        Customer4Builder::init()
            ->id('id0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInstrument(
        PaymentInstrument4Builder::init()
            ->id('id0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shippingAddress(
        ShippingAddress4Builder::init()
            ->id('id8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->instrumentIdentifier(
        InstrumentIdentifier3Builder::init()
            ->id('id4')
            ->state('state0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

