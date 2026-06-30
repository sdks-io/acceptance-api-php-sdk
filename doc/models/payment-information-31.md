
# Payment Information 31

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation31`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentType` | [`?PaymentType22`](../../doc/models/payment-type-22.md) | Optional | - | getPaymentType(): ?PaymentType22 | setPaymentType(?PaymentType22 paymentType): void |
| `customer` | [`?Customer42`](../../doc/models/customer-42.md) | Optional | - | getCustomer(): ?Customer42 | setCustomer(?Customer42 customer): void |
| `card` | [`?Card105`](../../doc/models/card-105.md) | Optional | - | getCard(): ?Card105 | setCard(?Card105 card): void |
| `brands` | [`?(Brand24[])`](../../doc/models/brand-24.md) | Optional | This array contains the supported brands. | getBrands(): ?array | setBrands(?array brands): void |
| `features` | [`?Features24`](../../doc/models/features-24.md) | Optional | - | getFeatures(): ?Features24 | setFeatures(?Features24 features): void |
| `invoice` | [`?Invoice`](../../doc/models/invoice.md) | Optional | - | getInvoice(): ?Invoice | setInvoice(?Invoice invoice): void |
| `network` | [`?Network24`](../../doc/models/network-24.md) | Optional | - | getNetwork(): ?Network24 | setNetwork(?Network24 network): void |
| `issuerInformation` | [`?IssuerInformation30`](../../doc/models/issuer-information-30.md) | Optional | - | getIssuerInformation(): ?IssuerInformation30 | setIssuerInformation(?IssuerInformation30 issuerInformation): void |
| `bank` | [`?Bank13`](../../doc/models/bank-13.md) | Optional | - | getBank(): ?Bank13 | setBank(?Bank13 bank): void |
| `accountFeatures` | [`?AccountFeatures2`](../../doc/models/account-features-2.md) | Optional | - | getAccountFeatures(): ?AccountFeatures2 | setAccountFeatures(?AccountFeatures2 accountFeatures): void |
| `paymentInstrument` | [`?PaymentInstrument4`](../../doc/models/payment-instrument-4.md) | Optional | - | getPaymentInstrument(): ?PaymentInstrument4 | setPaymentInstrument(?PaymentInstrument4 paymentInstrument): void |
| `instrumentIdentifier` | [`?InstrumentIdentifier27`](../../doc/models/instrument-identifier-27.md) | Optional | - | getInstrumentIdentifier(): ?InstrumentIdentifier27 | setInstrumentIdentifier(?InstrumentIdentifier27 instrumentIdentifier): void |
| `shippingAddress` | [`?ShippingAddress4`](../../doc/models/shipping-address-4.md) | Optional | - | getShippingAddress(): ?ShippingAddress4 | setShippingAddress(?ShippingAddress4 shippingAddress): void |
| `fluidData` | [`?FluidData4`](../../doc/models/fluid-data-4.md) | Optional | - | getFluidData(): ?FluidData4 | setFluidData(?FluidData4 fluidData): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation31Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType22Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\Customer42Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Card105Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Brand24Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Features24Builder;

$paymentInformation31 = PaymentInformation31Builder::init()
    ->paymentType(
        PaymentType22Builder::init()
            ->name('name6')
            ->type('type6')
            ->method('method0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->customer(
        Customer42Builder::init()
            ->customerId('customerId4')
            ->id('id0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->card(
        Card105Builder::init()
            ->suffix('suffix4')
            ->prefix('prefix4')
            ->expirationMonth('expirationMonth4')
            ->expirationYear('expirationYear0')
            ->startMonth('startMonth6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->brands(
        [
            Brand24Builder::init()
                ->type('type6')
                ->brandName('brandName0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            Brand24Builder::init()
                ->type('type6')
                ->brandName('brandName0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            Brand24Builder::init()
                ->type('type6')
                ->brandName('brandName0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->features(
        Features24Builder::init()
            ->accountFundingSource('accountFundingSource0')
            ->accountFundingSourceSubType('accountFundingSourceSubType6')
            ->cardProduct('cardProduct8')
            ->messageType('messageType6')
            ->acceptanceLevel('acceptanceLevel8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

