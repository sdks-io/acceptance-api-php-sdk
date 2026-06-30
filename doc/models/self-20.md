
# Self 20

*This model accepts additional fields of type array.*

## Structure

`Self20`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional, Read-only | Link to the Instrument Identifier. | getHref(): ?string | setHref(?string href): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Self20Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$self20 = Self20Builder::init()
    ->href('tms/v1/instrumentidentifiers/7010000000016241111')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

