
# Metadata 3

*This model accepts additional fields of type array.*

## Structure

`Metadata3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `creator` | `?string` | Optional, Read-only | The creator of the Instrument Identifier. | getCreator(): ?string | setCreator(?string creator): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Metadata3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$metadata3 = Metadata3Builder::init()
    ->creator('creator4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

