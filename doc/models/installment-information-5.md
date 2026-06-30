
# Installment Information 5

*This model accepts additional fields of type array.*

## Structure

`InstallmentInformation5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `identifier` | `?string` | Optional | Identifier<br><br>**Constraints**: *Maximum Length*: `100` | getIdentifier(): ?string | setIdentifier(?string identifier): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InstallmentInformation5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$installmentInformation5 = InstallmentInformation5Builder::init()
    ->identifier('identifier8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

