
# Links

*This model accepts additional fields of type array.*

## Structure

`Links`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?MSelf`](../../doc/models/m-self.md) | Optional | - | getSelf(): ?MSelf | setSelf(?MSelf self): void |
| `reversal` | [`?Reversal1`](../../doc/models/reversal-1.md) | Optional | - | getReversal(): ?Reversal1 | setReversal(?Reversal1 reversal): void |
| `capture` | [`?Capture`](../../doc/models/capture.md) | Optional | - | getCapture(): ?Capture | setCapture(?Capture capture): void |
| `customer` | [`?Customer1`](../../doc/models/customer-1.md) | Optional | - | getCustomer(): ?Customer1 | setCustomer(?Customer1 customer): void |
| `paymentInstrument` | [`?PaymentInstrument2`](../../doc/models/payment-instrument-2.md) | Optional | - | getPaymentInstrument(): ?PaymentInstrument2 | setPaymentInstrument(?PaymentInstrument2 paymentInstrument): void |
| `shippingAddress` | [`?ShippingAddress2`](../../doc/models/shipping-address-2.md) | Optional | - | getShippingAddress(): ?ShippingAddress2 | setShippingAddress(?ShippingAddress2 shippingAddress): void |
| `instrumentIdentifier` | [`?InstrumentIdentifier1`](../../doc/models/instrument-identifier-1.md) | Optional | - | getInstrumentIdentifier(): ?InstrumentIdentifier1 | setInstrumentIdentifier(?InstrumentIdentifier1 instrumentIdentifier): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\LinksBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MSelfBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\Reversal1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\CaptureBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Customer1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInstrument2Builder;

$links = LinksBuilder::init()
    ->self(
        MSelfBuilder::init()
            ->href('href0')
            ->method('method8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->reversal(
        Reversal1Builder::init()
            ->href('href6')
            ->method('method2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->capture(
        CaptureBuilder::init()
            ->href('href2')
            ->method('method6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->customer(
        Customer1Builder::init()
            ->href('href2')
            ->method('method6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInstrument(
        PaymentInstrument2Builder::init()
            ->href('href2')
            ->method('method6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

