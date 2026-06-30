
# Get Payment Instrument Response

*This model accepts additional fields of type array.*

## Structure

`GetPaymentInstrumentResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?Links20`](../../doc/models/links-20.md) | Optional, Read-only | - | getLinks(): ?Links20 | setLinks(?Links20 links): void |
| `id` | `?string` | Optional | The Id of the Payment Instrument Token.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` | getId(): ?string | setId(?string id): void |
| `object` | `?string` | Optional, Read-only | The type.<br><br>Possible Values:<br><br>- paymentInstrument | getObject(): ?string | setObject(?string object): void |
| `default` | `?bool` | Optional | Flag that indicates whether customer payment instrument is the dafault.<br>Possible Values:<br><br>- `true`: Payment instrument is customer's default.<br>- `false`: Payment instrument is not customer's default. | getDefault(): ?bool | setDefault(?bool default): void |
| `state` | `?string` | Optional, Read-only | Issuers state for the card number.<br>Possible Values:<br><br>- ACTIVE<br>- CLOSED : The account has been closed. | getState(): ?string | setState(?string state): void |
| `type` | `?string` | Optional, Read-only | The type of Payment Instrument.<br>Possible Values:<br><br>- cardHash | getType(): ?string | setType(?string type): void |
| `bankAccount` | [`?BankAccount`](../../doc/models/bank-account.md) | Optional | - | getBankAccount(): ?BankAccount | setBankAccount(?BankAccount bankAccount): void |
| `card` | [`?Card12`](../../doc/models/card-12.md) | Optional | - | getCard(): ?Card12 | setCard(?Card12 card): void |
| `buyerInformation` | [`?BuyerInformation13`](../../doc/models/buyer-information-13.md) | Optional | - | getBuyerInformation(): ?BuyerInformation13 | setBuyerInformation(?BuyerInformation13 buyerInformation): void |
| `billTo` | [`?BillTo15`](../../doc/models/bill-to-15.md) | Optional | - | getBillTo(): ?BillTo15 | setBillTo(?BillTo15 billTo): void |
| `processingInformation` | [`?TmsPaymentInstrumentProcessingInfo`](../../doc/models/tms-payment-instrument-processing-info.md) | Optional | - | getProcessingInformation(): ?TmsPaymentInstrumentProcessingInfo | setProcessingInformation(?TmsPaymentInstrumentProcessingInfo processingInformation): void |
| `merchantInformation` | [`?MerchantInformation18`](../../doc/models/merchant-information-18.md) | Optional | - | getMerchantInformation(): ?MerchantInformation18 | setMerchantInformation(?MerchantInformation18 merchantInformation): void |
| `instrumentIdentifier` | [`?InstrumentIdentifier10`](../../doc/models/instrument-identifier-10.md) | Optional | - | getInstrumentIdentifier(): ?InstrumentIdentifier10 | setInstrumentIdentifier(?InstrumentIdentifier10 instrumentIdentifier): void |
| `metadata` | [`?Metadata1`](../../doc/models/metadata-1.md) | Optional, Read-only | - | getMetadata(): ?Metadata1 | setMetadata(?Metadata1 metadata): void |
| `embedded` | [`?Embedded9`](../../doc/models/embedded-9.md) | Optional, Read-only | - | getEmbedded(): ?Embedded9 | setEmbedded(?Embedded9 embedded): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\GetPaymentInstrumentResponseBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links20Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self19Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self18Builder;

$getPaymentInstrumentResponse = GetPaymentInstrumentResponseBuilder::init()
    ->links(
        Links20Builder::init()
            ->self(
                Self19Builder::init()
                    ->href('href0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->customer(
                Self18Builder::init()
                    ->href('href2')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->id('id2')
    ->object('paymentInstrument')
    ->default(false)
    ->state('ACTIVE')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

