
# Card Verification 1

*This model accepts additional fields of type array.*

## Structure

`CardVerification1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `resultCode` | `?string` | Optional | CVN result code.<br><br>**Constraints**: *Maximum Length*: `1` | getResultCode(): ?string | setResultCode(?string resultCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CardVerification1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$cardVerification1 = CardVerification1Builder::init()
    ->resultCode('resultCode0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

