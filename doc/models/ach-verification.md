
# Ach Verification

*This model accepts additional fields of type array.*

## Structure

`AchVerification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `resultCode` | `?string` | Optional | Results from the ACH verification service.<br><br>**Constraints**: *Maximum Length*: `2` | getResultCode(): ?string | setResultCode(?string resultCode): void |
| `resultCodeRaw` | `?string` | Optional | Raw results from the ACH verification service.<br><br>**Constraints**: *Maximum Length*: `10` | getResultCodeRaw(): ?string | setResultCodeRaw(?string resultCodeRaw): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AchVerificationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$achVerification = AchVerificationBuilder::init()
    ->resultCode('resultCode0')
    ->resultCodeRaw('resultCodeRaw8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

