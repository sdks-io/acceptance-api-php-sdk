
# Error 2

*This model accepts additional fields of type array.*

## Structure

`Error2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional, Read-only | The type of error.<br><br>Possible Values:<br><br>- instrumentIdentifierDeletionError<br>- tokenIdConflict<br>- conflict | getType(): ?string | setType(?string type): void |
| `message` | `?string` | Optional, Read-only | The detailed message related to the type. | getMessage(): ?string | setMessage(?string message): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Error2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$error2 = Error2Builder::init()
    ->type('type6')
    ->message('message4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

