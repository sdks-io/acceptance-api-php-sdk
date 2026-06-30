
# Error Information 20

*This model accepts additional fields of type array.*

## Structure

`ErrorInformation20`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `?string` | Optional | 1-word description of why a request succeeded or failed. | getReason(): ?string | setReason(?string reason): void |
| `message` | `?string` | Optional | The user-facing description for why a request succeeded or failed. | getMessage(): ?string | setMessage(?string message): void |
| `details` | [`?(Detail[])`](../../doc/models/detail.md) | Optional | - | getDetails(): ?array | setDetails(?array details): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ErrorInformation20Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\DetailBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$errorInformation20 = ErrorInformation20Builder::init()
    ->reason('reason4')
    ->message('message8')
    ->details(
        [
            DetailBuilder::init()
                ->field('field4')
                ->reason('reason6')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

