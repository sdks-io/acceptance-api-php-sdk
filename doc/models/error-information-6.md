
# Error Information 6

*This model accepts additional fields of type array.*

## Structure

`ErrorInformation6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `?string` | Optional | The reason of status | getReason(): ?string | setReason(?string reason): void |
| `message` | `?string` | Optional | The detailed message related to the status and reason listed above. | getMessage(): ?string | setMessage(?string message): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ErrorInformation6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$errorInformation6 = ErrorInformation6Builder::init()
    ->reason('reason4')
    ->message('message8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

