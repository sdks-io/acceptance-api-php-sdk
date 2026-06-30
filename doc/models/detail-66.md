
# Detail 66

*This model accepts additional fields of type array.*

## Structure

`Detail66`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `location` | `?string` | Optional | - | getLocation(): ?string | setLocation(?string location): void |
| `message` | `?string` | Optional | - | getMessage(): ?string | setMessage(?string message): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Detail66Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$detail66 = Detail66Builder::init()
    ->location('location2')
    ->message('message8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

