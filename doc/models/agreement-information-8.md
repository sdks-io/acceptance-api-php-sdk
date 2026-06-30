
# Agreement Information 8

*This model accepts additional fields of type array.*

## Structure

`AgreementInformation8`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Identifier for the mandate.<br><br>#### SEPA/BACS<br><br>Required for mandates services<br><br>**Constraints**: *Maximum Length*: `50` | getId(): ?string | setId(?string id): void |
| `eSignIndicator` | `?string` | Optional | **Constraints**: *Maximum Length*: `1` | getESignIndicator(): ?string | setESignIndicator(?string eSignIndicator): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AgreementInformation8Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$agreementInformation8 = AgreementInformation8Builder::init()
    ->id('id6')
    ->eSignIndicator('eSignIndicator0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

