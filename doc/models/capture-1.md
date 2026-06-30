
# Capture 1

*This model accepts additional fields of type array.*

## Structure

`Capture1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `status` | `?string` | Optional | The status of the submitted transaction.<br><br>Possible values:<br><br>- PENDING<br>- TRANSMITTED (Only for Online Capture enabled merchants) | getStatus(): ?string | setStatus(?string status): void |
| `reason` | `?string` | Optional | The reason of the status.<br><br>Possible values:<br><br>- MISSING_FIELD<br>- INVALID_DATA<br>- DUPLICATE_REQUEST<br>- INVALID_MERCHANT_CONFIGURATION<br>- EXCEEDS_AUTH_AMOUNT<br>- AUTH_ALREADY_REVERSED<br>- TRANSACTION_ALREADY_SETTLED<br>- INVALID_AMOUNT<br>- MISSING_AUTH<br>- TRANSACTION_ALREADY_REVERSED_OR_SETTLED<br>- NOT_SUPPORTED | getReason(): ?string | setReason(?string reason): void |
| `message` | `?string` | Optional | The detail message related to the status and reason listed above. | getMessage(): ?string | setMessage(?string message): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Capture1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$capture1 = Capture1Builder::init()
    ->status('status0')
    ->reason('reason6')
    ->message('message2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

