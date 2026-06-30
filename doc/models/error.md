
# Error

*This model accepts additional fields of type array.*

## Structure

`Error`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional, Read-only | The type of error.<br><br>Possible Values:<br><br>- invalidHeaders<br>- missingHeaders<br>- invalidFields<br>- missingFields<br>- unsupportedPaymentMethodModification<br>- invalidCombination | getType(): ?string | setType(?string type): void |
| `message` | `?string` | Optional, Read-only | The detailed message related to the type. | getMessage(): ?string | setMessage(?string message): void |
| `details` | [`?(Detail40[])`](../../doc/models/detail-40.md) | Optional, Read-only | - | getDetails(): ?array | setDetails(?array details): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ErrorBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Detail40Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$error = ErrorBuilder::init()
    ->type('type6')
    ->message('message4')
    ->details(
        [
            Detail40Builder::init()
                ->name('name0')
                ->location('location4')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            Detail40Builder::init()
                ->name('name0')
                ->location('location4')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            Detail40Builder::init()
                ->name('name0')
                ->location('location4')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

