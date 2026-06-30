
# Payment Information

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `card` | [`?Card`](../../doc/models/card.md) | Optional | - | getCard(): ?Card | setCard(?Card card): void |
| `tokenizedCard` | [`?TokenizedCard`](../../doc/models/tokenized-card.md) | Optional | - | getTokenizedCard(): ?TokenizedCard | setTokenizedCard(?TokenizedCard tokenizedCard): void |
| `tokenizedPaymentMethod` | [`?TokenizedPaymentMethod`](../../doc/models/tokenized-payment-method.md) | Optional | - | getTokenizedPaymentMethod(): ?TokenizedPaymentMethod | setTokenizedPaymentMethod(?TokenizedPaymentMethod tokenizedPaymentMethod): void |
| `directDebit` | [`?DirectDebit`](../../doc/models/direct-debit.md) | Optional | - | getDirectDebit(): ?DirectDebit | setDirectDebit(?DirectDebit directDebit): void |
| `fluidData` | [`?FluidData`](../../doc/models/fluid-data.md) | Optional | - | getFluidData(): ?FluidData | setFluidData(?FluidData fluidData): void |
| `customer` | [`?Customer`](../../doc/models/customer.md) | Optional | - | getCustomer(): ?Customer | setCustomer(?Customer customer): void |
| `paymentInstrument` | [`?PaymentInstrument`](../../doc/models/payment-instrument.md) | Optional | - | getPaymentInstrument(): ?PaymentInstrument | setPaymentInstrument(?PaymentInstrument paymentInstrument): void |
| `instrumentIdentifier` | [`?InstrumentIdentifier`](../../doc/models/instrument-identifier.md) | Optional | - | getInstrumentIdentifier(): ?InstrumentIdentifier | setInstrumentIdentifier(?InstrumentIdentifier instrumentIdentifier): void |
| `shippingAddress` | [`?ShippingAddress`](../../doc/models/shipping-address.md) | Optional | - | getShippingAddress(): ?ShippingAddress | setShippingAddress(?ShippingAddress shippingAddress): void |
| `legacyToken` | [`?LegacyToken`](../../doc/models/legacy-token.md) | Optional | - | getLegacyToken(): ?LegacyToken | setLegacyToken(?LegacyToken legacyToken): void |
| `bank` | [`?Bank`](../../doc/models/bank.md) | Optional | - | getBank(): ?Bank | setBank(?Bank bank): void |
| `options` | [`?Options`](../../doc/models/options.md) | Optional | - | getOptions(): ?Options | setOptions(?Options options): void |
| `paymentType` | [`?PaymentType`](../../doc/models/payment-type.md) | Optional | - | getPaymentType(): ?PaymentType | setPaymentType(?PaymentType paymentType): void |
| `initiationChannel` | `?string` | Optional | Mastercard-defined code that indicates how the account information was obtained.<br><br>- `00`: Card<br>- `01`: Mobile Network Operator (MNO) controlled removable secure element (SIM or UICC) personalized for use with a mobile phone or smartphone<br>- `02`: Key fob<br>- `03`: Watch using a contactless chip or a fixed (non-removable) secure element not controlled by the MNO<br>- `04`: Mobile tag<br>- `05`: Wristband<br>- `06`: Mobile phone case or sleeve<br>- `07`: Mobile phone or smartphone with a fixed (non-removable) secure element controlled by the MNO,for example, code division multiple access (CDMA)<br>- `08`: Removable secure element not controlled by the MNO, for example, memory card personalized forused with a mobile phone or smartphone<br>- `09`: Mobile Phone or smartphone with a fixed (non-removable) secure element not controlled by the MNO<br>- `10`: MNO controlled removable secure element (SIM or UICC) personalized for use with a tablet or e-book<br>- `11`: Tablet or e-book with a fixed (non-removable) secure element controlled by the MNO<br>- `12`: Removable secure element not controlled by the MNO, for example, memory card personalized foruse with a tablet or e-book<br>- `13`: Tablet or e-book with fixed (non-removable) secure element not controlled by the MNO<br>- `14`: Mobile phone or smartphone with a payment application running in a host processor<br>- `15`: Tablet or e-book with a payment application running in a host processor<br>- `16`: Mobile phone or smartphone with a payment application running in the Trusted ExecutionEnvironment (TEE) of a host processor<br>- `17`: Tablet or e-book with a payment application running in the TEE of a host processor<br>- `18`: Watch with a payment application running in the TEE of a host processor<br>- `19`: Watch with a payment application running in a host processor<br><br>Values from 20–99 exclusively indicate the form factor only without also indicating the storage technology<br><br>- `20`: Card<br>- `21`: Phone e.g. Mobile Phone<br>- `22`: Tablet/e-reader<br>- `23`: Watch/Wristband e.g. Watch or wristband, including a fitness band, smart strap, disposable band, watch add-on, and security/ID band<br>- `24`: Sticker<br>- `25`: PC<br>- `26`: Device Peripheral e.g. mobile phone case or sleeve<br>- `27`: Tag e.g. key fob or mobile tag<br>- `28`: Jewelry e.g. ring, bracelet, necklace and cuff links<br>- `29`: Fashion Accessory e.g. handbag, bag charm and glasses<br>- `30`: Garment e.g. dress<br>- `31`: Domestic Appliance e.g refrigerator, washing machine<br>- `32`: Vehicle e.g. vehicle, including vehicle attached devices<br>- `33`: Media/Gaming Device e.g. media or gaming device, including a set top box, media player and television<br><br>34–99 are reserved for future form factors. Any value in this range may occur within form factor and transaction data without prior notice.<br><br>This field is supported only for Mastercard on Visa Acceptance through VisaNet.<br>When initiation channel is not provided via this API field, the value is extracted from EMV tag 9F6E for Mastercard transactions. To enable this feature please call support.<br><br>#### Used by<br><br>**Authorization**<br>Optional field.<br><br>**Constraints**: *Maximum Length*: `2` | getInitiationChannel(): ?string | setInitiationChannel(?string initiationChannel): void |
| `sepa` | [`?Sepa`](../../doc/models/sepa.md) | Optional | - | getSepa(): ?Sepa | setSepa(?Sepa sepa): void |
| `eWallet` | [`?EWallet`](../../doc/models/e-wallet.md) | Optional | - | getEWallet(): ?EWallet | setEWallet(?EWallet eWallet): void |
| `paymentAccountReference` | [`?PaymentAccountReference`](../../doc/models/payment-account-reference.md) | Optional | - | getPaymentAccountReference(): ?PaymentAccountReference | setPaymentAccountReference(?PaymentAccountReference paymentAccountReference): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\CardBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedCardBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedPaymentMethodBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\DirectDebitBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MandateBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\FluidDataBuilder;

$paymentInformation = PaymentInformationBuilder::init()
    ->card(
        CardBuilder::init()
            ->number('number6')
            ->expirationMonth('expirationMonth4')
            ->expirationYear('expirationYear0')
            ->type('type4')
            ->useAs('useAs8')
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
    ->tokenizedPaymentMethod(
        TokenizedPaymentMethodBuilder::init()
            ->id('id0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->directDebit(
        DirectDebitBuilder::init()
            ->mandate(
                MandateBuilder::init()
                    ->clearingDate('clearingDate6')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
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
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

