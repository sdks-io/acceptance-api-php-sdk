
# Error Information 17

*This model accepts additional fields of type array.*

## Structure

`ErrorInformation17`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `?string` | Optional | The reason of the status. | getReason(): ?string | setReason(?string reason): void |
| `message` | `?string` | Optional | The detail message related to the status and reason listed above. | getMessage(): ?string | setMessage(?string message): void |
| `details` | [`?(Detail27[])`](../../doc/models/detail-27.md) | Optional | - | getDetails(): ?array | setDetails(?array details): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ErrorInformation17Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Detail27Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$errorInformation17 = ErrorInformation17Builder::init()
    ->reason('reason6')
    ->message('message0')
    ->details(
        [
            Detail27Builder::init()
                ->reason('reason6')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            Detail27Builder::init()
                ->reason('reason6')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            Detail27Builder::init()
                ->reason('reason6')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

