
# Error 8

*This model accepts additional fields of type array.*

## Structure

`Error8`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional, Read-only | The type of error.<br><br>Possible Values:<br><br>- notAvailable | getType(): ?string | setType(?string type): void |
| `message` | `?string` | Optional, Read-only | The detailed message related to the type. | getMessage(): ?string | setMessage(?string message): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Error8Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$error8 = Error8Builder::init()
    ->type('type0')
    ->message('message0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

