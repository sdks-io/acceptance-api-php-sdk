
# Metadata 1

*This model accepts additional fields of type array.*

## Structure

`Metadata1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `creator` | `?string` | Optional, Read-only | The creator of the Payment Instrument. | getCreator(): ?string | setCreator(?string creator): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Metadata1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$metadata1 = Metadata1Builder::init()
    ->creator('creator4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

