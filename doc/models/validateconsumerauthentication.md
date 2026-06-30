
# Validateconsumerauthentication

*This model accepts additional fields of type array.*

## Structure

`Validateconsumerauthentication`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `status` | `?string` | Optional | The status for payerAuthentication 201 enroll and validate calls. Possible values are:<br><br>- `AUTHENTICATION_SUCCESSFUL`<br>- `PENDING_AUTHENTICATION`<br>- `AUTHENTICATION_FAILED` | getStatus(): ?string | setStatus(?string status): void |
| `reason` | `?string` | Optional | The reason of the status. Possible values are:<br><br>- `INVALID_MERCHANT_CONFIGURATION`<br>- `CONSUMER_AUTHENTICATION_REQUIRED`<br>- `CONSUMER_AUTHENTICATION_FAILED`<br>- `AUTHENTICATION_FAILED` | getReason(): ?string | setReason(?string reason): void |
| `message` | `?string` | Optional | The message describing the reason of the status. Value is:<br><br>- Encountered a Payer Authentication problem. Payer could not be authenticated. | getMessage(): ?string | setMessage(?string message): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ValidateconsumerauthenticationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$validateconsumerauthentication = ValidateconsumerauthenticationBuilder::init()
    ->status('status2')
    ->reason('reason8')
    ->message('message4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

