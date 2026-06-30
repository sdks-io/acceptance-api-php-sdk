
# Self 22

*This model accepts additional fields of type array.*

## Structure

`Self22`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional, Read-only | Link to the card art asset.<br>example: 'tms/v2/tokens/7020000000010603216/visa/assets/card-art-combined' | getHref(): ?string | setHref(?string href): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Self22Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$self22 = Self22Builder::init()
    ->href('href2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

