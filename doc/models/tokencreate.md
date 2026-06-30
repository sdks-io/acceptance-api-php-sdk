
# Tokencreate

*This model accepts additional fields of type array.*

## Structure

`Tokencreate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `status` | `?string` | Optional | The status of the token create.<br><br>Possible value is:<br><br>- SUCCESS<br>- SERVER_ERROR<br>- INVALID_REQUEST | getStatus(): ?string | setStatus(?string status): void |
| `reason` | `?string` | Optional | The reason of the status.<br><br>Possible values:<br><br>- INVALID_DATA<br>- SYSTEM_ERROR<br>- MISSING_FIELD | getReason(): ?string | setReason(?string reason): void |
| `message` | `?string` | Optional | The detail message related to the status and reason listed above. | getMessage(): ?string | setMessage(?string message): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TokencreateBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$tokencreate = TokencreateBuilder::init()
    ->status('status2')
    ->reason('reason8')
    ->message('message6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

