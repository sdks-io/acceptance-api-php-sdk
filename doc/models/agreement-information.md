
# Agreement Information

*This model accepts additional fields of type array.*

## Structure

`AgreementInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `agreementId` | `?string` | Optional | Identifier for the mandate being signed for. This mandate id is required for all the subsequent transactions. | getAgreementId(): ?string | setAgreementId(?string agreementId): void |
| `id` | `?string` | Optional | The processor specific billing agreement ID. References an approved recurring payment for goods or services. This value is sent by merchant via Visa Acceptance to processor. The value sent in this field is procured by the merchant from the processor.<br><br>**Constraints**: *Maximum Length*: `128` | getId(): ?string | setId(?string id): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AgreementInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$agreementInformation = AgreementInformationBuilder::init()
    ->agreementId('agreementId4')
    ->id('id2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

