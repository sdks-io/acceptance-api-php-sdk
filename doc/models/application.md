
# Application

*This model accepts additional fields of type array.*

## Structure

`Application`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | The name of the Visa Acceptance transaction type (such as CC settlement or CC authorization) that the merchant wants to process in a transaction request. More than one transaction type can included in a transaction request. Each transaction type separately returns their own status, reasonCode, rCode, and rFlag messages. | getName(): ?string | setName(?string name): void |
| `status` | `?string` | Optional | The description for this field is not available. | getStatus(): ?string | setStatus(?string status): void |
| `reasonCode` | `?string` | Optional | 3-digit reason code that indicates why the customer profile payment succeeded or failed. | getReasonCode(): ?string | setReasonCode(?string reasonCode): void |
| `rCode` | `?string` | Optional | Indicates whether the service request was successful.<br>Possible values:<br><br>- `-1`: An error occurred.<br>- `0`: The request was declined.<br>- `1`: The request was successful. | getRCode(): ?string | setRCode(?string rCode): void |
| `rFlag` | `?string` | Optional | One-word description of the result of the application. | getRFlag(): ?string | setRFlag(?string rFlag): void |
| `reconciliationId` | `?string` | Optional | Reference number that you use to reconcile your Visa Acceptance reports with your processor reports. | getReconciliationId(): ?string | setReconciliationId(?string reconciliationId): void |
| `rMessage` | `?string` | Optional | Message that explains the reply flag for the application. | getRMessage(): ?string | setRMessage(?string rMessage): void |
| `returnCode` | `?int` | Optional | The description for this field is not available. | getReturnCode(): ?int | setReturnCode(?int returnCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ApplicationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$application = ApplicationBuilder::init()
    ->name('name4')
    ->status('status6')
    ->reasonCode('reasonCode8')
    ->rCode('rCode8')
    ->rFlag('rFlag8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

