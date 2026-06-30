
# Post Instrument Identifier Enrollment Request

*This model accepts additional fields of type array.*

## Structure

`PostInstrumentIdentifierEnrollmentRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?Links21`](../../doc/models/links-21.md) | Optional, Read-only | - | getLinks(): ?Links21 | setLinks(?Links21 links): void |
| `id` | `?string` | Optional | The Id of the Instrument Identifier Token. | getId(): ?string | setId(?string id): void |
| `object` | `?string` | Optional, Read-only | The type.<br><br>Possible Values:<br><br>- instrumentIdentifier | getObject(): ?string | setObject(?string object): void |
| `state` | `?string` | Optional, Read-only | Issuers state for the card number.<br>Possible Values:<br><br>- ACTIVE<br>- CLOSED : The account has been closed. | getState(): ?string | setState(?string state): void |
| `type` | `?string` | Optional | The type of Instrument Identifier.<br>Possible Values:<br><br>- enrollable card<br>- enrollable token | getType(): ?string | setType(?string type): void |
| `tokenProvisioningInformation` | [`?TokenProvisioningInformation`](../../doc/models/token-provisioning-information.md) | Optional | - | getTokenProvisioningInformation(): ?TokenProvisioningInformation | setTokenProvisioningInformation(?TokenProvisioningInformation tokenProvisioningInformation): void |
| `card` | [`?Card2`](../../doc/models/card-2.md) | Optional | - | getCard(): ?Card2 | setCard(?Card2 card): void |
| `bankAccount` | [`?BankAccount1`](../../doc/models/bank-account-1.md) | Optional | - | getBankAccount(): ?BankAccount1 | setBankAccount(?BankAccount1 bankAccount): void |
| `tokenizedCard` | [`?Tmsv2TokenizedCard`](../../doc/models/tmsv-2-tokenized-card.md) | Optional | - | getTokenizedCard(): ?Tmsv2TokenizedCard | setTokenizedCard(?Tmsv2TokenizedCard tokenizedCard): void |
| `issuer` | [`?Issuer4`](../../doc/models/issuer-4.md) | Optional, Read-only | - | getIssuer(): ?Issuer4 | setIssuer(?Issuer4 issuer): void |
| `processingInformation` | [`?ProcessingInformation28`](../../doc/models/processing-information-28.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation28 | setProcessingInformation(?ProcessingInformation28 processingInformation): void |
| `billTo` | [`?BillTo3`](../../doc/models/bill-to-3.md) | Optional | - | getBillTo(): ?BillTo3 | setBillTo(?BillTo3 billTo): void |
| `metadata` | [`?Metadata3`](../../doc/models/metadata-3.md) | Optional, Read-only | - | getMetadata(): ?Metadata3 | setMetadata(?Metadata3 metadata): void |
| `embedded` | [`?Embedded2`](../../doc/models/embedded-2.md) | Optional, Read-only | - | getEmbedded(): ?Embedded2 | setEmbedded(?Embedded2 embedded): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PostInstrumentIdentifierEnrollmentRequestBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links21Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self20Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInstruments1Builder;

$postInstrumentIdentifierEnrollmentRequest = PostInstrumentIdentifierEnrollmentRequestBuilder::init()
    ->links(
        Links21Builder::init()
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
            ->build()
    )
    ->id('id8')
    ->object('instrumentIdentifier')
    ->state('ACTIVE')
    ->type('type2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

