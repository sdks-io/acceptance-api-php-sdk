
# Metadata 4

*This model accepts additional fields of type array.*

## Structure

`Metadata4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `creator` | `?string` | Optional, Read-only | The creator of the Shipping Address. | getCreator(): ?string | setCreator(?string creator): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Metadata4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$metadata4 = Metadata4Builder::init()
    ->creator('creator4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

