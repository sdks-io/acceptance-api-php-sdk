
# Issuer

*This model accepts additional fields of type array.*

## Structure

`Issuer`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `discretionaryData` | `?string` | Optional | Data defined by the issuer.<br><br>The value for this reply field will probably be the same as the value that you submitted in the authorization request, but it is possible for the processor, issuer, or acquirer to modify the value.<br><br>This field is supported only for Visa transactions on **Visa Acceptance through VisaNet**.<br><br>**Constraints**: *Maximum Length*: `255` | getDiscretionaryData(): ?string | setDiscretionaryData(?string discretionaryData): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuerBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$issuer = IssuerBuilder::init()
    ->discretionaryData('discretionaryData4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

