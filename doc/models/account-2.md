
# Account 2

*This model accepts additional fields of type array.*

## Structure

`Account2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `correctedAccountNumber` | `?string` | Optional | Corrected account number from the ACH verification service.<br><br>**Constraints**: *Maximum Length*: `17` | getCorrectedAccountNumber(): ?string | setCorrectedAccountNumber(?string correctedAccountNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Account2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$account2 = Account2Builder::init()
    ->correctedAccountNumber('correctedAccountNumber6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

