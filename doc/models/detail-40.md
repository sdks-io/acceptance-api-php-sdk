
# Detail 40

*This model accepts additional fields of type array.*

## Structure

`Detail40`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional, Read-only | The name of the field that caused the error. | getName(): ?string | setName(?string name): void |
| `location` | `?string` | Optional, Read-only | The location of the field that caused the error. | getLocation(): ?string | setLocation(?string location): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Detail40Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$detail40 = Detail40Builder::init()
    ->name('name0')
    ->location('location4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

