
# Agreement Information 6

*This model accepts additional fields of type array.*

## Structure

`AgreementInformation6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Identifier for the mandate.<br><br>#### SEPA/BACS<br><br>Required for mandates services<br><br>**Constraints**: *Maximum Length*: `50` | getId(): ?string | setId(?string id): void |
| `dateSigned` | `?string` | Optional | Date the mandate has been signed.  Format YYYYMMdd<br><br>#### SEPA/BACS<br><br>Required for Import Mandate<br><br>**Constraints**: *Maximum Length*: `8` | getDateSigned(): ?string | setDateSigned(?string dateSigned): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AgreementInformation6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$agreementInformation6 = AgreementInformation6Builder::init()
    ->id('id0')
    ->dateSigned('dateSigned0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

