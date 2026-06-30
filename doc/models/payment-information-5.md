
# Payment Information 5

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `card` | [`?Card4`](../../doc/models/card-4.md) | Optional | - | getCard(): ?Card4 | setCard(?Card4 card): void |
| `bank` | [`?Bank2`](../../doc/models/bank-2.md) | Optional | - | getBank(): ?Bank2 | setBank(?Bank2 bank): void |
| `tokenizedCard` | [`?TokenizedCard`](../../doc/models/tokenized-card.md) | Optional | - | getTokenizedCard(): ?TokenizedCard | setTokenizedCard(?TokenizedCard tokenizedCard): void |
| `fluidData` | [`?FluidData`](../../doc/models/fluid-data.md) | Optional | - | getFluidData(): ?FluidData | setFluidData(?FluidData fluidData): void |
| `customer` | [`?Customer`](../../doc/models/customer.md) | Optional | - | getCustomer(): ?Customer | setCustomer(?Customer customer): void |
| `paymentInstrument` | [`?PaymentInstrument`](../../doc/models/payment-instrument.md) | Optional | - | getPaymentInstrument(): ?PaymentInstrument | setPaymentInstrument(?PaymentInstrument paymentInstrument): void |
| `instrumentIdentifier` | [`?InstrumentIdentifier`](../../doc/models/instrument-identifier.md) | Optional | - | getInstrumentIdentifier(): ?InstrumentIdentifier | setInstrumentIdentifier(?InstrumentIdentifier instrumentIdentifier): void |
| `shippingAddress` | [`?ShippingAddress`](../../doc/models/shipping-address.md) | Optional | - | getShippingAddress(): ?ShippingAddress | setShippingAddress(?ShippingAddress shippingAddress): void |
| `legacyToken` | [`?LegacyToken`](../../doc/models/legacy-token.md) | Optional | - | getLegacyToken(): ?LegacyToken | setLegacyToken(?LegacyToken legacyToken): void |
| `paymentType` | [`?PaymentType3`](../../doc/models/payment-type-3.md) | Optional | - | getPaymentType(): ?PaymentType3 | setPaymentType(?PaymentType3 paymentType): void |
| `eWallet` | [`?EWallet2`](../../doc/models/e-wallet-2.md) | Optional | - | getEWallet(): ?EWallet2 | setEWallet(?EWallet2 eWallet): void |
| `paymentAccountReference` | [`?PaymentAccountReference`](../../doc/models/payment-account-reference.md) | Optional | - | getPaymentAccountReference(): ?PaymentAccountReference | setPaymentAccountReference(?PaymentAccountReference paymentAccountReference): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Card4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedCardBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\FluidDataBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\CustomerBuilder;

$paymentInformation5 = PaymentInformation5Builder::init()
    ->card(
        Card4Builder::init()
            ->number('number6')
            ->expirationMonth('expirationMonth4')
            ->expirationYear('expirationYear0')
            ->type('type4')
            ->accountEncoderId('accountEncoderId8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->bank(
        Bank2Builder::init()
            ->account(
                Account3Builder::init()
                    ->type('type0')
                    ->number('number8')
                    ->encoderId('encoderId4')
                    ->checkNumber('checkNumber6')
                    ->checkImageReferenceNumber('checkImageReferenceNumber2')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->routingNumber('routingNumber0')
            ->iban('iban2')
            ->swiftCode('swiftCode0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->tokenizedCard(
        TokenizedCardBuilder::init()
            ->number('number2')
            ->expirationMonth('expirationMonth0')
            ->expirationYear('expirationYear4')
            ->type('type0')
            ->cryptogram('cryptogram0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->fluidData(
        FluidDataBuilder::init()
            ->keySerialNumber('keySerialNumber4')
            ->descriptor('descriptor0')
            ->value('value0')
            ->encoding('encoding0')
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
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

