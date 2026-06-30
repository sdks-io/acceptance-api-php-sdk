
# Self 21

*This model accepts additional fields of type array.*

## Structure

`Self21`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional, Read-only | Link to the Tokenized Card.<br>example: 'tms/v2/tokenized-cards/7010000000016241111' | getHref(): ?string | setHref(?string href): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Self21Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$self21 = Self21Builder::init()
    ->href('href0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

