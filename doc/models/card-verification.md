
# Card Verification

*This model accepts additional fields of type array.*

## Structure

`CardVerification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `resultCode` | `?string` | Optional | CVN result code.<br><br>**Constraints**: *Maximum Length*: `1` | getResultCode(): ?string | setResultCode(?string resultCode): void |
| `resultCodeRaw` | `?string` | Optional | CVN result code sent directly from the processor. Returned only when the processor returns this value.<br><br>**Important** Do not use this field to evaluate the result of card verification. Use for debugging purposes only.<br><br>**Constraints**: *Maximum Length*: `10` | getResultCodeRaw(): ?string | setResultCodeRaw(?string resultCodeRaw): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CardVerificationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$cardVerification = CardVerificationBuilder::init()
    ->resultCode('resultCode4')
    ->resultCodeRaw('resultCodeRaw4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

