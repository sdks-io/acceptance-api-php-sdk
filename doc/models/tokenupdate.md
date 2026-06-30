
# Tokenupdate

*This model accepts additional fields of type array.*

## Structure

`Tokenupdate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `status` | `?string` | Optional | The status of the token update.<br><br>Possible value is:<br><br>- SUCCESS<br>- SERVER_ERROR<br>- INVALID_REQUEST | getStatus(): ?string | setStatus(?string status): void |
| `reason` | `?string` | Optional | The reason of the status.<br>Possible values:<br><br>- INVALID_DATA<br>- SYSTEM_ERROR<br>- MISSING_FIELD | getReason(): ?string | setReason(?string reason): void |
| `message` | `?string` | Optional | The detail message related to the status and reason listed above. | getMessage(): ?string | setMessage(?string message): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenupdateBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$tokenupdate = TokenupdateBuilder::init()
    ->status('status6')
    ->reason('reason2')
    ->message('message8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

