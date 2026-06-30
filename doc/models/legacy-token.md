
# Legacy Token

*This model accepts additional fields of type array.*

## Structure

`LegacyToken`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Unique identifier for the legacy Secure Storage token used in the transaction.<br>When you include this value in your request, many of the fields that are normally required for an authorization or credit<br>become optional.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` | getId(): ?string | setId(?string id): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\LegacyTokenBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$legacyToken = LegacyTokenBuilder::init()
    ->id('id4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

