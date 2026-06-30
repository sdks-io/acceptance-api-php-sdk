
# Error Information 2

*This model accepts additional fields of type array.*

## Structure

`ErrorInformation2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `?string` | Optional | - | getReason(): ?string | setReason(?string reason): void |
| `message` | `?string` | Optional | - | getMessage(): ?string | setMessage(?string message): void |
| `details` | [`?(Detail15[])`](../../doc/models/detail-15.md) | Optional | - | getDetails(): ?array | setDetails(?array details): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ErrorInformation2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Detail15Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$errorInformation2 = ErrorInformation2Builder::init()
    ->reason('reason0')
    ->message('message4')
    ->details(
        [
            Detail15Builder::init()
                ->field('field4')
                ->message('message0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

