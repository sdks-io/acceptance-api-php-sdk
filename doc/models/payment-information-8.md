
# Payment Information 8

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation8`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bank` | [`?Bank1`](../../doc/models/bank-1.md) | Optional | - | getBank(): ?Bank1 | setBank(?Bank1 bank): void |
| `customer` | [`?Customer`](../../doc/models/customer.md) | Optional | - | getCustomer(): ?Customer | setCustomer(?Customer customer): void |
| `paymentInstrument` | [`?PaymentInstrument`](../../doc/models/payment-instrument.md) | Optional | - | getPaymentInstrument(): ?PaymentInstrument | setPaymentInstrument(?PaymentInstrument paymentInstrument): void |
| `instrumentIdentifier` | [`?InstrumentIdentifier2`](../../doc/models/instrument-identifier-2.md) | Optional | - | getInstrumentIdentifier(): ?InstrumentIdentifier2 | setInstrumentIdentifier(?InstrumentIdentifier2 instrumentIdentifier): void |
| `shippingAddress` | [`?ShippingAddress`](../../doc/models/shipping-address.md) | Optional | - | getShippingAddress(): ?ShippingAddress | setShippingAddress(?ShippingAddress shippingAddress): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation8Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\CustomerBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInstrumentBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\InstrumentIdentifier2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShippingAddressBuilder;

$paymentInformation8 = PaymentInformation8Builder::init()
    ->bank(
        Bank1Builder::init()
            ->account(
                Account2Builder::init()
                    ->correctedAccountNumber('correctedAccountNumber4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->correctedRoutingNumber('correctedRoutingNumber0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->customer(
        CustomerBuilder::init()
            ->customerId('customerId4')
            ->id('id0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInstrument(
        PaymentInstrumentBuilder::init()
            ->id('id0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->instrumentIdentifier(
        InstrumentIdentifier2Builder::init()
            ->id('id4')
            ->state('state0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shippingAddress(
        ShippingAddressBuilder::init()
            ->id('id8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

