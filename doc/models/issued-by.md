
# Issued By

*This model accepts additional fields of type array.*

## Structure

`IssuedBy`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `administrativeArea` | `?string` | Optional | The State or province where the customer’s driver’s license was issued.<br><br>Use the two-character State, Province, and Territory Codes for the United States and Canada.<br><br>**Constraints**: *Maximum Length*: `20` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuedByBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$issuedBy = IssuedByBuilder::init()
    ->administrativeArea('administrativeArea4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

