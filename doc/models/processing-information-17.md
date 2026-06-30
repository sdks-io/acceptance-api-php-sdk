
# Processing Information 17

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation17`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentId` | `?string` | Optional | This field is to accept the id of credit/capture in the body of the requests so the type of void can be identified and processed correctly.<br><br>**Constraints**: *Maximum Length*: `28` | getPaymentId(): ?string | setPaymentId(?string paymentId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation17Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation17 = ProcessingInformation17Builder::init()
    ->paymentId('paymentId2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

