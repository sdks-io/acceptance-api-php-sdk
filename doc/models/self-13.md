
# Self 13

*This model accepts additional fields of type array.*

## Structure

`Self13`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional | - | getHref(): ?string | setHref(?string href): void |
| `method` | `?string` | Optional | - | getMethod(): ?string | setMethod(?string method): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Self13Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$self13 = Self13Builder::init()
    ->href('/pts/v1/transaction-batches')
    ->method('GET')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

