
# Token Information 2

*This model accepts additional fields of type array.*

## Structure

`TokenInformation2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customer` | [`?Customer4`](../../doc/models/customer-4.md) | Optional | - | getCustomer(): ?Customer4 | setCustomer(?Customer4 customer): void |
| `paymentInstrument` | [`?PaymentInstrument4`](../../doc/models/payment-instrument-4.md) | Optional | - | getPaymentInstrument(): ?PaymentInstrument4 | setPaymentInstrument(?PaymentInstrument4 paymentInstrument): void |
| `shippingAddress` | [`?ShippingAddress4`](../../doc/models/shipping-address-4.md) | Optional | - | getShippingAddress(): ?ShippingAddress4 | setShippingAddress(?ShippingAddress4 shippingAddress): void |
| `instrumentIdentifier` | [`?InstrumentIdentifier27`](../../doc/models/instrument-identifier-27.md) | Optional | - | getInstrumentIdentifier(): ?InstrumentIdentifier27 | setInstrumentIdentifier(?InstrumentIdentifier27 instrumentIdentifier): void |
| `jti` | `?string` | Optional | TMS Transient Token, 64 hexadecimal id value representing captured payment credentials (including Sensitive Authentication Data, e.g. CVV). | getJti(): ?string | setJti(?string jti): void |
| `transientTokenJwt` | `?string` | Optional | Flex API Transient Token encoded as JWT (JSON Web Token), e.g. Flex microform or Unified Payment checkout result. | getTransientTokenJwt(): ?string | setTransientTokenJwt(?string transientTokenJwt): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenInformation2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Customer4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInstrument4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShippingAddress4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\InstrumentIdentifier27Builder;

$tokenInformation2 = TokenInformation2Builder::init()
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
        InstrumentIdentifier27Builder::init()
            ->id('id4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->jti('jti2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

