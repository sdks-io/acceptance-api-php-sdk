
# Self 25

*This model accepts additional fields of type array.*

## Structure

`Self25`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional, Read-only | Link to the card art asset.<br>example: 'tms/v2/tokens/7020000000010603216/visa/assets/icon' | getHref(): ?string | setHref(?string href): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Self25Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$self25 = Self25Builder::init()
    ->href('href4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

