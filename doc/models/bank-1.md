
# Bank 1

*This model accepts additional fields of type array.*

## Structure

`Bank1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `account` | [`?Account2`](../../doc/models/account-2.md) | Optional | - | getAccount(): ?Account2 | setAccount(?Account2 account): void |
| `correctedRoutingNumber` | `?string` | Optional | Corrected account number from the ACH verification service.<br><br>**Constraints**: *Maximum Length*: `9` | getCorrectedRoutingNumber(): ?string | setCorrectedRoutingNumber(?string correctedRoutingNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bank1 = Bank1Builder::init()
    ->account(
        Account2Builder::init()
            ->correctedAccountNumber('correctedAccountNumber4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->correctedRoutingNumber('correctedRoutingNumber6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

